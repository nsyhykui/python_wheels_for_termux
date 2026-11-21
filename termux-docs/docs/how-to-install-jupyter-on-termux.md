# 📓 How to Install Jupyter on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-jupyter-on-termux.zh_cn.md)

Jupyter pulls in a large dependency tree that is painful to build on Termux. Install the whole stack from the prebuilt wheel index instead.

## Step 1 — Install Jupyter from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ jupyter
```

pip resolves every dependency (NumPy, traitlets, tornado, and so on) from the same index; no manual builds needed.

## Step 2 — Verify

```bash
jupyter --version
```

## Step 3 — Start the notebook server

```bash
jupyter notebook
```

Open the URL printed in the terminal (it contains the access token) in your browser.

> ⚠️ **If you get `dlopen failed: library "xxx.so" not found`**
>
> Drop the `.so` suffix and install the matching Termux package with `pkg install`, e.g. `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install Matplotlib](how-to-install-matplotlib-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
