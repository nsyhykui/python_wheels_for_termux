# 🔥 How to Install PyTorch on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-torch-on-termux.zh_cn.md)

Running `pip install torch` on Termux usually fails — PyPI has no official prebuilt wheel for Termux (Android aarch64), so pip tries to build from source, which is extremely slow and often crashes with out-of-memory errors.

## Step 1 — Install PyTorch from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ torch
```

The PyTorch wheel is large, so the download takes a while. That is normal.

## Step 2 — Verify

```bash
python -c "import torch; print(torch.__version__); print(torch.rand(3, 3))"
```

You should see a version number and a random tensor, for example:

```text
2.x.x
tensor([[0.1234, 0.5678, 0.9012],
        [0.3456, 0.7890, 0.2345],
        [0.6789, 0.0123, 0.4567]])
```

## FAQ

**Q: Why does PyTorch from official PyPI not install?**
PyTorch only ships prebuilt wheels for Linux (manylinux) and Windows. On Termux, `sys.platform` is `android` rather than `linux`, so the PyPI wheels do not match.

**Q: Can this PyTorch use a GPU?**
No. The wheel in this index is CPU-only: `torch.cuda.is_available()` returns `False` and `torch.version.cuda` is `None`. It is suitable for learning and light inference.

**Q: What about linker warnings on `import torch`?**
Warnings such as `unused DT entry: unknown processor-specific ... (ignoring)` are harmless Android linker notes about ELF entries and do not affect runtime.

> ⚠️ **Getting `dlopen failed: library "xxx.so" not found`?**
>
> Drop the `.so` suffix and install the matching Termux package with `pkg install`: `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install OpenCV](how-to-install-opencv-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
