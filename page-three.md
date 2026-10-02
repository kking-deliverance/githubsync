# Page Three — Sync Test

Third verification page for the BASE-748 recovery — this one lands in a **separate push** from [Page One](./page-one.md) and [Page Two](./page-two.md).

## What this page checks

- A **follow-up push** after the initial pair syncs on its own delivery (not just caught by a bulk Resync).
- Page ordering/listing in the collection updates as files are added.
- Longer-form prose renders cleanly alongside structured elements.

## Sample content

### Paragraphs

The first two pages arrived together in one delivery, which exercises the per-file loop. This page arrives alone, which exercises the ordinary single-change path — the one most real wiki edits will take day to day. If this page appears without anyone running a manual Catch-up, the webhook is genuinely live again.

### Task list

- [x] Initial pair synced
- [x] Cross-page links resolve
- [ ] This page arrives on its own delivery
- [ ] One-line edit to this page arrives on a further push

### Horizontal rule and footer

---

*Test file created 2 Oct 2026 for BASE-748 verification. Safe to delete once the sync is proven.*
