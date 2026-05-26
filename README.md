# Obsidian Web-App Guideline Wiki

這個 vault 用來建立一套由 AI 長期維護的 Obsidian wiki，主題是 `web-app guideline`。

核心想法來自 `LLM-wiki.md`：不要只把資料丟給 AI 臨時查詢，而是讓 AI 把原始資料逐步整理成一個持續累積、互相連結、可維護的 markdown wiki。

## 檔案角色

- `LLM-wiki.md`：原始理念文件，說明 LLM Wiki 的設計模式。
- `AGENTS.md`：給 AI agent 看的操作規範，定義如何初始化、維護、更新這個 wiki。
- `README.md`：給人看的入門說明，也就是你現在正在讀的文件。
- `raw/sources/`：原始資料，作為 source of truth。
- `raw/assets/`：圖片、附件與媒體檔。
- `wiki/index.md`：wiki 內容索引。
- `wiki/log.md`：wiki 維護日誌。
- `wiki/topics/`：web app guideline 的主題頁。
- `wiki/entities/`：專案、工具、服務、系統、團隊或專有名詞等實體頁。
- `wiki/sources/`：AI 撰寫的來源摘要。
- `wiki/syntheses/`：跨來源整理、決策、比較與耐久問答。
- `templates/`：AI 維護 wiki 時使用的頁面模板。

## 本 vault 的設定

- 目的與領域：web-app guideline。
- 範圍：開發與維護、版本控制、部署流程、專案術語，以及可長期沉澱的 web app 實務準則。
- wiki 語言：繁體中文。
- 維護方式：每次 ingest 先產生摘要與預計更新內容，經確認後再寫入 wiki。

## 新手怎麼開始

把下面這段話貼給你的 AI agent：

```text
請先閱讀本 vault 的 `LLM-wiki.md` 與 `AGENTS.md`。

我想建立一個由 AI 長期維護的 Obsidian wiki。請先詢問我這個 wiki 的目的、領域、資料來源類型、偏好的語言與維護方式，然後依照 `AGENTS.md` 幫我初始化 wiki 架構。
```

如果你還不知道怎麼描述目的，可以這樣回答 AI：

```text
這個 wiki 的目的：我想建立一個由 AI 維護的 Obsidian 知識庫，用來整理「請填入你的主題」。資料來源可能包含文章、網頁、PDF、影片筆記和我自己的想法。請用繁體中文建立架構，並讓未來的 AI 能持續 ingest、整理、交叉連結與維護。
```

## 使用流程

1. 先保留 `LLM-wiki.md`，它是 AI 理解整體模式的原文。
2. 讓 AI 依照 `AGENTS.md` 維護 wiki 架構。
3. 之後新增資料時，把原始資料放進 `raw/sources/`，附件放進 `raw/assets/`，再請 AI 執行 ingest。
4. ingest 時，AI 應先產生摘要與預計更新內容，等你確認後才寫入 wiki。
5. 問 AI 問題時，可以要求它把有價值的答案寫回 `wiki/syntheses/`。
6. 定期請 AI 執行 lint，檢查孤立頁、矛盾資訊、缺少索引、缺少連結等問題。

## 什麼時候更新 AGENTS.md

`AGENTS.md` 不是一次性文件。當你發現 wiki 的分類、命名、頁面格式或工作流程需要改進時，請 AI 同步更新 `AGENTS.md`，讓未來的 AI agent 繼續沿用新的規則。
