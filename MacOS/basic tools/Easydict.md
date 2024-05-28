# Easydict

`Easydict` 是一个开箱即用的聚合翻译软件，能自动识别输入文本语言，支持输入翻译，划词翻译和 OCR 截图翻译。

![](./assets/image-20240523120910663.png)

## 安装

- 手动下载安装：[下载](https://github.com/tisfeng/Easydict/releases) 最新版本的 Easydict。

- Homebrew 安装

```
brew install --cask easydict
```

## 使用

- 鼠标划词翻译：点击图标
- 快捷键划词翻译：选中后，`⌥ + D`
- 截图翻译：`⌥ + S`
- 输入翻译：唤出查词窗口， `⌥ + A` 
- 静默截图 OCR： `⌥ + ⇧ + S`，截图 OCR 并自动保存到剪贴板



## 配合 PopClip 使用

### 安装 PopClip 插件

> 你需要先安装 [PopClip](https://pilotmoon.com/popclip/)，然后选中以下代码块，`PopClip` 会显示 "安装扩展 Easydict"，点击它即可。

```
-- #popclip
-- name: Easydict
-- icon: iconify:ri:translate
-- language: applescript
tell application "Easydict"
  launch
  open location "easydict://query?text={popclip text}"
end tell
```

### 使用

PopClip 中配置插件启用后，选中文字跳出图标后，点击即可。