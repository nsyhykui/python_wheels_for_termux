# 📚 Termux Python 包安装教程

> 🌐 **语言：** [English](index.md) · **简体中文**

本系列教程教你如何在 Termux 上安装 Python 包，无需等待编译，直接使用预编译的 wheel 包。

## ⚡ 为什么要用预编译源？

### ❌ 不用预编译源（官方 PyPI）

```bash
$ pip install numpy
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Downloading numpy-2.4.4.tar.gz (20.7 MB)
...
error: subprocess-exited-with-error
```

⚠️ 编译失败，折腾半小时还是装不上。

**结果：** 编译失败，浪费大量时间 ⏱️

### ✅ 使用预编译源（本仓库）

```bash
$ pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
Looking in indexes: https://nsyhykui.github.io/...
Downloading numpy-2.4.4-cp313-cp313-android_24_arm64_v8a.whl (5.7 MB)
...
Successfully installed numpy-2.4.4
real 2m47.352s
```

**结果：** 不到 3 分钟装好 ✅

> 💡 设置一次，之后直接 `pip install 包名`：
>
> ```bash
> pip config set global.index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/
> ```

## 📖 全部教程

- [📦 如何在 Termux 上安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [📊 如何在 Termux 上安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [🔬 如何在 Termux 上安装 SciPy](how-to-install-scipy-on-termux.zh_cn.md)
- [📓 如何在 Termux 上安装 Jupyter](how-to-install-jupyter-on-termux.zh_cn.md)
- [📈 如何在 Termux 上安装 Matplotlib](how-to-install-matplotlib-on-termux.zh_cn.md)
- [🔥 如何在 Termux 上安装 PyTorch](how-to-install-torch-on-termux.zh_cn.md)

## 💡 更多包

把命令里的包名替换即可，支持 1200+ 预编译包。查看完整列表：[包索引](https://nsyhykui.github.io/python_wheels_for_termux/)。

---

🔗 [← 返回包索引首页](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub 仓库](https://github.com/nsyhykui/python_wheels_for_termux)
