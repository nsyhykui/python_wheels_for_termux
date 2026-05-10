# python_wheels_for_termux

🎉 **在 Termux 上装 Python 包，不用再等编译了！**

本仓库提供 Termux (Android) 环境下预编译的 Python wheel 包 (.whl)，让你安装 numpy、pandas 等常用包时直接安装，告别漫长的编译等待。

## 📦 包含的包及更新日志

| 文件 | 适用架构 | 说明 |
|------|----------|------|
| [包索引](./wheels/index.html) | aarch64 / arm64-v8a | 800+预编译 wheel 的完整列表（可以搜索包名（链接：https://nsyhykui.github.io/python_wheels_for_termux/wheels ）） |
| [更新日志](./update-libs/) | - | 更新日志 |
| [错误日志](./error-libs-logs/) | - | 构建失败的包日志 |

## 🚀 快速开始

直接使用本仓库作为 pip 源：

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ 包名
```

例如安装 numpy：

```bash
pip install --index-url https://nsyhykui.github.io/python_wheels_for_termux/simple/ numpy
```

⚠️ 注意事项

· 非完整 PyPI 源：本仓库仅包含部分预编译包，若未找到你需要的包，请使用官方 PyPI 源或其他第三方源。
· 适用环境：主要针对 Termux 环境，特别是 android(aarch64) 架构系统。
· Python 版本：请确保你的 Python 版本与 wheel 包（支持Python3.13，Python3.12（Python3.12已停止更新））匹配。
· **动态库依赖**：部分包（如 numpy、scipy、pandas）运行时需要系统动态库。若遇到类似 `dlopen failed: library "libopenblas.so" not found` 的错误，请根据缺失的库名安装对应的 Termux 包：
  ```bash
  pkg install libopenblas   # 去掉 .so 后缀，即 libopenblas.so → libopenblas
```
📄 许可证

Apache 2.0 License

## 许可证与致谢

- 本仓库中的预编译 `.whl` 文件，基于 Termux 官方提供的二进制文件重新打包而成，**未对原始代码进行任何修改**。
- 每个 `.whl` 文件内部均已包含其对应软件（如 psutil、opencv-python、cmake、grpcio 等）的原始许可证文件（如 `LICENSE`），使用前请仔细阅读。
- 本项目的打包脚本 `update-python-wheels.sh` 采用 [Apache-2.0](LICENSE) 许可证。
- 特别致谢 [Termux](https://termux.dev/) 项目及其贡献者，本仓库的存在离不开他们的卓越工作。

## 📅 更新日志

### 2026-05-07
- **许可证变更**：从 MIT 切换到 Apache 2.0，新增 `NOTICE` 文件，明确要求保留版权和来源链接

## 相关教程

如果你想知道具体怎么安装某个包，可以看这些教程：

- [如何在 Termux 上安装 NumPy（无需编译）](./docs/how-to-install-numpy-on-termux.html)
- [如何在 Termux 上安装 Pandas（无需编译）](./docs/how-to-install-pandas-on-termux.html)
- [如何在 Termux 上安装 SciPy（无需编译）](./docs/how-to-install-scipy-on-termux.html)
---

⭐ 如果这个项目对你有帮助，欢迎 [来 GitHub 给个 Star](https://github.com/nsyhykui/python_wheels_for_termux)，感谢支持～
