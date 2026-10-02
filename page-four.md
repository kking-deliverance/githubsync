# Page Four — Sync Test

Fourth verification page for the BASE-748 recovery — the edge-case page. Pairs with [Page One](./page-one.md), [Page Two](./page-two.md) and [Page Three](./page-three.md).

## What this page checks

- Characters that commonly break naive importers: ampersands & angle brackets < >, emoji 🚀, accented text (Zoë, naïve, Müller), and an em-dash — all in one page.
- An HTML-looking snippet inside a code fence stays literal instead of being interpreted:

```html
<script>alert("this should render as text, never execute")</script>
```

- A deeply nested structure survives:

1. Level one
   1. Level two
      - Level three bullet
        - Level four bullet with `inline code`

## Sample content

### Blockquote with formatting inside

> **Bold inside a quote**, a [link inside a quote](./page-one.md), and `code inside a quote` — three things flattening importers tend to lose.

### A longer table

| Case | Input | Expected in Base |
| --- | --- | --- |
| Ampersand | AT&T | AT&T, not AT&amp;T |
| Angle brackets | a < b > c | rendered literally |
| Emoji | 🚀 | visible, not stripped |
| Accents | Zoë, Müller | intact |
| Fenced HTML | script tag above | shown as code, never executed |

---

*Test file created 2 Oct 2026 for BASE-748 verification. Safe to delete once the sync is proven.*
