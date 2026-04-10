---
name: check-resume
description: 检查简历 Markdown 文件的格式问题，包括空格、标点、专有名词、篇幅、排版等
disable-model-invocation: true
argument-hint: [file]
---

检查简历文件 $ARGUMENTS（默认为 resume.md）的格式问题，逐项列出问题并给出修复建议，最后询问用户是否需要自动修复。

## 检查项

### 1. 专有名词大小写

技术术语必须使用官方大小写，常见易错项：

- `GitHub`（不是 Github / github）
- `JavaScript`（不是 Javascript / javascript）
- `TypeScript`（不是 Typescript / typescript）
- `Node.js`（不是 NodeJS / node.js / nodejs）
- `Vue.js`（不是 VueJS / vue.js）
- `Next.js`（不是 NextJS / next.js）
- `React Native`（不是 react native / ReactNative）
- `MobX`（不是 Mobx / mobx）
- `VSCode` 或 `VS Code`（不是 vscode）
- `Claude`（不是 claude）
- `macOS`（不是 MacOS / macos）
- `iOS`（不是 IOS / ios）
- `Android`（不是 android）
- `CSS`（不是 css）
- `HTML`（不是 html）
- `SSR`（不是 ssr）
- `PWA`（不是 pwa）
- `CI/CD`（不是 ci/cd）
- `Tailwind CSS`（不是 tailwind css）
- `shadcn/ui`（不是 Shadcn / ShadCN）
- `Zustand`（不是 zustand）
- `Jenkins`（不是 jenkins）
- `GitLab`（不是 Gitlab / gitlab）
- `Monorepo`（不是 monorepo，用于句首或标题时）
- `pnpm`（全小写，不是 PNPM）
- `npm`（全小写，不是 NPM）
- `Webpack`（不是 webpack，用于句首或标题时）
- `Sass`（不是 SASS / sass）
- `MySQL`（不是 mysql / MYSQL / Mysql）
- `Xcode`（不是 xcode / XCode）
- `App Store`（不是 app store / AppStore）
- `Java`（不是 JAVA / java）
- `LCP` / `FCP`（大写缩写）
- `AJAX`（不是 Ajax / ajax，注意 AJAX 是技术而非"语言"）

### 2. 中英文之间的空格

中文和英文、中文和数字之间应有一个空格，例如：

- ✅ `6 年前端开发经验`
- ❌ `6年前端开发经验`
- ✅ `基于 Next.js 实现 SSR`
- ❌ `基于Next.js实现SSR`

### 3. 单位规范

- 文件大小单位使用大写：`KB`、`MB`、`GB`（不是 kb、mb、gb）
- 数字和单位之间应有空格：`2.3 MB`（不是 `2.3MB`）

### 4. 标点符号一致性

- 技术栈分隔符（斜体行中的 `|`）应统一使用半角 `|`，不要混用全角 `｜`
- 中文内容使用中文标点（句号、逗号、顿号等）
- 检查是否有中英文标点混用的情况

### 5. 空行规范

- 各级标题前后应有且仅有一个空行
- 不应出现连续两个及以上的空行（注释块内除外）

### 6. 日期格式统一

- 全文只使用一种日期格式，保持统一（如统一用 `2024.06` 或 `2024/06` 或 `2024-06`）
- 日期范围分隔符统一（如 `2024.06 - 2025.09`）

### 7. 篇幅与排版

- 简历正文内容（不含注释）以 1-2 页为佳，不超过 3 页
- 避免大幅空白区域
- 列表项缩进一致
- 标题层级合理

### 8. Markdown 格式

- 加粗语法 `**text**` 前后与中文之间不需要空格（Markdown 渲染会自动处理）
- 链接格式正确，URL 可访问
- 标题层级合理递进

## 输出格式

按检查项分类列出发现的问题，格式如下：

```
### 检查结果

**专有名词大小写**
- 第 X 行：`错误写法` → `正确写法`

**中英文空格**
- 第 X 行：`问题文本` → `修正文本`

...

共发现 N 个问题。是否需要自动修复？
```

如果没有发现问题，输出：`✅ 未发现格式问题。`
