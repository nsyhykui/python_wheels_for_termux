# 📈 如何在 Termux 上安装 Matplotlib（无需编译）

> 🌐 **语言：** [English](how-to-install-matplotlib-on-termux.md) · **简体中文**

Matplotlib 从源码编译需要 freetype、PNG 等原生库，在 Termux 上很麻烦。直接使用预编译源。

## 第 1 步：从预编译源安装 Matplotlib

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ matplotlib
```

pip 会自动解析 NumPy、Pillow 等依赖。

## 第 2 步：验证

```bash
python -c "import matplotlib; print(matplotlib.__version__)"
```

> ⚠️ **遇到 `dlopen failed: library "xxx.so" not found`？**
>
> 去掉 `.so` 后缀，用 `pkg install` 装上对应包，例如 `libopenblas.so` → `pkg install libopenblas`。

## 相关教程

- [安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [安装 Jupyter](how-to-install-jupyter-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
