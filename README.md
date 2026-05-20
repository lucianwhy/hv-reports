# hv-reports

`hv-reports` 是一个公开托管仓库，作用有两层：

1. 放横纵分析法研究报告的静态网页成品  
2. 放生成这些报告时使用的 `hv-analysis` skill

仓库地址：  
[https://github.com/lucian-why/hv-reports](https://github.com/lucian-why/hv-reports)

报告站点地址：  
[https://lucian-why.github.io/hv-reports/](https://lucian-why.github.io/hv-reports/)

## 仓库结构

```text
hv-reports/
├─ index.html                  # 报告首页
├─ reports.json                # 报告索引
├─ hyperliquid/                # 单篇报告页面
├─ brain-computer-interface/   # 单篇报告页面
└─ skills/
   └─ hv-analysis/
      └─ SKILL.md              # 横纵分析法 skill
```

## 这个仓库是干什么的

这个仓库不是普通博客仓库，也不是单纯的技能仓库。

它更像一个“研究成品 + 研究方法”放在一起的公开归档点：

- `reports/` 这一层的内容，解决“研究结果怎么展示、怎么分享”
- `skills/hv-analysis/` 这一层的内容，解决“这种研究报告是怎么稳定生成出来的”

也就是说，别人既可以直接读报告，也可以把 `hv-analysis` skill 拿走，自己继续产出同风格、同结构的研究网页。

## hv-analysis skill 是什么

`hv-analysis` 是“横纵分析法”深度研究 skill。

它的作用：

- 遇到产品、公司、概念、技术、人物等研究对象时，要求先做纵向历史梳理
- 再做横向竞品/同类比较
- 最后把两条轴交叉，得出判断和洞察
- 最终产出单文件、可直接部署的 HTML 研究报告

它不仅管“写什么”，也管“怎么排版”。

当前 skill 已经包含这些前端展示规则：

- 封面必须是首屏主视觉
- 正文必须始终居中
- 目录不能挤占正文流
- 目录优先做成正文左上角悬浮小按钮，点击后展开
- 页面需要适配桌面和移动端

## hv-analysis skill 在哪里

GitHub 页面地址：  
[https://github.com/lucian-why/hv-reports/tree/main/skills/hv-analysis](https://github.com/lucian-why/hv-reports/tree/main/skills/hv-analysis)

直接下载地址（Raw）：  
[https://raw.githubusercontent.com/lucian-why/hv-reports/main/skills/hv-analysis/SKILL.md](https://raw.githubusercontent.com/lucian-why/hv-reports/main/skills/hv-analysis/SKILL.md)

## 怎么下载这个 skill

因为这个 skill 目前只有一个 `SKILL.md` 文件，所以最直接的拿法有两种。

### 方式 1：直接下载单文件

打开 Raw 地址后保存为 `SKILL.md`：

`https://raw.githubusercontent.com/lucian-why/hv-reports/main/skills/hv-analysis/SKILL.md`

然后放到你本地的 skill 目录里，比如：

- Codex 常见个人 skill 目录：`~/.agents/skills/hv-analysis/SKILL.md`
- 如果你在别的 agent 环境，也可以放进该环境约定的 skill 目录

### 方式 2：克隆整个仓库

```bash
git clone https://github.com/lucian-why/hv-reports.git
```

克隆后 skill 路径在：

```text
hv-reports/skills/hv-analysis/SKILL.md
```

这种方式适合两类人：

- 既想拿 skill，也想顺手看现成报告样式
- 想直接复用这个仓库作为 GitHub Pages 报告站的人

## 怎么使用这个 skill

把 `SKILL.md` 放进你的 agent skill 目录后，就可以在需要时显式调用 `hv-analysis`。

典型用途：

- “研究一下 Hyperliquid”
- “帮我横纵分析一下某家公司”
- “做个某技术方向的深度研究”
- “把研究结果输出成可分享 HTML 报告”

适用对象：

- 产品
- 公司
- 技术
- 概念
- 人物

不适用对象：

- 简单名词解释
- 只要一句话摘要
- 普通资讯快讯改写

## 这个仓库和这个 skill 的关系

一句话讲清：

这个仓库负责“公开托管成果”，这个 skill 负责“稳定生产成果”。

两者合起来，形成一个完整链路：

1. 用 `hv-analysis` 做研究
2. 生成单文件 HTML 报告
3. 发布到 `hv-reports`
4. 通过 GitHub Pages 对外分享

## 发布新报告怎么部署

`hv-analysis` 产出 HTML 后，如果用户明确同意部署，默认发布到这个固定仓库，不要再猜目标地址：

- GitHub 仓库：`https://github.com/lucian-why/hv-reports`
- Clone 地址：`https://github.com/lucian-why/hv-reports.git`
- Pages 首页：`https://lucian-why.github.io/hv-reports/`
- 单篇报告 URL 模板：`https://lucian-why.github.io/hv-reports/<slug>/`

### 标准发布步骤

1. 在本地 `hv-reports` 工作副本中创建报告目录：`<slug>/`
2. 将报告 HTML 放到：`<slug>/index.html`
3. 更新根目录 `reports.json`
4. 若这次也修改了 `hv-analysis` 规则，同步更新 `skills/hv-analysis/SKILL.md`
5. 若仓库使用说明受影响，同步更新本 README
6. `git add` 只添加本次相关文件
7. 提交并推送到 `origin/main`
8. 返回三个链接：
   - 仓库地址
   - Pages 首页
   - 单篇报告链接

### 提交范围原则

- 不要覆盖或回滚仓库里无关的未提交改动
- 发布普通新报告时，最小变更集通常只有：
  - `reports.json`
  - `<slug>/index.html`
- 只有在方法论或部署规范变化时，才额外更新：
  - `skills/hv-analysis/SKILL.md`
  - `README.md`

## 适合谁用

适合这些场景：

- 想长期积累研究报告的人
- 想把研究写成网页、方便分享的人
- 想复用“纵向历史 + 横向比较 + HTML 交付”方法论的人
- 想把 agent 研究工作流沉淀成可复用 skill 的人

## License / 使用说明

当前仓库主要用于公开归档与方法沉淀。

如果你只是个人研究、个人复用，直接拿来改通常没问题。  
如果后面要补更正式的授权方式，可以再单独加 `LICENSE` 文件。
