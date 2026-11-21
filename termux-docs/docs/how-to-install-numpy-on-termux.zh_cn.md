# 📦 如何在 Termux 上安装 NumPy（无需编译）

> 🌐 **语言：** [English](how-to-install-numpy-on-termux.md) · **简体中文**

在 Termux 上直接 `pip install numpy` 会触发漫长编译，这里教你绕过编译直接装。

## 第 1 步：安装系统依赖

```bash
pkg install libopenblas
```

## 第 2 步：从预编译源安装 NumPy

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
```

## 第 3 步：验证

```bash
python -c "import numpy as np; print(np.__version__)"
```

> ⚠️ **如果报错 `libopenblas.so not found`**
>
> 重新运行 `pkg install libopenblas` 即可。其他 `dlopen failed: library "xxx.so" not found` 同理：去掉 `.so` 后缀，用 `pkg install` 装上对应包。

## 相关教程

- [安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [安装 SciPy](how-to-install-scipy-on-termux.zh_cn.md)
- [安装 Matplotlib](how-to-install-matplotlib-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
