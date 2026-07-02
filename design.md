# Design System Rules

本文档整理自「唯品会 B 端设计系统 V2.0」中已读取的 Figma 节点，供 Claude Code / Codex 生成 UI 时执行。

原则：只使用已确认规则；不要把示意图颜色、标注颜色、规范页排版间距当作产品 UI 规则。

## Visual Style

- 面向 B 端后台工具：克制、清晰、高信息密度、可扫描。
- 页面不要做营销化 hero、大面积装饰图形或过度留白。
- 页面层级优先靠背景、白色容器、边框、圆角和有限投影建立。
- 主操作要突出，但每个操作区域只能有一个主按钮。
- 表格、筛选、表单、卡片区域应保持对齐稳定。

## Color Tokens

### Brand

| Token | Usage | Value |
| --- | --- | --- |
| `Brand-7` | pressed / active | `#484CB8` |
| `Brand-6` | primary normal | `#5765DE` |
| `Brand-5` | hover | `#797EF5` |
| `Brand-4` | progress / component accent | `#8A95FF` |
| `Brand-3` | special cases | `#A3ACFF` |
| `Brand-2` | module background | `#BDC3FF` |
| `Brand-1` | light background | `#F0F1FF` |

Use `Brand-6` for primary actions. Use `Brand-5` for hover and `Brand-7` for pressed.

### Secondary

| Token | Usage | Value |
| --- | --- | --- |
| `Secondary-7` | pressed | `#A8337D` |
| `Secondary-6` | normal | `#CC3D93` |
| `Secondary-5` | hover | `#E065A7` |
| `Secondary-4` | special cases | `#F5A6CE` |
| `Secondary-3` | special cases | `#FAC3DD` |
| `Secondary-2` | module background | `#FFE0ED` |
| `Secondary-1` | light background | `#FFF0F9` |

Secondary color is for auxiliary emphasis, not for replacing primary action color.

### Neutral And Background

| Token | Usage | Value |
| --- | --- | --- |
| `Neutral-white` | card / container | `#FFFFFF` |
| `Neutral-Gray-1` | page background | `#F5F7F9` |
| `Neutral-Gray-2` | secondary background / disabled fill | `#F3F4F5` |
| `Neutral-Gray-3` | tertiary background | `#E2E2E2` |
| `Neutral-Gy1-5%` | table row hover | `rgba(34, 34, 34, 0.05)` |
| `Neutral-Gy2-50%` | modal mask | `rgba(0, 0, 0, 0.5)` |

Use `#F5F7F9` as the default page background and `#FFFFFF` as the default content container background.

### Text

| Token | Usage | Value |
| --- | --- | --- |
| `Text-6` | main content / title | `#222222` |
| `Text-5` | secondary content / long description | `#585C64` |
| `Text-4` | auxiliary hint | `#858B94` |
| `Text-3` | placeholder | `#B3B6BC` |
| `Text-2` | disabled text | `#CACCD2` |
| `Text-1` | white text | `#FFFFFF` |

### Line

| Token | Usage | Value |
| --- | --- | --- |
| `Line-3` | border | `#D3D6DA` |
| `Line-2` | divider | `#E7E7E7` |
| `Line-1` | chart grid / base line | `#EEEEEE` |

Use `Line-3` for input/select/button borders. Use `Line-2` for module dividers.

### Status

| Token | Usage | Value |
| --- | --- | --- |
| `Success-5` | success normal | `#21A663` |
| `Success-4` | success hover | `#24B86D` |
| `Success-6` | success pressed | `#1C8C54` |
| `Success-1` | success light background | `#E9F9F1` |
| `Warning-5` | warning normal | `#FF7A1A` |
| `Warning-4` | warning hover | `#FF8C1A` |
| `Warning-6` | warning pressed | `#E56000` |
| `Warning-1` | warning light background | `#FFF6E3` |
| `Error-5` | error / danger normal | `#F6445D` |
| `Error-4` | error / danger hover | `#FF5C66` |
| `Error-6` | error / danger pressed | `#E2283A` |
| `Error-1` | error light background | `#FFF0F0` |
| `Data-Increase` | increase | `#F85C72` |
| `Data-Decrease` | decrease | `#21A663` |

Use data tokens for increase/decrease values; do not reuse generic error/success semantics for data movement unless the business meaning matches.

### Known Inconsistencies

- Some visible Figma labels differ from local paint styles, such as `Brand-6`, `Brand-2`, `Brand-5`, `Text-3`, and `Error-6`.
- Prefer local paint style values listed in this document.
- Do not create duplicate tokens for visible-label variants.

## Typography

### Font Family

Use this stack for UI:

```css
font-family: "PingFang SC", "Microsoft YaHei", "微软雅黑", "Helvetica Neue", Helvetica, Arial, sans-serif;
```

- Chinese and mixed UI text: `PingFang SC`.
- Windows fallback: `Microsoft YaHei` / `微软雅黑`.
- Numeric dashboard values: `Avenir` where available.

### UI Text Scale

