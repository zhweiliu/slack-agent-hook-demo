# Claude Marketing Translation Demo

## 專案目的
這是一個多語言行銷文案翻譯 Demo 專案。
將繁體中文行銷文案自動翻譯成英文和日文，
經人工審批後發布到指定渠道。

## 工作流程
1. 讀取 `data/input/` 內的行銷文案
2. 查詢 Notion 歷史文案作為翻譯參考
3. 將文案翻譯成英文和日文
4. 透過 Slack 發送審批請求，等待 approve/reject
5. 審批通過後，發布到指定渠道

## 目錄結構
- `.claude/` — Claude Code 設定、hooks
- `tools/` — Custom tools（Notion 查詢、Slack 發送、渠道發布）
- `data/input/` — 待翻譯的原始行銷文案
- `data/storage/` — 本地暫存資料
- `src/` — Python 核心邏輯
- `output/pending/` — 等待審批的翻譯結果
- `output/approved/` — 已核准的文案
- `output/rejected/` — 已拒絕的文案

## 語言
- 來源語言：繁體中文
- 目標語言：英文、日文

## 渠道
- Slack（真實發送）
- LinkedIn（Mock）
- Instagram（Mock）
- Facebook（Mock）

## 重要規則
- 翻譯前必須先查詢 Notion 歷史文案
- 發布前必須經過人工審批（透過 Slack）
- 只接受第一個 approve 或 reject 指令
- 審批結果需標示在 Slack 訊息上
