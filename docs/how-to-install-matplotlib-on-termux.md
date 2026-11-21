# 📈 How to Install Matplotlib on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-matplotlib-on-termux.zh_cn.md)

Matplotlib needs native libraries (freetype, PNG) to build from source. Skip the build with the prebuilt wheel index.

## Step 1 — Install Matplotlib from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ matplotlib
```

pip resolves dependencies such as NumPy and Pillow automatically.

## Step 2 — Verify

```bash
python -c "import matplotlib; print(matplotlib.__version__)"
```

> ⚠️ **If you get `dlopen failed: library "xxx.so" not found`**
>
> Drop the `.so` suffix and install the matching Termux package with `pkg install`, e.g. `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install Jupyter](how-to-install-jupyter-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