| Role | Size / Line-height | Weight |
| --- | --- | --- |
| Level 1 title | `20 / 28` | Semibold 600 |
| Level 2 title | `18 / 26` | Semibold 600 |
| Level 3 title | `16 / 24` | Semibold 600 |
| Extra large body | `16 / 24` | Regular 400 |
| Large body | `14 / 22` | Regular 400 |
| Large body emphasis | `14 / 22` | Semibold 600 |
| Medium body | `13 / 20` | Regular 400 |
| Medium body emphasis | `13 / 20` | Semibold 600 |
| Small body | `12 / 18` | Regular 400 |
| Small body emphasis | `12 / 18` | Semibold 600 |
| Tiny label | `10 / 16` | Regular 400 |

Rules:

- Page title: use `20 / 28 Semibold`.
- Module title or dialog title: use `18 / 26` or `16 / 24 Semibold`.
- Form, table, and normal body: use `14 / 22 Regular`.
- Dense table cells, tags, and auxiliary content may use `12 / 18`.
- Use `10px` only for tiny labels; do not use it for normal body text.

### Numeric Text

Use `Avenir` numeric styles for metrics, KPI cards, amounts, and dashboard values.

| Level | Size / Line-height | Weight |
| --- | --- | --- |
| `Num 1` | `32 / 48` | Black 900 or Medium 500 |
| `Num 2` | `28 / 42` | Black 900 or Medium 500 |
| `Num 3` | `24 / 36` | Black 900 or Medium 500 |
| `Num 4` | `20 / 30` | Black 900 or Medium 500 |
| `Num 5` | `18 / 26` | Black 900 or Medium 500 |
| `Num 6` | `16 / 24` | Black 900 or Medium 500 |
| `Num 7` | `14 / 22` | Heavy 800 or Medium 500 |
| `Num 8` | `13 / 20` | Heavy 800 or Medium 500 |
| `Num 9` | `12 / 18` | Heavy 800 or Medium 500 |

## Layout And Grid

### Page Layout

- Use `1440px` as the baseline design width.
- Two main layout structures are supported:
  - Top layout: top bar + content area.
  - Side layout: top bar + side navigation + content area.
- Top bar height: `112px`.
- Page background: `#F5F7F9`.
- Content containers: `#FFFFFF`.
- Top navigation and side navigation may exceed the content grid width.

### Grid

- Prefer a `24` column grid for complex B-end pages.
- `12` column grid exists, but `24` columns provide better flexibility for complex content.
- Grid variables:
  - `W`: total grid/content width.
  - `a`: column width, computed by screen/content width.
  - `i`: gutter.
  - `M`: page margin outside content width.
- Do not place content inside gutters.
- Do not place content outside column width for visual alignment hacks.

Grid formulas:

```text
with outer margin: W = (a + i) * n
without outer margin: W = (a + i) * n - i
```

Example from Figma:

```text
i = 24
n = 24
W = 1440 - 256 - 32 - 24 = 1128
1128 = (a + 24) * 24
a = 24
```

Do not hardcode `a = 24` globally; column width changes with content width.

### Gutters And Spacing

Use only these gutter values:

| Name | Value |
| --- | --- |
| `XS` | `8px` |
| `SM` | `16px` |
| `MD` | `24px` |
| `LG` | `32px` |
| `XL` | `40px` |

Rules:

- Default module spacing: `16px` or `24px`.
- Use `16px` for dense content.
- Use `24px` for more comfortable module separation.
- Use `32px` or `40px` only for larger page-level separation.
- Use `8px` for compact inner spacing, not as the default module gap.
- Box height should follow an `8n` rhythm when possible.

### Module Layout

- Page modules support `3` column and `4` column layouts.
- When the screen reaches the minimum width, modules should stack.
- A single page should use no more than `3` card layout combinations.
- Recommended combinations include `1+1+1`, `1+2`, and `1+1+1+1`.

## Radius

Use only these radius levels:

| Level | Value | Usage |
| --- | --- | --- |
| Level 1 | `8px` | module card, dialog |
| Level 2 | `4px` | button, select, input, tooltip, product image |
| Full | `9999px` | tag, option tag, pill search |

Rules:

- Cards and dialogs use `8px`.
- Buttons, inputs, selects, tooltips, and product images use `4px`.
- Tags and pill controls use full radius.
- Do not invent intermediate radius values unless existing code already defines them.

## Shadow

Use only these shadow levels:

| Level | CSS | Usage |
| --- | --- | --- |
| Base | `0 2px 4px rgba(211, 211, 211, 0.5)` | content modules that must separate from background; use sparingly |
| Middle | `0 4px 12px rgba(0, 0, 0, 0.1)` | hover layer, dropdown, select menu |
| Upper | `0 4px 24px rgba(0, 0, 0, 0.1)` | modal, warning layer, global message, notification |

Rules:

- Do not apply shadow to every card by default.
- Dropdowns and hover float layers use middle shadow.
- Modal, message, and notification use upper shadow.
- Base shadow is optional and should be used sparingly.

## Component: Button

