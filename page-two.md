# Page Two — Sync Test

Second verification page for the BASE-748 sync recovery — pairs with [Page One](./page-one.md).

## What this page checks

- Two files in the **same push** both arrive (the per-file loop handles more than one change per delivery).
- A relative link **between synced pages** resolves inside Base rather than pointing back at GitHub.
- An image reference renders (or degrades visibly rather than silently).

## Sample content

### Quote and emphasis

> The importer swallows failures — so the real test of this fix is not that sync works, but that when it breaks, something *says so*.

### Nested list

- Delivery
  - Signature check
  - Decrypt (the BASE-748 fix point — this used to 500 silently)
- Reconcile
  - Match by path
  - Update in place, never wipe-and-rebuild

### Inline code

The sweep script flags any row where `decryptSecret(webhookSecret)` throws — those need regeneration, not redelivery.

---

*Test file created 2 Oct 2026 for BASE-748 verification. Safe to delete once the sync is proven.*
