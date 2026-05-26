---
type: entity
status: active
language: zh-TW
entity_type: project
created: 2026-05-26
updated: 2026-05-26
source_count: 1
---

# web-app

## Overview

`web-app` 是此 wiki 中主要討論的 web application 專案之一。它會使用 [[web-common]] 的共用元件，並在 `web-app/modules/components` 中保存可多頁複用的 ui layer component。

## Role In This Wiki

- 使用 [[web-common]] 提供的 `base component`。
- 在 `web-app/modules/components` 中提供 [[Component 分層與共用策略|ui layer component]]。
- 是 [[CSS 模組與 SCSS 遷移]] 中需要與 [[web-common]] 使用相同 CSS 套件的專案。

## Related Guidelines

- 開發 component 時，若 [[web-common]] 沒有合適元件，應再查 `web-app/modules/components`。
- 若元件不需要通用，可寫在當頁畫面直接使用。
- CSS 可與 component 共置，例如 `Button.js` 搭配 `Button.module.scss`。

## Related Sources

- [[開發與維護 Summary]]

## Related Topics

- [[Component 分層與共用策略]]
- [[CSS 模組與 SCSS 遷移]]

## Open Questions

- `web-app/modules/components` 中哪些 component 已被視為正式可複用，目前尚未有清單。
- 當頁專用 component 何時應提升為 ui layer component，仍待補充準則。