- Usage:
  - Buttons trigger explicit user actions.
  - Primary button is for the highest-priority action in a page or operation area.
  - Default button is for normal secondary actions.
  - Text button is for weak actions, row operations, and lightweight entrances.
  - Danger button is for destructive or high-risk actions such as delete, move, disable, or permission changes.
  - Icon-only button is for narrow spaces; prefer icon + text when space allows.

- Variants:
  - `theme`: `primary` / `default` / `danger`
  - `appearance`: `filled` / `outline` / `text`
  - `icon`: `none` / `prefix` / `suffix` / `icon-only`
  - `size`: `default` / `small`
  - `state`: `normal` / `hover` / `pressed` / `disabled` / `loading`

- Size:
  - Default height: `32px`.
  - Small height: `24px`.
  - Radius: `4px`.
  - Default text: `14px / 22px`.
  - Small text: `12px / 18px`.
  - Default text-only button example: about `60x32`.
  - Default prefix/suffix icon button example: about `82x32`.
  - Default icon-only button example: about `38x32`.
  - Small text-only button example: about `40x24`.
  - Small prefix/suffix icon button example: about `56x24`.
  - Small icon-only button example: about `28x24`.
  - Default horizontal padding: `16px`.
  - Small horizontal padding: `8px`.
  - Default icon-text gap: `8px`.
  - Small icon-text gap: `4px`.

- State:
  - Primary normal: `#5765DE` background, white text.
  - Primary hover: `#797EF5`.
  - Primary pressed: `#484CB8`.
  - Danger normal: `#F6445D`.
  - Danger hover: `#FF5C66`.
  - Danger pressed: `#E2283A`.
  - Default filled: `#F3F4F5` background, `#222222` text.
  - Default outline: white background, `#D3D6DA` border, `#222222` text.
  - Disabled: `#F3F4F5` background and `#CACCD2` text.
  - Loading: keep theme color, show loading icon before text, prevent repeated submit.

- Layout:
  - One operation area can have only one primary button.
  - Recommended combinations: one primary + one secondary; one primary + multiple secondary.
  - Prefix icon improves recognition.
  - Suffix icon is only for directional actions such as dropdown or navigation.
  - Small buttons are for card interiors, table interiors, and compact layouts.
  - Full-width buttons are for small modules or mobile-compatible form pages.

- Do:
  - Use primary button for `submit`, `save`, `confirm`, or the page's main action.
  - Use default outline button for `cancel`, `return`, or secondary actions.
  - Use danger button for destructive operations and consider confirmation.
  - Use text button for table row operations.
  - Use clear action labels such as `下载`, `导出`, `去查看`.
  - Use loading state for asynchronous submit, save, query, or import/export.

- Don't:
  - Do not place multiple primary buttons in one operation area.
  - Do not use danger buttons for normal emphasis.
  - Do not use primary filled buttons only to make the UI look stronger.
  - Do not overuse icon-only buttons.
  - Do not use unclear labels such as `操作` or `更多处理`.
  - Do not bind actions to disabled buttons.
  - Do not create undefined button sizes, radius, or state colors.

## Component: Dialog / Modal

Extracted from the「创建PK实验」dialog flow (Figma file `YUse2swwK7pHy9pJRpNwlm`, nodes 8053-13845 / 14068 / 15884 / 19770 / 17874).

- Usage:
  - Dialog is for a focused create / confirm / detection flow layered above the current page.
  - Use it when the task needs the page context to stay visible behind a mask, but user attention must be captured.

- Position:
  - Center the dialog both horizontally and vertically in the viewport (centered over the mask).
  - When the viewport is shorter than the dialog, the mask scrolls so the whole dialog stays reachable.

- Size:
  - This flow uses a fixed dialog size of `800 x 540`.
  - Keep the dialog height fixed across all internal states (initial / loading / pass / fail / success) so the box does not jump; let the body area take up remaining space with internal scroll on overflow, and keep short states top-aligned with bottom whitespace.
  - `800 x 540` is the confirmed size for this create-flow dialog; other dialog sizes may exist and should be read from their own Figma nodes before use.

- Mask:
  - Mask color: `rgba(0, 0, 0, 0.5)` (`Neutral-Gy2-50%`).

- Radius and Shadow:
  - Dialog corner radius: `8px` (Radius Level 1).
  - Dialog shadow: upper level `0 4px 24px rgba(0, 0, 0, 0.1)`.

- Structure:
  - Header: fixed `48px` height; title on the left, close `✕` on the right. Title uses `18 / 26 Semibold` (or `16 / 24 Semibold`).
  - Body: content region with `24px` side padding; scrolls internally when content exceeds the fixed height.
  - Footer: right-aligned action buttons pinned to the bottom of the body; `取消` uses default outline, the main action uses primary; only one primary button.

- Behavior:
  - Close via header `✕`, `取消`, mask click, or `Esc`.
  - Use loading state on the button for asynchronous submit (e.g. `创建`, `检测`), and prevent repeated submit.
  - Footer confirm button may stay hidden / disabled until a precondition passes (e.g. `创建` appears only after detection passes).

## Component Coverage

Button and Dialog / Modal rules have been extracted into this document so far.

Do not invent rules for Input, Select, Table, Card, Tabs, Tag, or other components until their Figma component areas are read and summarized.
