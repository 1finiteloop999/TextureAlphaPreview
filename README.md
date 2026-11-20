# TextureAlphaPreview — UE5 Texture Alpha Thumbnail Preview

[中文](#中文) | [English](#english) | [下载 / Releases](https://github.com/1finiteloop999/TextureAlphaPreview/releases)

## 中文

### UE5 原生内容浏览器网格中的 Texture2D Alpha 预览

**直接在 UE5 原生内容浏览器的资产网格中，为现有 Texture2D 缩略图提供 Alpha 通道预览。** 支持 Alpha 灰度蒙版与 RGBA 棋盘格透明合成，便于辨认存储在 Alpha 通道中的纹理轮廓。支持批量切换预览模式，无需逐张打开纹理编辑器，也无需修改 Texture Group。

| 预览方式 | 用途 |
| --- | --- |
| Alpha 灰度 | 单独查看 Alpha 通道中的蒙版形状 |
| RGBA 棋盘格 | 同时查看贴图颜色与透明轮廓 |
| 自动分析 | 辅助选择预览方式；不合适时可手动指定 |

插件仅调整编辑器内的缩略图预览，不以修改贴图像素、材质连接、LOD 或流送设置来实现效果。

### 下载与兼容性

当前发布版本为 **0.1.5，UE 5.8 / Windows 64 位**。其他引擎版本和平台尚未验证，可能需要重新编译。

从 [Releases](https://github.com/1finiteloop999/TextureAlphaPreview/releases) 下载 `TextureAlphaPreview-0.1.5-UE5.8-Win64.zip`。插件包包含编译文件和 Source 源码文件夹；GitHub 自动生成的 `Source code.zip` 不是安装包。

在 0.1.4 中，重新打开项目后，设置过的缩略图可能又显示为 UE 默认预览。0.1.5 会读取当前项目保存在本机的预览选择，分批刷新缩略图。打开原贴图目录后可以直接查看，无需再次运行自动分析。升级时请保留项目的 `Saved/Config` 目录。

### 安装与使用

1. 保存工作并关闭 Unreal Editor。
2. 解压插件 ZIP，将 `TextureAlphaPreview` 文件夹放入项目的 `Plugins` 文件夹；没有该文件夹时可自行创建。
3. 打开项目，在“编辑 → 插件”中搜索 `Texture Alpha Preview`，启用并按提示重启。
4. 在内容浏览器中选择一张或多张贴图，通过右键菜单选择插件的 Alpha、RGBA 棋盘格或自动分析预览。

目录结构应为：

```text
你的项目/
├─ 你的项目.uproject
└─ Plugins/
   └─ TextureAlphaPreview/
      ├─ TextureAlphaPreview.uplugin
      ├─ Binaries/
      └─ Source/
```

避免多嵌套一层版本号文件夹。建议先用少量贴图确认效果，再批量处理。

### 常见问题与限制

**为什么默认缩略图无法呈现 Alpha 通道中的轮廓？**

当纹理形状主要存储在 Alpha 通道时，仅显示 RGB 的预览无法反映该蒙版。Alpha 灰度适合检查通道数据，RGBA 棋盘格适合查看透明合成效果。

**能修复贴图丢失 Alpha 或游戏中的材质不透明吗？**

不能。插件用于缩略图预览，不负责恢复缺失的通道数据或修复导入、压缩、材质透明度问题。自动分析可能判断不准确，所有纹理类型也尚未逐一验证。

### 更新、卸载与反馈

更新前保存并关闭编辑器，将旧插件文件夹移到项目外备份，再放入新版；不要在项目中同时保留两个版本。

卸载时先禁用插件并关闭编辑器，再移出插件文件夹。卸载不会删除贴图或材质，预览功能停止后缩略图恢复 UE 默认显示方式。

通过 [Issues](https://github.com/1finiteloop999/TextureAlphaPreview/issues) 反馈时，请提供 UE 完整版本、插件版本、复现步骤、预期与实际结果，以及必要的截图或日志。请勿上传无权公开的商业素材、完整项目或敏感信息。

## English

### Texture2D alpha previews in the native UE5 Content Browser grid

**Preview alpha channels directly in existing Texture2D thumbnails within the native UE5 Content Browser asset grid.** Supports Alpha grayscale masks, RGBA transparency over a checkerboard, and batch preview mode selection, without opening individual textures or changing their Texture Group.
This texture thumbnail preview plugin provides alpha preview modes for existing Texture2D assets directly in the native UE5 Content Browser grid.

| Preview mode | Use |
| --- | --- |
| Alpha grayscale | Inspect the mask stored in the alpha channel |
| RGBA checkerboard | View texture color with its transparent outline |
| Automatic analysis | Suggest a preview mode; override manually when needed |

The plugin changes editor thumbnail previews without modifying texture pixels, material connections, LOD, or streaming settings.

### Download and compatibility

The current release is **0.1.5 for UE 5.8 / Windows 64-bit**. Other engine versions and platforms have not been verified and may require recompilation.

Download `TextureAlphaPreview-0.1.5-UE5.8-Win64.zip` from [Releases](https://github.com/1finiteloop999/TextureAlphaPreview/releases). It includes compiled files and a Source folder. GitHub's automatically generated `Source code.zip` is not the installation package.

In 0.1.4, thumbnails could revert to the default UE preview when you reopened a project. Version 0.1.5 reads the preview modes saved locally for that project and refreshes the thumbnails in batches. Reopen the texture folder to see your previews without running automatic analysis again. Keep the project’s `Saved/Config` directory when upgrading.

### Installation and use

1. Save your work and close Unreal Editor.
2. Extract the plugin into `<YourProject>/Plugins/TextureAlphaPreview/`, with `TextureAlphaPreview.uplugin` directly inside that folder.
3. Open the project, enable **Texture Alpha Preview** in **Edit > Plugins**, and restart if prompted.
4. Select one or more textures in the Content Browser. Use the plugin's right-click preview menu to choose Alpha, RGBA checkerboard, or automatic analysis.

Try a few textures before applying a mode in bulk. Avoid nesting the plugin inside an extra version-number folder.

### Questions and limitations

**Why does the default thumbnail not show the shape stored in alpha?**

When a texture stores its shape in the alpha channel, an RGB-only preview does not represent that mask. Alpha grayscale displays the channel data; RGBA checkerboard displays color composited with transparency.

**Does this fix missing alpha data or opaque materials in the game?**

No. This is a thumbnail preview tool. Import, compression, and material transparency issues must be addressed separately. Automatic analysis can choose an unsuitable mode, and not all texture types have been verified.

### Updating, removal, and support

Before updating, close the editor and move the old plugin folder outside the project as a backup. Install the new version without keeping two copies inside the project.

To remove it, disable the plugin, close the editor, and move its folder out of the project. Textures and materials are retained; thumbnails return to UE's default display when the preview functionality stops.

Report problems through [Issues](https://github.com/1finiteloop999/TextureAlphaPreview/issues), including the full UE version, plugin version, reproduction steps, expected and actual results, and relevant screenshots or logs. Do not upload private projects, sensitive information, or assets you cannot share.
