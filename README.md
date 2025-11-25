# Custom Header Links

一个 Discourse 主题组件，允许您在论坛头部添加自定义链接。

## 功能特性

- ✅ 在 Discourse 头部添加自定义链接
- ✅ 支持链接位置配置（左侧或右侧）
- ✅ 支持设备视图过滤（桌面/移动端）
- ✅ 支持多语言链接（根据用户语言显示）
- ✅ 支持滚动时隐藏链接
- ✅ 支持链接打开方式（新窗口/当前窗口）
- ✅ 与 discourse-header-search 组件兼容

## 安装

1. 在 Discourse 管理后台，进入 **自定义** → **主题**
2. 点击 **导入** 按钮
3. 输入此仓库的 URL 或上传主题文件
4. 将组件添加到您的主题中

## 配置

### 链接位置

- **right**（默认）：链接显示在头部右侧
- **left**：链接显示在头部左侧

### 链接配置

每个链接支持以下配置项：

| 配置项 | 类型 | 必填 | 说明 |
|--------|------|------|------|
| `text` | string | 是 | 链接显示文本（1-100 字符） |
| `url` | string | 是 | 链接地址（1-2048 字符，必须是有效 URL） |
| `title` | string | 否 | 链接标题提示（1-1000 字符） |
| `view` | enum | 否 | 设备视图：`vdm`（桌面和移动端）、`vdo`（仅桌面）、`vmo`（仅移动端） |
| `target` | enum | 否 | 打开方式：`blank`（新窗口）、`self`（当前窗口） |
| `hide_on_scroll` | enum | 否 | 滚动时行为：`remove`（隐藏）、`keep`（保持显示），默认为 `keep` |
| `locale` | string | 否 | 语言代码，仅在该语言下显示此链接 |

### 配置示例

```yaml
custom_header_links:
  - text: "帮助中心"
    url: "https://example.com/help"
    title: "访问帮助中心"
    view: "vdm"
    target: "blank"
    hide_on_scroll: "keep"
  - text: "联系我们"
    url: "https://example.com/contact"
    view: "vdo"
    target: "self"
    locale: "zh_CN"
```

## 开发

### 环境要求

- Node.js >= 22
- pnpm 9.x

### 安装依赖

```bash
pnpm install
```

### 代码规范

项目使用以下工具进行代码检查：

- ESLint
- Prettier
- Stylelint
- Ember Template Lint
- RuboCop

## 许可证

MIT License

Copyright (c) Civilized Discourse Construction Kit, Inc.

## 相关链接

- [Discourse 官方讨论帖](https://meta.discourse.org/t/custom-header-links/90588)
- [许可证文件](LICENSE)
