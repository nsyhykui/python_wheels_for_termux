# 📊 How to Install Pandas on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-pandas-on-termux.zh_cn.md)

Building Pandas from source on Termux is slow and often fails. Install it from the prebuilt wheel index instead.

## Step 1 — Install the system dependency

```bash
pkg install libopenblas
```

## Step 2 — Install Pandas from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ pandas
```

pip resolves and installs dependencies such as NumPy automatically; no manual steps needed.

## Step 3 — Verify

```bash
python -c "import pandas as pd; print(pd.__version__)"
```

> ⚠️ **If you get `dlopen failed: library "xxx.so" not found`**
>
> Drop the `.so` suffix and install the matching Termux package, e.g. `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install SciPy](how-to-install-scipy-on-termux.md)
- [Install Matplotlib](how-to-install-matplotlib-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
