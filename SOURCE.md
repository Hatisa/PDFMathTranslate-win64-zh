# 源码与重建说明（AGPL-3.0 合规）

本发行版是 [PDFMathTranslate](https://github.com/PDFMathTranslate/PDFMathTranslate) v1.9.11（AGPL-3.0）的**打包与界面汉化**，未修改翻译算法、模型或 `babeldoc` 依赖。

## 发行包构成

`PDFMathTranslate-1.9.11-win64-zh.zip` = 官方发行包 `pdf2zh-v1.9.11-with-assets-win64.zip`（GitHub Releases，546 MB，含嵌入式 Python 3.12 运行环境、依赖、检测模型与字体离线包）经下列改动后重新压缩：

| 文件 | 改动 |
|---|---|
| `pdf2zh.exe` | 改名为 `PDFMathTranslate.exe`（PyStand 宿主） |
| `_pystand_static.int` | 重写启动脚本：中文横幅、空闲端口探测、离线资源还原、错误不闪退、`--help` 显示正确程序名 |
| `site-packages/pdf2zh/gui.py` | 界面汉化；下拉框选项改为「中文显示 / 英文取值」；默认翻译服务 Bing |
| `site-packages/gradio/templates/frontend/index.html` | 强制前端语言为 zh-CN（用 `Object.defineProperty` 覆盖 `navigator.language`） |
| `无法运行请安装vc_redist.x64.exe` | 改名为 `vc_redist.x64.exe` |
| `使用说明.txt`、`创建桌面快捷方式.bat` | 新增 |

其余文件（`runtime/`、`site-packages/` 的其它内容、`offline_assets_*.zip`）与官方包逐字节一致。

## 本仓库 `source/` 目录

| 文件 | 对应发行包位置 |
|---|---|
| `source/pdf2zh_gui.py` | `site-packages/pdf2zh/gui.py`（本版） |
| `source/gradio_index.html` | `site-packages/gradio/templates/frontend/index.html`（本版） |
| `source/_pystand_static.int` | 启动脚本（本版） |
| `source/使用说明.txt` | 发行包内使用说明 |

## 如何重建

1. 从上游 Releases 下载 `pdf2zh-v1.9.11-with-assets-win64.zip` 并解压。
2. 用本仓库 `source/` 中的同名文件覆盖对应位置（`pdf2zh_gui.py` → `site-packages/pdf2zh/gui.py`，`gradio_index.html` → `site-packages/gradio/templates/frontend/index.html`）。
3. 把 `pdf2zh.exe` 改名 `PDFMathTranslate.exe`，`无法运行请安装vc_redist.x64.exe` 改名 `vc_redist.x64.exe`。
4. 重新压缩即可得到与本发行版一致的目录结构。

## 许可证

本发行版整体遵循 **AGPL-3.0**（与上游一致）。上游版权归 PDFMathTranslate 项目作者所有。
