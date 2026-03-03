[Table of contents](../)

# CSS normalisation

The design goal behind this style sheet is to normalise certain styles that have become broadly expected across modern interfaces while avoiding overly opinionated defaults. Only relative units (i.e. `rem`) are used in this style sheet and no absolute units (e.g. `px`).

## Global styles

`*`, `*::after`, `*::before`
: Through the universal selector, the box model is set to `border-box` (see exception below: `textarea`) and padding and margin is removed.

`:focus-visible`
: Focusable elements are outlined which helps with keyboard navigation.

`:where(address, audio, blockquote, canvas, details, dl, embed, h1, h2, h3, h4, h5, h6, iframe, img, menu, object, ol, p, pre, table, ul, video):first-child:not(:where(hgroup *))`
and
`:where(address, audio, blockquote, canvas, details, dl, embed, h1, h2, h3, h4, h5, h6, iframe, img, menu, object, ol, p, pre, table, ul, video):last-child:not(:where(hgroup *))`
:These block elements have block (top and bottom) margins. To prevent extra space between containers and their respective first and last children, block-start (top) margins are removed from first children and block-end (bottom) margins are removed from last children. This allows containers' padding to fully control vertical spacing, avoiding unintended gaps caused by collapsing margins.

## Main root

`html`
: Styled to always show a vertical scrollbar (`overflow-y: scroll;`). This prevents visual layout shifts when navigating between pages with differing amounts of content. Vertical scrollbars are commonly needed and take up minimal space whereas horizontal scrollbars are rarely intentional and typically indicate unexpected content overflow.

## Sectioning root

`body`
: Styled so that the font size is `1rem`, the line height is `1.5rem` and the font family is `sans-serif`. A margin of `1rem` is also applied to all sides.

## Content sectioning

`address`
: Styled to render in normal font style rather than italics which has historically been the user agent default. The italic styling has no semantic basis and is a legacy convention that does not reflect how addresses are typically written or displayed in contemporary content.

`h1`–`h6`
: Given consistent, scaled font sizes and line heights that exceed those provided by default in most user agents.

## Text content

`blockquote`
: Given a minimalist style (left border and padding) to set it apart from other content.

`p`
: Styled to justify text and apply automatic hyphenation.

`pre`
: Given a minimalist style (background and border) to set it apart from other content.

## Inline text semantics

`a`
: Styled to remove the underline which has historically been the user agent default.

`abbr[title]`
: Styled with a help cursor to visually indicate that additional explanatory information (such as an expansion or definition) is available.

`cite`
: Styled to render in normal font style rather than italics which has historically been the user agent default. Citation styling varies across style guides and contexts so no presentational assumptions are made at this level.

`code`
: Given a minimalist style (background, border and padding) to set it apart from other content.

`kbd kbd`, `kbd samp`
: Given a minimalist style (background, border and padding) to set it apart from other content.

`q::after`, `q::before`
: Styled to remove content (`content: none`). Although the element was designed to insert locale-specific quotation marks as a presentation detail, in practice this behaviour causes problems: The generated marks are often not selectable or copied, may be inconsistently exposed to assistive technologies and make quotation marks behave unlike all other punctuation which is authored explicitly in HTML. By requiring quotation marks to be part of the document text, this rule improves copy-and-paste fidelity, accessibility, predictability across user agents and authorial control while still allowing for purely semantic annotation.

`span[title]`
: Styled with a dotted underline and help cursor to visually indicate the presence of supplementary information (tool tips).

## Image and multimedia

`audio`, `img` and `video`
: Styled to display as a block with a height of `auto` and a maximum width of `100%`.

`img`
: Styled so that any visible fallback text (from the `alt` attribute) is rendered in italics, making it visually distinct from surrounding text when an image can not be displayed.

## Embedded content

`embed`, `iframe`, `object`
: Styled to display as a block with a border style of `0`, a block-size (height) of `auto` and a maximum width of `100%`. Although they share similar functionality, each element can be rendered differently by user-agent default, particularly with regard to borders and sizing.

## SVG and MathML

No changes made.

## Scripting

`canvas`
: Styled to display as a block.

## Demarcating edits

No changes made.

## Table content

Table elements are styled to match Wikimedia's "wikitable" conventions. This replaces the default user-agent table styles, which are inconsistent across browsers and generally unsuitable for modern layouts.

## Forms

`button, input, select, textarea`
: Styled to inherit font family and font size from their parent elements. This ensures consistent typography across the user interface by overriding user-agent default fonts and sizes. Padding is normalised and vertical alignment is set to `middle` except for the input types `checkbox` and `radio`. Block-size (height) is normalised for all input types except `checkbox`, `file`, `image` and `radio`. The hover state uses the system colour `Highlight` for the outline to provide clear visual feedback.

`textarea`
: The only element in this style sheet using the `content-box` box model. This allows its block-size (height) to be set using the `lh` unit so that only the content area is counted. Padding and margin are excluded from the block-size.

## Interactive elements

`dialog`
: Normalised across user agents.

# Web Components

No changes made.