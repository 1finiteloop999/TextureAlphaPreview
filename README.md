# TextureAlphaPreview — UE5 Texture Alpha Thumbnail Preview Plugin

TextureAlphaPreview is an Unreal Engine 5 editor plugin that displays
Texture2D alpha channels and RGBA transparency directly in Content Browser
thumbnails.

It helps inspect VFX textures whose thumbnails appear as white squares
because their shape is stored in the alpha channel.

Preview modes include Alpha grayscale and RGBA with a checkerboard
background, with automatic analysis, manual selection, and batch processing.

There is no need to change Texture Group to UI. The preview does not rely
on changing texture pixels, material connections, LOD, or streaming settings.

UE5 贴图缩略图 Alpha 通道预览插件：解决内容浏览器中部分特效贴图显示为白色方块、
无法直接辨认透明轮廓的问题，支持 Alpha 灰度和 RGBA 棋盘格预览。

## Compatibility

- Released for Unreal Engine 5.8 / Windows 64-bit
- Editor plugin
- Other engine versions and platforms have not been verified

## Download

Download the plugin ZIP from [Releases](https://github.com/1finiteloop999/TextureAlphaPreview/releases).
Do not use GitHub's automatically generated Source code ZIP as the installation package.
## 解决什么问题？

部分特效贴图的 RGB 接近纯白，形状信息主要储存在 Alpha 通道中。
这类贴图在内容浏览器中可能显示成白色方块，不方便直接筛选。

本插件提供缩略图通道预览功能，减少逐张打开纹理编辑器检查的操作。

## 功能

- Alpha 通道预览。
- RGBA 与棋盘格背景预览。
- 自动分析并选择预览方式。
- 手动指定预览方式。
- 支持批量处理所选贴图。

自动分析属于辅助判断，不能保证适合所有贴图。
如果结果不符合需要，可以手动选择预览模式。

## 对原资产的影响

插件用于调整编辑器内的缩略图预览方式。

不需要为了显示缩略图而修改 Texture Group 为 UI，
也不以修改贴图像素、材质连接、LOD 或流送设置来实现预览。

## 当前发布环境

- 插件版本：0.1.4
- Unreal Engine：5.8
- 平台：Windows 64 位
- 类型：编辑器插件

其他 UE 版本和平台尚未验证。
即使版本接近，也可能因引擎构建不同而需要重新编译。

## 下载

请进入本仓库的 **Releases** 页面，下载：

`TextureAlphaPreview-0.1.4-UE5.8-Win64.zip`

不要把 GitHub 自动生成的 `Source code.zip` 当作插件安装包。

本次发布的插件 ZIP 包含编译文件和 Source 源码文件夹。

## 安装

1. 保存工作并关闭 Unreal Editor。
2. 下载并解压插件 ZIP。
3. 把解压后的 `TextureAlphaPreview` 文件夹放入项目的 `Plugins` 文件夹。
4. 如果项目中没有 `Plugins` 文件夹，可以手动创建。
5. 打开项目，在“编辑 → 插件”中搜索 `Texture Alpha Preview`。
6. 启用插件，如有提示则保存并重启编辑器。

正确的目录结构：

```text
你的项目/
├─ 你的项目.uproject
└─ Plugins/
   └─ TextureAlphaPreview/
      ├─ TextureAlphaPreview.uplugin
      ├─ Binaries/
      └─ Source/
```

请避免多嵌套一层版本号文件夹。

## 使用

1. 在内容浏览器中选择一张或多张纹理。
2. 右键打开插件的预览相关菜单。
3. 可先使用自动分析。
4. 如果显示不符合预期，手动选择 Alpha 或 RGBA 棋盘格等预览模式。

建议先选择少量贴图确认效果，再进行批量操作。

## 更新

1. 保存工作并关闭编辑器。
2. 将旧版插件文件夹移到项目外备份。
3. 放入新版插件文件夹。
4. 重新打开项目。

不要在同一项目中同时保留两个版本的插件。

## 卸载

1. 在“编辑 → 插件”中取消启用插件。
2. 保存工作并关闭编辑器。
3. 将 `Plugins/TextureAlphaPreview` 文件夹移出项目或删除。
4. 重新打开项目。

卸载不会删除贴图或材质。
插件预览功能停止后，缩略图会恢复为 UE 默认显示方式。

## 已知限制

- 自动分析可能判断不准确，可使用手动预览模式。
- 未验证所有纹理类型、UE 版本和平台。
- 插件不负责修复纹理本身的导入、压缩或材质透明度问题。

## 问题反馈

欢迎通过 Issues 反馈，请尽量提供：

- UE 完整版本号。
- 插件版本。
- 问题截图。
- 操作步骤。
- 预期显示效果与实际显示效果。
- 相关错误日志片段。

请勿上传无权公开的商业素材、完整项目或敏感信息。
