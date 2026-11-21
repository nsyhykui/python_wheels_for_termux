# python_wheels_for_termux

> **Languages:** **English** ([README.md](README.md)) · [简体中文](README.zh_cn.md)

🎉 **Install Python packages on Termux — no more waiting for builds!**

This repository provides prebuilt Python wheels (`.whl`) for Termux (Android), so you can install common packages such as NumPy and Pandas directly, without long compilation waits.

## 📦 Packages & Changelog

| File | Architecture | Description |
|------|--------------|-------------|
| [Package index](./wheels/simple/index.html) | aarch64 / arm64-v8a | Full list of 1200+ prebuilt wheels (link: https://nsyhykui.github.io/python_wheels_for_termux/wheels/simple/ ) |
| [Changelog](./update-libs/) | - | Changelog |
| [Error logs](./error-libs-logs/) | - | Build-failure logs |

## 🚀 Quick start

Use this repository directly as a pip index:

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ <package>
```

For example, to install NumPy:

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
```

⚠️ Notes

- **Not a full PyPI mirror**: this repository only contains a subset of prebuilt packages. If the package you need is missing, use the official PyPI index or another third-party index.
- **Target environment**: mainly Termux, especially Android (aarch64) systems.
- **Python version**: make sure your Python version matches the wheels (Python 3.14 supported; Python 3.13 and 3.12 are no longer updated).
- **Shared library dependencies**: some packages (e.g. NumPy, SciPy, Pandas) need system shared libraries at runtime. If you hit an error such as `dlopen failed: library "libopenblas.so" not found`, install the matching Termux package by dropping the `.so` suffix:
  ```bash
  pkg install libopenblas   # libopenblas.so → libopenblas
  ```

📄 License

Apache 2.0 License

## License & Acknowledgements

- The prebuilt `.whl` files in this repository are repackaged from binaries provided by Termux, **without any modification to the original code**.
- Every `.whl` ships the original license file (e.g. `LICENSE`) of its upstream software (psutil, opencv-python, cmake, grpcio, etc.). Please read it before use.
- The packaging script `update-python-wheels.sh` is licensed under [Apache-2.0](LICENSE).
- Special thanks to the [Termux](https://termux.dev/) project and its contributors — this repository would not exist without their excellent work.

## 📅 Changelog

### 2026-11-21
- **Added English documentation**: the README, site homepage, and all installation guides are now available in English, with language switchers.

### 2026-05-07
- **License change**: switched from MIT to Apache 2.0, added a `NOTICE` file requiring preservation of copyright and source links.

## Related guides

Want step-by-step instructions for a specific package? See:

- [How to install NumPy on Termux (no compilation)](./docs/how-to-install-numpy-on-termux.md)
- [How to install Pandas on Termux (no compilation)](./docs/how-to-install-pandas-on-termux.md)
- [How to install SciPy on Termux (no compilation)](./docs/how-to-install-scipy-on-termux.md)
- [How to install Jupyter on Termux (no compilation)](./docs/how-to-install-jupyter-on-termux.md)
- [How to install Matplotlib on Termux (no compilation)](./docs/how-to-install-matplotlib-on-termux.md)
- [How to install PyTorch on Termux (no compilation)](./docs/how-to-install-torch-on-termux.md)
- [How to install OpenCV on Termux (no compilation, FFmpeg version caveat)](./docs/how-to-install-opencv-on-termux.md)

---

⭐ If this project helps you, please [give it a Star on GitHub](https://github.com/nsyhykui/python_wheels_for_termux). Thanks for your support!
