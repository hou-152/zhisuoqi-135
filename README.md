# 知所栖 135 · 公网快照

这是「知所栖 135」的**公网发布仓库**，只放构建产物，不放源文件。

- 线上地址：<https://hou-152.github.io/zhisuoqi-135/>
- 源仓库：本地项目 `知乎黑客松/`（**不含** `.private/`，且未推公开）
- 生成方式：`node scripts/build-public.mjs`（源：`prototype/知所栖-壳.html`）
- 概念来源：用户 Notion 概念库 509 + 飞书 Context Engineering 28 篇 + Harness Engineering 30 篇 + AI 内参 260912 期 10 篇 → 合并 1156 → AI 相关性过滤 856 → 并入内参 80 → **936**

## 这一版包含什么

单文件、零依赖、零服务端，双击或直开都能跑：

| 部分 | 内容 |
|---|---|
| 概念图 | **936 个概念 / 531 条依赖**（骨架 203 实线 / 328 虚线），纵轴 = 依赖层级 L0–L5，横轴默认**按功能分列**（可切按 21 条主题线或按来源） |
| 策展层 | **21 条主题线**，每条带「为什么值得走」+ 入口（组内无前置且解锁最多）+ 沿真实依赖边的路线 + 收敛点 |
| 待你看一眼 | 依赖边**逐条过过审核**：机器已判 251 条，留 43 条给人看 |
| 两棵树 | 全量树 / 自己的树（自己的标记只存访问者本机 localStorage） |
| Agent | **15 个已装 skill** 的清单；其中 `dbs-learning-beta` 与 `dbs-standard-answer` 带完整 SKILL.md 原文 |
| 内参 | 260912 期 10 篇；四栏（三级笔记 / 概念网络 / 费曼 ×3 / 阅读原文）。**概念网络里的 88 张概念卡已 88/88 并进概念图**，点名字直接跳到地图那张卡 |
| 星球 | 球面均布视图 |

## 对话有三条路（页面自己按顺序试）

1. **本地服务端** —— 只有在 `127.0.0.1` / `localhost` 下才会去问 `/api/health`（公网地址下不探，避免 404 噪音）。
2. **访客自带 DeepSeek key** —— 浏览器直连 `api.deepseek.com`。key **只写进访客自己浏览器的 localStorage**，本站不上传、不记录、不在任何地方落盘。
3. **录制回放** —— 两样都没有时，播 2026-09-12 用真模型跑同一个 skill 录下来的对话，并在气泡上**明说这不是对本次提问的回答**。

## 数据时效

概念、依赖边、主题标签、边预判、录制回放全部**烘死于 2026-09-12**，是静态快照，不会自己更新。

## 第三方内容

`dbs-learning-beta` 与 `dbs-standard-answer` 的 SKILL.md 原文来自 **dontbesilent 的 dbskill**，按原样引用，仅用于让访客看到「真 skill 被真调用」这件事。若原作者要求移除，删掉本仓库即可。

## 更新方式

```sh
cd 知乎黑客松
node scripts/curate-concepts.mjs   # 策展（有缓存，改判据不重烧 token）
node scripts/curate-edges.mjs      # 边预判
node scripts/build-shell.mjs       # 壳
node scripts/record-replays.mjs    # 录制回放（需本地 serve 与 .private/llm.env）
node scripts/build-public.mjs      # → deploy/zhisuoqi-135/index.html
node scripts/check-public.mjs      # 验收
```
