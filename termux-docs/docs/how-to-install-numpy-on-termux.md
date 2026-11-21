# 📦 How to Install NumPy on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-numpy-on-termux.zh_cn.md)

Running `pip install numpy` on Termux triggers a long build. This guide skips it and installs NumPy straight from the prebuilt wheel index.

## Step 1 — Install the system dependency

```bash
pkg install libopenblas
```

## Step 2 — Install NumPy from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
```

## Step 3 — Verify

```bash
python -c "import numpy as np; print(np.__version__)"
```

> ⚠️ **If you get `libopenblas.so not found`**
>
> Just rerun `pkg install libopenblas`. For any other `dlopen failed: library "xxx.so" not found` error, drop the `.so` suffix and install the matching Termux package with `pkg install`.

## Related guides

- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install SciPy](how-to-install-scipy-on-termux.md)
- [Install Matplotlib](how-to-install-matplotlib-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
