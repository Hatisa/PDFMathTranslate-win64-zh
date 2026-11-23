基于 [PDFMathTranslate](https://github.com/PDFMathTranslate/PDFMathTranslate) **v1.9.11** 的 Windows 64 位便携版，界面完整汉化，解压双击即用。

## 下载

| 文件 | 大小 | 说明 |
|---|---|---|
| `PDFMathTranslate-1.9.11-win64-zh.zip` | 约 640 MB | 完整便携包：内置 Python 3.12、全部依赖、版面检测模型、25 套离线字体 |

- 系统要求：Windows 10 / 11 64 位。
- 双击无反应？先安装包内 `vc_redist.x64.exe`（微软 VC++ 运行库）。

## 使用

1. 解压到任意目录，双击 `PDFMathTranslate.exe`（黑色窗口是程序本体，使用期间不要关闭）。
2. 浏览器会自动打开 <http://127.0.0.1:7860/>（端口被占用会自动顺延，按窗口提示的地址访问）。
3. 「输入方式」选「文件」→ 选择 PDF；选「源语言 / 目标语言」，如 English → 简体中文。
4. 「翻译服务」默认 **Bing**（免费、免注册、国内可用）；需要 API Key 的服务（OpenAI / DeepSeek / 智谱 / Gemini / DeepL / Azure 等）在界面中填入即可。
5. 点「开始翻译」，在「翻译结果」下载 `-mono.pdf`（纯译文）或 `-dual.pdf`（双语对照）。

首次启动会解压自带模型与字体到 `%USERPROFILE%\.cache\babeldoc`（约 320 MB），之后启动秒开。

## 本版改动

1. 界面全中文：标签、按钮、提示、错误信息（语言 / 页码下拉为「中文显示、英文取值」，翻译逻辑不变）。
2. Gradio 自带组件文案中文化（强制前端语言 zh-CN，英文浏览器下也是中文界面）。
3. 默认翻译服务改为 **Bing**（Google 国内易被 429 限流，仍可手动切换）。
4. 启动器：自动探测 7860–7889 空闲端口、首启还原离线资源、异常不闪退、`--help` 显示正确程序名。
5. 附带 `vc_redist.x64.exe` 与 `创建桌面快捷方式.bat`。

改动源码见仓库 [`source/`](https://github.com/Hatisa/PDFMathTranslate-win64-zh/tree/main/source) 与 [SOURCE.md](https://github.com/Hatisa/PDFMathTranslate-win64-zh/blob/main/SOURCE.md)。

## 许可

本发行版为上游 **AGPL-3.0** 项目的打包汉化，同样以 AGPL-3.0 发布；上游版权归 PDFMathTranslate 作者所有。
