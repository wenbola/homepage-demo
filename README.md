# 个人主页项目

一个静态个人主页及其配套的前端练习页面，纯 HTML / CSS / JavaScript 实现，无构建步骤、无第三方依赖，用浏览器直接打开即可。

主页主人：**陈文斌**（复旦大学 · 金融硕士在读）

## 文件说明

| 文件 | 说明 |
|---|---|
| `index.html` | **个人主页**。含头像、个人简介、兴趣方向、技能标签、联系方式五个板块。配色为深蓝 + 浅灰，跟随系统自动切换深色模式，支持响应式布局。 |
| `dynamic.html` | Canvas 交互演示页。鼠标移动产生彩色发光粒子拖尾，点击从点击位置爆发一圈粒子，中央文字随鼠标轻微倾斜；进场先显示「你好」欢迎词。 |
| `hello.py` | 最基础的 Python 脚本，打印一行问候语，用于验证运行环境。 |
| `news.md` | 记录的一条新闻，测试用。 |

## 使用方法

**个人主页**：双击 `index.html`，或用浏览器打开：

```bash
start index.html        # Windows
```

**交互演示页**：同样直接打开，移动鼠标和点击即可看到效果：

```bash
start dynamic.html
```

**Python 脚本**：需要 Python 3。

```bash
python hello.py
# 输出：Hello from Claude Code
```

## 技术说明

- 全部为静态单文件页面，无需安装依赖或启动本地服务器
- `index.html` 使用 CSS 变量统一管理配色，通过 `prefers-color-scheme` 媒体查询适配深色模式
- `dynamic.html` 用 Canvas 2D 实现粒子系统：预渲染辉光精灵图代替 `shadowBlur`（后者在粒子数量大时严重掉帧），配合固定容量粒子池与环形复用，避免运行期内存分配；发光效果由 `globalCompositeOperation = 'lighter'` 叠加实现

## 环境要求

- 现代浏览器（Chrome / Edge / Firefox / Safari 均可）
- 仅运行 `hello.py` 时需要 Python 3
