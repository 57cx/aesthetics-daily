# 审美日课 · 写作说明

后续每天只新增 **一篇** 文章，按 `_data/curriculum.yml` 的 `day` 从小到大，写 `published: false` 里最小的那一天。不要跳日，不要一次写多篇。

站点是 Jekyll，给 GitHub Pages 的 **Deploy from a branch: main / (root)** 用。`_config.yml` 里 `url` 是 `https://57cx.github.io`，`baseurl` 是 `/aesthetics-daily`。不要改这两项，除非仓库地址变了。不要添加 `.nojekyll`。不要添加 GitHub Actions 的 Pages 工作流。不要加入 GitHub Pages 白名单以外的插件。

## 文章固定结构

每篇都是这五段，标题用这几个字，顺序不要换：

1. **一句话讲清核心概念** — 正文最前面，用下面的 HTML，不要写成标题。
2. **图例讲解** — 用开放许可的原作把概念讲清楚。
3. **好与不好的对比** — 说明白为什么一边让眼睛能停，另一边让眼睛累。不嘲笑任何人的品味，不拿真人的家、衣服或作品出丑。
4. **小练习** — 当天能做完，不需要出门买材料。
5. **赏析练习** — 收在一幅图上，加 3 到 5 个观察问题。问题没有标准答案，正文里不要把答案先说完。

篇幅大约读 5 到 10 分钟。用口语中文，像把一幅画摊在桌上讲给零基础的人听。术语当页就解释，解释完可以告诉读者这个词不必背。

语气：具体，温和，诚实。可以说一张示意「看着累」，要说出累在哪里（没有地方停、每样东西一样大声）。不要说「品味差」「俗」。

## 头信息

文件放在 `_posts/YYYY-MM-DD-day-NN-英文短横线.md`。`NN` 是两位日序。日期用发布当天，并且不早于上一篇。

```yaml
---
layout: article
title: "与 curriculum.yml 里这一日的 title 完全一致"
description: "一两句，给首页和摘要用。不要和下面的「一句话」原文重复。"
date: 2026-11-13 09:00:00 +0800
day: 2
category: 基础理论
topic: 构图与比例
permalink: /days/02/
image: /assets/images/day-02/封面图.jpg
image_alt: "用一句话描述画面里看得见的东西，不要只写作品名。"
image_width: 1600
image_height: 1200
---
```

| 字段 | 要求 |
| --- | --- |
| `title` | 与 `_data/curriculum.yml` 该日 `title` 逐字一致 |
| `day` | 整数，与课表 `day` 一致 |
| `category` | 只能是：`基础理论`、`艺术史入门`、`生活美学`、`赏析练习`。与课表一致。Jekyll 会把它放进 `categories`，模板靠这个归档 |
| `topic` | 与课表 `topic` 一致 |
| `description` | 首页卡片用，一两句 |
| `permalink` | `/days/01/` 这种两位日序，必须写 |
| `image` | 首页用的封面，站内路径，以 `/assets/` 开头 |
| `date` | 带时区。不要写成未来日期 |

不要在头信息里写 `published: false`。文章是否发布，只改课表。

## 正文模板

图片地址用 `relative_url`，这样会带上 `/aesthetics-daily`。

```html
<p class="core"><span class="core-label">一句话</span>这里只放一句完整的话。</p>

## 图例讲解

<figure class="plate">
  <img src="{{ '/assets/images/day-02/作品.jpg' | relative_url }}" width="1600" height="1200" alt="看见什么就写什么。">
  <figcaption>
    <span class="cap-title">作者《作品名》</span>
    <span class="cap-meta">馆方标题原文。作者，年代。材质，尺寸。机构，藏品号，入藏说明。</span>
    <span class="cap-license"><a href="藏品页 URL">藏品页</a> · 许可：把藏品页上的原话概括清楚，并链到许可说明。</span>
  </figcaption>
</figure>

## 好与不好的对比

<div class="compare">
  <figure>
    <img src="{{ '/assets/images/day-02/compare-open.svg' | relative_url }}" width="800" height="800" alt="示意图在说什么。">
    <figcaption>
      <span class="label">这样更妥</span>
      一句话。
    </figcaption>
  </figure>
  <figure>
    <img src="{{ '/assets/images/day-02/compare-crowded.svg' | relative_url }}" width="800" height="800" alt="示意图在说什么。">
    <figcaption>
      <span class="label">这样发闷</span>
      一句话，只说眼睛为什么累。
    </figcaption>
  </figure>
</div>

<section class="practice">
  <h2>小练习</h2>
  <p>段落。</p>
</section>

## 赏析练习

<ol class="questions">
  <li>问题一</li>
  <li>问题二</li>
  <li>问题三</li>
</ol>

<p class="colophon">图从哪里下载、有没有裁切、哪些是本站示意图，用两三句写清楚。</p>
```

