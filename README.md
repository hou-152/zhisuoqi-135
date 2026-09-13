# 知所栖 135 · 公网快照

这是「知所栖 135」的**公网发布仓库**，只放构建产物，不放源文件。

- 线上地址：<https://hou-152.github.io/zhisuoqi-135/>（**09-13 两轮减法后**：只剩「知识体系 + 内参」两栏）
- 语义单元索引页：<https://hou-152.github.io/zhisuoqi-135/units.html>（538 个内容单元，可搜可筛，单文件）
- 源仓库：本地项目 `知乎黑客松/` → <https://github.com/hou-152/zhisuoqi-135-src>（2026-09-13 起公开；**不含** `.private/`）
- 生成方式：`node scripts/build-public.mjs`（源：`prototype/知所栖-壳.html`）· `node scripts/build-units-page.mjs`（源：`内容结构化系统/模块/ai-concept-base/data/`）
- 概念来源：Notion 概念库 509 + 飞书 Context Engineering 28 篇 + Harness Engineering 30 篇 + AI 内参 260912 期 10 篇 → 合并 1156 → AI 相关性过滤 856 → 并入内参 80 → **936**

## 这一版包含什么

单文件、零依赖、零服务端，双击或直开都能跑：

| 部分 | 内容 |
|---|---|
| 知识体系 | **936 个概念 / 531 条依赖**（203 实线 / 328 虚线），纵轴 = 依赖层级 L0–L5，横轴默认按功能分列（可切 21 条主题线或按来源）；图谱 / 星球两种视图 |
| 主题 | **21 条主题**；点一条只看这一列，再点「← 全部主题」回到全图 |
| 倒逼判定 | 概念卡里直接给复述输入框；公网没有模型时走**机械兜底**，只标 `mech`，**不冒充「过了」**，页面上写明「没经语义判定」 |
| 内参 | 260912 期 10 篇；四栏（三级笔记 / 概念网络 / 费曼 ×3 / 阅读原文）。概念网络里的 88 张概念卡**已 88/88 并进概念地图**，点名字直接跳到地图那张卡 |
| 语义单元索引（`units.html`） | **538 个内容单元**：问题 141 / 概念 76 / 观点 169 / 案例 76 / 方案 76。支持全文搜索、按类型与主题筛选、深链（`units.html#CON-context-rot`） |

## 09-13 减法删掉了什么

策展层 / 待你看一眼 / 我在学 / 对话 / 底部那条栏 / 左栏主题图例与状态点 **全部已删** —— 留白给队友接着做。
公网版因此**不再烘 skill 原文、不再有录制回放、没有 key 面板**（那些都随对话层一起走掉了）。

## 数据时效

概念地图、内参、语义单元索引全部是**构建时烘死的静态快照**，页面不会自己更新。

## 第三方内容

概念卡与语义单元复用自「Context × Harness 图鉴」的**已审计产物**（76 张概念卡 / 169 条关系 / 7 个分类轴），
按原样引用。若原作者要求移除，删掉对应部分即可。

## 更新方式

```sh
cd 知乎黑客松
node scripts/build-shell.mjs        # → prototype/知所栖-壳.html
node scripts/build-public.mjs       # → deploy/zhisuoqi-135/index.html
node scripts/build-units-page.mjs   # → deploy/zhisuoqi-135/units.html
node scripts/check-public.mjs       # 验收（本地静态；线上传 URL 参数）
node scripts/check-units-page.mjs   # 验收（语义单元索引页）
git -C deploy/zhisuoqi-135 push     # **改文件 ≠ 发布，线上要 push**
```
