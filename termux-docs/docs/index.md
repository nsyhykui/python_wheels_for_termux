# 📚 Termux Python Package Installation Guides

> 🌐 **Languages:** **English** · [简体中文](index.zh_cn.md)

This series shows how to install Python packages on Termux without waiting for builds — just use the prebuilt wheels.

## ⚡ Why use a prebuilt index?

### ❌ Without a prebuilt index (official PyPI)

```bash
$ pip install numpy
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Downloading numpy-2.4.4.tar.gz (20.7 MB)
...
error: subprocess-exited-with-error
```

⚠️ Build still fails after half an hour of tinkering.

**Result:** Build fails and a lot of time is wasted ⏱️

### ✅ Using this repository's prebuilt index

```bash
$ pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
Looking in indexes: https://nsyhykui.github.io/...
Downloading numpy-2.4.4-cp313-cp313-android_24_arm64_v8a.whl (5.7 MB)
...
Successfully installed numpy-2.4.4
real 2m47.352s
```

**Result:** Installed in under 3 minutes ✅

> 💡 Set it once, then just `pip install <package>`:
>
> ```bash
> pip config set global.index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/
> ```

## 📖 All guides

- [📦 How to Install NumPy on Termux](how-to-install-numpy-on-termux.md)
- [📊 How to Install Pandas on Termux](how-to-install-pandas-on-termux.md)
- [🔬 How to Install SciPy on Termux](how-to-install-scipy-on-termux.md)
- [📓 How to Install Jupyter on Termux](how-to-install-jupyter-on-termux.md)
- [📈 How to Install Matplotlib on Termux](how-to-install-matplotlib-on-termux.md)
- [🔥 How to Install PyTorch on Termux](how-to-install-torch-on-termux.md)

## 💡 More packages

Just replace the package name in the command — 1200+ prebuilt wheels are available. See the full list: [Package index](https://nsyhykui.github.io/python_wheels_for_termux/).

---

🔗 [← Back to package index](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub repository](https://github.com/nsyhykui/python_wheels_for_termux)
