# 📓 如何在 Termux 上安装 Jupyter（无需编译）

> 🌐 **语言：** [English](how-to-install-jupyter-on-termux.md) · **简体中文**

Jupyter 依赖树很大，在 Termux 上逐个编译非常折腾。直接从预编译源一次装齐。

## 第 1 步：从预编译源安装 Jupyter

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ jupyter
```

pip 会从同一个源自动解析全部依赖（NumPy、traitlets、tornado 等），无需手动编译。

## 第 2 步：验证

```bash
jupyter --version
```

## 第 3 步：启动 Notebook

```bash
jupyter notebook
```

在浏览器打开终端里打印出来的地址（带 token 的那个）即可。

> ⚠️ **遇到 `dlopen failed: library "xxx.so" not found`？**
>
> 去掉 `.so` 后缀，用 `pkg install` 装上对应包，例如 `libopenblas.so` → `pkg install libopenblas`。

## 相关教程

- [安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [安装 Matplotlib](how-to-install-matplotlib-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
