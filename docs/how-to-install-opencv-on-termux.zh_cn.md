# 👁️ 如何在 Termux 上安装 OpenCV（无需编译）

> 🌐 **语言：** [English](how-to-install-opencv-on-termux.md) · **简体中文**

在 Termux 上直接 `pip install opencv-python` 会从源码编译 OpenCV，过程很慢，还经常卡在依赖检测上。这里用预编译 wheel 直接装。

## 第 1 步：从预编译源安装 OpenCV

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ opencv-python
```

pip 会自动解析并安装 NumPy 等依赖，无需手动处理。

## 第 2 步：验证

```bash
python -c "import cv2; print(cv2.__version__)"
```

正常会输出版本号，例如 `4.12.0`。

## FFmpeg 版本兼容（重要）

本源的 OpenCV wheel 基于 **FFmpeg 8.x** 构建，运行时需要 `libavcodec.so.62`。但 Termux 官方仓库已升级到 **FFmpeg 9.x**，直接安装可能报：

```text
ImportError: dlopen failed: library "libavcodec.so.62" not found
```

目前有两种处理方式：

- **降级 FFmpeg 到 8.x**：从 Termux 历史镜像手动下载并安装 `ffmpeg_8.x_aarch64.deb`。注意 TUR 仓库目前只有 `ffmpeg5.1` 和 `ffmpeg7`，没有 8.x，需要自己找历史包。降级可能影响其他依赖 FFmpeg 9 的软件，请自行评估。
- **等新版 OpenCV**：等本源基于 FFmpeg 9.x 重编 wheel 后再装。在此之前，OpenCV 的视频读写功能可能不可用。

> ⚠️ **其他 `dlopen failed: library "xxx.so" not found` 报错？**
>
> 去掉 `.so` 后缀，用 `pkg install` 装上对应包：`libopenblas.so` → `pkg install libopenblas`。

## 相关教程

- [安装 NumPy](how-to-install-numpy-on-termux.zh_cn.md)
- [安装 Pandas](how-to-install-pandas-on-termux.zh_cn.md)
- [安装 Matplotlib](how-to-install-matplotlib-on-termux.zh_cn.md)

---

🔗 [← 返回教程首页](index.zh_cn.md) · [📦 包索引（1200+ 包）](https://nsyhykui.github.io/python_wheels_for_termux/) · ⭐ [GitHub](https://github.com/nsyhykui/python_wheels_for_termux)
