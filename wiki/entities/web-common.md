---
type: entity
status: active
language: zh-TW
entity_type: project
created: 2026-05-26
updated: 2026-05-26
source_count: 1
---

# web-common

## Overview

`web-common` 是此 wiki 中的共用元件來源，主要承載 `base component`。開發者在建立新 component 前，應先查 `web-common` 是否已有可用的共用元件。

## Role In This Wiki

- 提供 [[Component 分層與共用策略]] 中的 `base component`。
- 透過 Storybook 作為人可讀的共用元件文件。
- 是 [[web-app]] 與 [[web-front]] 會使用到的共用層。
- 目前開發流程是先建立 `js + css`，再由 AI 產生 Storybook。

## Related Guidelines

- 新增元件時，先查 `web-common` 是否已有共用元件。
- 若元件可能共用，可與 UI 討論是否沿用 `web-common` 既有設計以增加共用性。
- CSS 技術方向應與 [[web-app]] 對齊，朝 [[CSS 模組與 SCSS 遷移|scss]] 收斂。

## Related Sources

- [[開發與維護 Summary]]

## Related Topics

- [[Component 分層與共用策略]]
- [[CSS 模組與 SCSS 遷移]]

## Open Questions

- `web-common` 中哪些元件已被視為正式可共用元件，尚未有完整清單。
- Storybook 的產生、審查與更新責任尚未定義。
