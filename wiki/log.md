---
type: log
language: zh-TW
domain: web-app guideline
aliases:
  - Wiki Log
created: 2026-05-26
updated: 2026-05-26
---

# Wiki Log

本檔案為 append-only 的維護紀錄。重大變更、來源 ingest、耐久問答歸檔與 lint 結果都應記錄於此。

## [2026-05-26] ingest | 開發與維護

- Added: [[開發與維護 Summary]]
- Added: [[Component 分層與共用策略]], [[CSS 模組與 SCSS 遷移]]
- Added: [[web-common]], [[web-app]], [[web-front]]
- Updated: [[index|Wiki Index]]
- Notes: 來源為 Ray、Vincent、Joe 關於 component 分層、共用元件查找順序、Storybook 與 CSS 技術方向的討論。原始日期格式 `2026-0526 15:21:34 CST` 已於摘要中正規化為 2026-05-26；`web-front` 目前僅知道是 `web-common` 的使用專案之一。

## [2026-05-26] structure | 初始化 web-app guideline wiki

- Added: [[index|Wiki Index]], [[log|Wiki Log]]
- Added folders: `raw/sources/`, `raw/assets/`, `wiki/topics/`, `wiki/entities/`, `wiki/sources/`, `wiki/syntheses/`, `templates/`
- Added templates: `source-summary.md`, `topic.md`, `entity.md`, `synthesis.md`
- Updated: `AGENTS.md`, `README.md`, `歡迎.md`
- Notes: 使用者指定 wiki 目的為 web-app guideline；範圍包含開發與維護、版本控制、部署流程、專案術語；頁面語言為繁體中文；未來 ingest 必須先產生摘要並等待使用者確認後再寫入 wiki。
