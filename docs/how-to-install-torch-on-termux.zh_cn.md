# 🔥 如何在 Termux 上安装 PyTorch（无需编译）

> 🌐 **语言：** [English](how-to-install-torch-on-termux.md) · **简体中文**

在 Termux 上直接 `pip install torch` 通常会失败——PyPI 上没有 Termux (Android aarch64) 的官方预编译 wheel，pip 会尝试从源码编译，过程极慢且经常因内存不足而崩溃。

## 第 1 步：从预编译源安装 PyTorch

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ torch
```

PyTorch 的 wheel 体积较大，下载需要一些时间，属正常现象。

## 第 2 步：验证

```bash
python -c "import torch; print(torch.__version__); print(torch.rand(3, 3))"
```

正常会输出版本号和一个随机张量，比如：

```text
2.x.x
tensor([[0.1234, 0.5678, 0.9012],
        [0.3456, 0.7890, 0.2345],
        [0.6789, 0.0123, 0.4567]])
```

## 常见问题

**Q：官方 PyPI 的 PyTorch 为什么装不上？**
PyTorch 官方只为 Linux (manylinux) 和 Windows 提供预编译 wheel，Termux 的 `sys.platform` 是 `android` 而非 `linux`，因此 PyPI 上的 wheel 无法匹配。

**Q：这个 PyTorch 能跑 GPU 吗？**
不能。本源的 PyTorch 是 CPU 版本：`torch.cuda.is_available()` 返回 `False`，`torch.version.cuda` 为 `None`，适合学习和轻量推理。

**Q：`import torch` 时刷出 linker warning 怎么办？**
类似 `unused DT entry: unknown processor-specific ... (ignoring)` 的警告可以忽略，是 Android linker 对 ELF 条目的提示，不影响运行。

> ⚠️ **遇到 `dlopen failed: library "xxx.so" not found`？**
>
> 把 `.so` 去掉，用 `pkg install` 装上就行：`libopenblas.so` → `pkg install libopenblas`。

## 相关教程

- [安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [安装 OpenCV](how-to-install-opencv-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
