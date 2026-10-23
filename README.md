# 控制大综合

**控制理论从数学基础到工程落地的 116 章**（前言 + 正文 + 结语），网页版与 PDF 同源。

> 每一章都回答四件事：这个方法需要什么信息、参数往哪个方向调、什么时候会失效、失效时怎么降级。

## 在线阅读

**https://dingjq1216.github.io/control-theory-comprehensive/**

首页是总目录，按十个部分分组，支持按章号或标题关键词过滤；任意一章的页头页尾都有「上一章 / 下一章 / 返回目录」，不需要反复打开文件。

- 前言：<https://dingjq1216.github.io/control-theory-comprehensive/preface.html>
- 从第 0 章开始：<https://dingjq1216.github.io/control-theory-comprehensive/ch000.html>
- 结语：<https://dingjq1216.github.io/control-theory-comprehensive/conclusion.html>
- 全书 PDF：<https://dingjq1216.github.io/control-theory-comprehensive/#pdf>

## 规模

| 项目 | 数量 |
| --- | --- |
| 章 | 116（第 0–115 章） |
| 部分 | 10 |
| 字数 | 约 366.8 万 |
| 编号公式 | 3,669 |
| 插图 | 993（SVG，随仓库分发） |
| PDF | 12 册，合计约 175 MB、约 4,800 页 |

## 内容结构

| 部分 | 主题 | 章 |
| --- | --- | --- |
| 第零部分 | 数学与信号基础 | 0–14 |
| 第一部分 | 建模、辨识与学习基础 | 15–36 |
| 第二部分 | 经典控制 | 37–50 |
| 第三部分 | 现代控制 | 51–65 |
| 第四部分 | 智能控制 | 66–72 |
| 第五部分 | 前沿控制 | 73–83 |
| 第六部分 | 计算机控制 | 84–93 |
| 第七部分 | 运动控制 | 94–103 |
| 第八部分 | 过程控制 | 104–113 |
| 第九部分 | 总结 | 114–115 |

## PDF 分册

单本合订约 380 MB，超过 GitHub 100 MB 的单文件上限，因此按 12 章一册切分，每册开头带本册目录：

| 文件 | 内容 | 体积 |
| --- | --- | --- |
| `pdf/00-preface.pdf` | 前言 | 0.4 MB |
| `pdf/01-ch000-011.pdf` | 第 0–11 章 | 12.1 MB |
| `pdf/02-ch012-023.pdf` | 第 12–23 章 | 14.5 MB |
| `pdf/03-ch024-035.pdf` | 第 24–35 章 | 14.5 MB |
| `pdf/04-ch036-047.pdf` | 第 36–47 章 | 21.1 MB |
| `pdf/05-ch048-059.pdf` | 第 48–59 章 | 21.4 MB |
| `pdf/06-ch060-071.pdf` | 第 60–71 章 | 22.1 MB |
| `pdf/07-ch072-083.pdf` | 第 72–83 章 | 18.7 MB |
| `pdf/08-ch084-095.pdf` | 第 84–95 章 | 15.7 MB |
| `pdf/09-ch096-107.pdf` | 第 96–107 章 | 22.6 MB |
| `pdf/10-ch108-115.pdf` | 第 108–115 章 | 11.6 MB |
| `pdf/11-conclusion.pdf` | 结语 | 0.4 MB |

## 网页版说明

- **纯静态**：无后端、无数据库，克隆下来直接双击 `index.html` 也能读。
- **离线可用**：KaTeX 及其字体、全部插图都在仓库内，不依赖任何 CDN，断网也能正常显示公式与图。
- **相对路径**：站点部署在 `/{仓库名}/` 子路径下，所有链接与资源均用相对路径，换仓库名或换托管平台都不需要改页面。
- **同源**：网页与 PDF 由同一份 Markdown 经 pandoc 渲染，公式编号、图号、表号与正文一致。

## 目录结构

```
.
├── index.html            总目录（十个部分分组 + 搜索 + PDF 列表）
├── preface.html          前言
├── ch000.html … ch115.html
├── conclusion.html       结语
├── pdf/                  12 册 PDF
├── figs/chNNN/*.svg      正文插图
├── assets/
│   ├── book.css          正文版式（网页与 PDF 共用）
│   ├── site.css          站点层样式（导航、目录页）
│   └── katex/            KaTeX 运行库与字体
└── .nojekyll             关闭 Jekyll，避免下划线开头的文件被忽略
```

## 本地构建

网页与 PDF 由 `book/tools/site.py` 一次生成（在书的源目录 `book/` 下运行）：

```powershell
# 完整构建：生成网页 + 12 册 PDF
D:\Anaconda3\envs\py311\python.exe tools\site.py

# 只更新网页，复用已有 PDF
D:\Anaconda3\envs\py311\python.exe tools\site.py --no-pdf

# 只重打 PDF
D:\Anaconda3\envs\py311\python.exe tools\site.py --pdf-only
```

依赖：Python 3.11、pandoc、Microsoft Edge（headless 打印 PDF）。

## Pages 发布方式

- 发布源：分支 `main`、目录 `/`（仓库根即站点根）
- 因为是根目录发布，`index.html` 必须在仓库根，不能放进子目录
- 根目录放 `.nojekyll`，避免 Jekyll 处理 KaTeX 资源与下划线开头的文件

## 引用与联系

仓库未附开源许可证。如需引用书中结论、图表或整段文字，请注明出处并先联系作者。
