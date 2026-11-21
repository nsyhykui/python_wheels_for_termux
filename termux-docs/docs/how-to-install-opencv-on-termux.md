# 👁️ How to Install OpenCV on Termux (No Compilation)

> 🌐 **Languages:** **English** · [简体中文](how-to-install-opencv-on-termux.zh_cn.md)

Running `pip install opencv-python` on Termux builds OpenCV from source — a slow process that often stalls on dependency detection. Here is how to install it directly from a prebuilt wheel.

## Step 1 — Install OpenCV from the prebuilt index

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ opencv-python
```

pip resolves and installs dependencies such as NumPy automatically; no manual steps needed.

## Step 2 — Verify

```bash
python -c "import cv2; print(cv2.__version__)"
```

You should see a version number, for example `4.12.0`.

## FFmpeg version compatibility (important)

The OpenCV wheel in this index is built against **FFmpeg 8.x** and needs `libavcodec.so.62` at runtime. However, the official Termux repositories have moved to **FFmpeg 9.x**, so installing it directly may fail with:

```text
ImportError: dlopen failed: library "libavcodec.so.62" not found
```

There are currently two ways to handle this:

- **Downgrade FFmpeg to 8.x**: manually download and install `ffmpeg_8.x_aarch64.deb` from a Termux historical mirror. Note that the TUR repository currently only offers `ffmpeg5.1` and `ffmpeg7` — no 8.x — so you will need to find a historical package yourself. Downgrading may affect other software that depends on FFmpeg 9; assess the impact yourself.
- **Wait for a newer OpenCV**: install once this index has rebuilt the wheel against FFmpeg 9.x. Until then, OpenCV's video read/write features may not work.

> ⚠️ **Other `dlopen failed: library "xxx.so" not found` errors?**
>
> Drop the `.so` suffix and install the package with `pkg install`:
> `libopenblas.so` → `pkg install libopenblas`.

## Related guides

- [Install NumPy](how-to-install-numpy-on-termux.md)
- [Install Pandas](how-to-install-pandas-on-termux.md)
- [Install Matplotlib](how-to-install-matplotlib-on-termux.md)

---

🔗 [← Back to guides](index.md) · [📦 Package index (1200+ packages)](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
