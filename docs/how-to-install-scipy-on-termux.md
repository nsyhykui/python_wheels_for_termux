# 🔬 How to Install SciPy on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-scipy-on-termux.zh_cn.md)

SciPy needs a Fortran/BLAS toolchain to build from source. Skip all of that with the prebuilt wheel index.

## Step 1 — Install the system dependency

```bash
pkg install libopenblas
```

## Step 2 — Install SciPy from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ scipy
```

## Step 3 — Verify

```bash
python -c "import scipy; print(scipy.__version__)"
```

> ⚠️ **If you get `dlopen failed: library "xxx.so" not found`**
>
> Drop the `.so` suffix and install the matching Termux package, e.g. `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install Matplotlib](how-to-install-matplotlib-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
