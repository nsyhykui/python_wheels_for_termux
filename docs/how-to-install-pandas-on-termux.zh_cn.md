# 📊 如何在 Termux 上安装 Pandas（无需编译）

> 🌐 **语言：** [English](how-to-install-pandas-on-termux.md) · **简体中文**

在 Termux 上从源码编译 Pandas 又慢又容易失败，直接使用预编译源即可。

## 第 1 步：安装系统依赖

```bash
pkg install libopenblas
```

## 第 2 步：从预编译源安装 Pandas

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ pandas
```

pip 会自动解析并安装 NumPy 等依赖，无需手动处理。

## 第 3 步：验证

```bash
python -c "import pandas as pd; print(pd.__version__)"
```

> ⚠️ **遇到 `dlopen failed: library "xxx.so" not found`？**
>
> 去掉 `.so` 后缀，用 `pkg install` 装上对应包，例如 `libopenblas.so` → `pkg install libopenblas`。

## 相关教程

- [安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [安装 SciPy](how-to-install-scipy-on-termux.zh_cn.md)
- [安装 Matplotlib](how-to-install-matplotlib-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