「这样更妥」的一边可以是真迹，也可以是本站示意图。「这样发闷」的一边用本站画的 SVG 或简图，不要找一件真作品来当反面教材。

前后日的链接由 `_layouts/article.html` 按 `day` 自动生成，正文里不用再写。

## 图片

每篇至少 **3** 张图。算进这三张的，是开放许可的摄影或馆藏图像。本站示意图可以另加，不代替这三张。

只允许：

- 公有领域（Public Domain）
- CC0

不使用 CC BY、CC BY-SA，也不使用「仅限非商业」的许可。艺术品本身年头够久，不等于照片可以随便用。必须是 **照片或扫描件** 的许可清楚。

可以找图的地方：

- The Met Open Access（藏品 `isPublicDomain: true`，再打开藏品页核对）
- Art Institute of Chicago（`is_public_domain: true`，藏品页核对）
- National Gallery of Art Open Access
- Cleveland Museum of Art Open Access（藏品页常写 Public Domain；开放获取计划写明 CC0）
- Rijksmuseum 开放数据（以藏品页为准）
- 台北故宫开放数据（以该条数据的许可原文为准）
- Wikimedia Commons 上标明 Public domain 或 CC0 的文件页

先打开 **藏品页或文件页**，读页面上的权利说明，再下载。说不清的就换一张。图注里写下你在页面上看到的许可，并给出链接。

每张图注都要有：作品名、作者、年代、机构、藏品页链接、许可。尺寸、材质、藏品号写得下就写。中文名如果是译者起的，要注明馆方原文标题。

文件：

- 放在 `assets/images/day-NN/`，`NN` 两位。
- 文件名用英文短横线，例如 `ma-yuan-watching-deer.jpg`。
- 下载原图后缩小：最长边不超过 1600 像素，JPEG 质量约 82，渐进式。SVG 示意图不用再压。
- 不要热链馆方地址。页面里的 `src` 指向本仓库。

缩小示例：

```python
from PIL import Image
im = Image.open("original.jpg").convert("RGB")
im.thumbnail((1600, 1600), Image.Resampling.LANCZOS)
im.save("assets/images/day-02/work.jpg", "JPEG", quality=82, optimize=True, progressive=True)
```

课表里的 `examples` 是计划，不是命令。若那件作品没有合法图像，保留这一日的概念和分类，换一件许可清楚的作品，改 `examples` 的文字，并在正文里用一句话说明换了什么。不要为了凑图使用来路不明的文件。

第一日用的三张图，2026-11-12 核对过克利夫兰艺术博物馆藏品页，页面写 Public Domain，并链到该馆 Open Access（CC0）：

- <https://www.clevelandart.org/art/1997.88>
- <https://www.clevelandart.org/art/1997.89>
- <https://www.clevelandart.org/art/1961.421.1>
- 开放获取说明：<https://www.clevelandart.org/open-access>

## 怎样把下一天标成已发布

假设下一天是第 2 日。

1. 打开 `_data/curriculum.yml`，找到 `published: false` 里 `day` 最小的一条。只写这一条。
2. 按上面的模板写 `_posts/当天日期-day-02-短名.md`，头信息与课表对齐。
3. 至少准备 3 张已核对许可的图，放进 `assets/images/day-02/`。
4. 文章能读、图注齐全之后，再把课表里这一日改成：

```yaml
published: true
date: 2026-11-13
```

`date` 与文章头信息是同一天。`title`、`category`、`topic` 不要在文章和课表里各写各的。

5. 不要提前把还没写完的日子标成 `published: true`。标了已发布却没有文章，课表会显示「待补文」。

## 本地构建

需要 Ruby 和 Bundler。`Gemfile` 里只有 `github-pages`，这样本地和 GitHub Pages 用同一套 Jekyll。

```bash
bundle install
bundle exec jekyll build
bundle exec jekyll serve
```

浏览器打开 <http://127.0.0.1:4000/aesthetics-daily/> 。

发布前看这几处：

- 首页最新一篇是刚写的，顺序是新的在前
- `/aesthetics-daily/days/NN/` 五段都在，图能打开，图注有藏品页和许可
- 对应的分类页「已经写好」里有这篇
- `/aesthetics-daily/curriculum/` 这一日是「已发布」，并且链到文章
- 手机宽度下没有横向滚动条，字号和行距还看得清

构建失败时，先看是不是头信息缩进、`permalink` 漏了，或图片路径没写成 `{{ '/assets/...' | relative_url }}`。
