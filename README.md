# 我的 AI 工具箱 · my-ai-toolbox

一个目录 + 一份资料大全 + 一个每日趋势看板，全部是静态文件，放在 GitHub Pages 上就能看。

- 目录页：`index.html`（打开 https://dyixia67-art.github.io/my-ai-toolbox/ 就是它）
- 每日趋势看板：`dashboard.html`
- 资料大全在线版：`tools.html`，原文：`AI软件资料大全.md`（快照 2026-11-17）
- 数据索引：`data/index.json`（只含摘要，不含全文）
- 目录配置：`data/catalog.json`
- 全文归档：`archive/ai/YYYY-MM-DD.md`（AI 日报，2026-10-18 起 30 期）、`archive/fund/YYYY-MM-DD.md`（基金早报，2026-09-26 起 45 期）

## 怎么加一个板块（不用改 HTML）

1. 在 `data/catalog.json` 的 `sections` 里加一条：`id`（如 `sec-13`）、`title`、`desc`、`target`（如 `tools.html#sec-13`）、`source`（源文件名）。
2. 在仓库里加对应的源文件：如果是资料大全里的一节，就在 `AI软件资料大全.md` 和 `tools.html` 里加一节；如果是独立内容，直接加一个 `.md` 文件，`target` 写它的文件名。
3. 提交到 main 分支，等 1-2 分钟，目录页自动出现新卡片。

## 每天怎么更新（定时任务）

- 08:15 基金早报推送后：把当天全文存为 `archive/fund/YYYY-MM-DD.md`，把摘要（信号文字、沪深300涨跌幅）追加进 `data/index.json`。
- 21:30 AI 日报推送后：把当天全文存为 `archive/ai/YYYY-MM-DD.md`，把摘要（一句话主线、新词标题）追加进 `data/index.json`。
- 每月 1 号上午：刷新 `AI软件资料大全.md` 和 `tools.html`（停产、涨价、新模型、新地区开放四类）。
- 推到 GitHub 后，目录和看板自动就是最新版，不用手动同步。

## 为什么看板不会越用越卡

看板页 `dashboard.html` 本身不到 200KB，打开时只加载 `data/index.json`（摘要索引）。
全文从来不塞进看板页：点日历上某一天，看板才用 `fetch()` 加载那一天的两个归档文件（`archive/fund/…` 和 `archive/ai/…`），看完就关。
搜索也只搜 `data/index.json`，不逐字翻所有归档文件。

## 数据口径（重要）

- 沪深300涨跌幅：只收录简报中明确给出、带正负号的指数值；ETF 代理价、午盘值、未核实值一律不收；周末报周五收盘、11-16 复用 11-14 旧值的情况一律略去。被略去的日期和原因见 `data/index.json` 的 `csi300_omitted`。
- 买卖信号：只按简报原文记录。🟢只在简报写明“新触发”时记为触发（全期一次，2026-10-22）；🔴因止盈目标与再平衡偏离上限待填，全期未触发；⚫全期未触发。
- 公开市场信息解读，不构成投资建议。

## 推送说明

推送方式不变：每天 08:15 基金早报、21:30 AI 日报照常发到 Muse（聊天里）。上面说的“同步到 GitHub”是同一份内容多存一份归档，方便随时在网页上回看，不影响聊天里的推送。
