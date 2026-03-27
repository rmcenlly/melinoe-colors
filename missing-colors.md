# Missing / Undocumented Colors

Colors present in `melinoe-color-theme.json` that have **no corresponding scope** in `BlackGreenTheme.jsonc`, and may be worth adding there for completeness.

---

## Token Colors (syntax highlighting)

These scopes exist in melinoe but BlackGreenTheme does not address them directly (it relies on VS Code's default fallback):

### JavaScript / TypeScript specific
| Scope | melinoe color (old) | Suggested BGT color |
|---|---|---|
| `entity.name.module.js` | `#FF5370` | `#9CE0BB` — variables are mint green in BGT |
| `variable.import.parameter.js` | `#FF5370` | `#9CE0BB` |
| `variable.other.class.js` | `#FF5370` | `#9CE0BB` |
| `meta.class-method.js entity.name.function.js` | `#82AAFF` | `#DCDCAA` — functions are yellow in BGT |
| `variable.function.constructor` | `#82AAFF` | `#DCDCAA` |
| `entity.name.method.js` | `#82AAFF` | `#DCDCAA` |
| `tag.decorator.js entity.name.tag.js` | `#82AAFF` | `#DCDCAA` |
| `tag.decorator.js punctuation.definition.tag.js` | `#82AAFF` | `#DCDCAA` |
| `source.js constant.other.object.key.js string.unquoted.label.js` | `#FF5370` | `#F44747` (invalid/error) |

### JSON nested key levels
BGT uses a flat VS Code Dark+ base with no per-level JSON key coloring. melinoe colors JSON keys differently at each nesting depth (levels 0–8). Consider adding these to BGT if you want consistent JSON highlighting:

| Level | Scope suffix | melinoe color (updated) |
|---|---|---|
| 0 | `...support.type.property-name.json` | `#9CE0BB` |
| 1 | (one extra nesting) | `#3AD970` |
| 2 | (two extra nestings) | `#3A9D60` |
| 3 | (three extra nestings) | `#D4D4D4` |
| 4–8 | (cycling pattern) | alternates `#9CE0BB` / `#3AD970` / `#3A9D60` / `#D4D4D4` |

### Markdown extended scopes
BGT only covers `markup.bold`, `markup.italic`, `markup.heading`, `markup.inserted/deleted/changed`. melinoe additionally covers:

| Scope | Notes |
|---|---|
| `text.html.markdown markup.inline.raw.markdown` | Inline code in markdown |
| `text.html.markdown markup.inline.raw.markdown punctuation.definition.raw.markdown` | Backtick punctuation around inline code |
| `markup.heading.markdown punctuation.definition.heading.markdown` | The `#` characters in headings |
| `markup.quote punctuation.definition.blockquote.markdown` | The `>` blockquote marker |
| `string.other.link.title.markdown` | Link text `[text]` |
| `string.other.link.description.title.markdown` | Reference link labels |
| `constant.other.reference.link.markdown` | Reference link anchors |
| `markup.raw.block` | Fenced code block content |
| `punctuation.definition.fenced.markdown` | The ` ``` ` fence markers |
| `variable.language.fenced.markdown` | Language identifier after fence |
| `meta.separator` | Horizontal rules (`---`) |
| `markup.table` | Table content |
| `punctuation.definition.list_item.markdown` | List bullet markers |

### CSS / SCSS scopes
BGT addresses CSS attribute names and class selectors but misses:

| Scope | Notes |
|---|---|
| `source.css support.type.property-name` (and sass/scss/less/stylus/postcss variants) | CSS property names — melinoe uses `#9CE0BB` |
| `source.sass keyword.control` | Sass `@`-rule keywords |

### Misc scopes not in BGT
| Scope | Notes |
|---|---|
| `constant.other.color` | Named color constants |
| `support.other.variable` | Misc support variables |
| `string.other.link` | String-typed link values |
| `punctuation.separator.inheritance.php` | PHP `::` and `->` |
| `keyword.other.template` / `keyword.other.substitution` | Template/interpolation keywords |
| `meta.tag.sgml` | SGML/XML meta tags |
| `markup.deleted.git_gutter` / `markup.inserted.git_gutter` / `markup.changed.git_gutter` | Git gutter diff indicators |

---

## UI Colors (`colors` block)

The following UI color keys exist as **commented-out entries** in `BlackGreenTheme.jsonc` (and therefore are absent from melinoe). They may be worth activating if you want finer UI control:

### High-value additions to consider
| Key | Suggested value | Notes |
|---|---|---|
| `editor.selectionBackground` | `#264f78` | Active text selection color |
| `editorCursor.foreground` | `#aeafad` | Cursor color |
| `editorGhostText.foreground` | `#ffffff56` | Inline AI/ghost text suggestions |
| `editor.lineHighlightBackground` | (null in BGT) | Current line highlight — null = no highlight |
| `editorSuggestWidget.background` | `#202020` | Autocomplete popup background |
| `editorSuggestWidget.foreground` | `#cccccc` | Autocomplete popup text |
| `editorSuggestWidget.selectedBackground` | `#3ad92022` | Selected autocomplete item |
| `editorHoverWidget.background` | `#202020` | Hover tooltip background |
| `editorHoverWidget.border` | `#454545` | Hover tooltip border |
| `editorInlayHint.foreground` | `#969696` | Inlay type hints |
| `editorInlayHint.background` | `#6161611a` | Inlay hint background |
| `diffEditor.insertedLineBackground` | `#9bb95533` | Added lines in diff editor |
| `diffEditor.removedLineBackground` | `#ff000033` | Removed lines in diff editor |
| `gitDecoration.modifiedResourceForeground` | `#e2c08d` | Modified files in source control |
| `gitDecoration.addedResourceForeground` | `#81b88b` | Added files in source control |
| `gitDecoration.deletedResourceForeground` | `#c74e39` | Deleted files in source control |
| `gitDecoration.untrackedResourceForeground` | `#73c991` | Untracked files |
| `gitDecoration.ignoredResourceForeground` | `#8c8c8c` | Git-ignored files |
| `breadcrumb.foreground` | `#cccccccc` | Breadcrumb path text |
| `breadcrumb.background` | `#0f0f0f` | Breadcrumb background |
| `list.hoverBackground` | `#2a2d2e` | File explorer hover |
| `list.inactiveSelectionBackground` | `#37373d` | Inactive sidebar selection |
| `scrollbarSlider.background` | `#79797966` | Scrollbar thumb |
| `scrollbarSlider.hoverBackground` | `#646464b3` | Scrollbar thumb on hover |
| `terminal.selectionBackground` | `#264f78` | Terminal text selection |
| `terminal.ansi*` | various | Full terminal ANSI color palette (16 colors) |
