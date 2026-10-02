# Page One — Sync Test

This page exists to verify the GitHub → Base wiki sync end to end after the BASE-748 fix (webhook secret regeneration + the empty-catch logging).

## What this page checks

- A **new file** in a subfolder arrives as a new Base page under the right collection path.
- Markdown constructs render: headings, bold, lists, code, links, and a table.

## Sample content

The sync pipeline listens for pushes to `main`, verifies the webhook signature, then reconciles changed files against existing pages by path.

### A list

1. Webhook delivery received
2. Signature verified
3. File fetched from the repository
4. Page created or updated in place

### A code block

```ts
export function pageKey(path: string): string {
  return path.replace(/\.md$/, "").toLowerCase();
}
```

### A table

| Step | Expected result |
| --- | --- |
| Push to main | Delivery shows 200 in GitHub |
| Resync | This page appears in Base |
| Edit + push | The edit arrives without a manual refresh |

### A link

See also [Page Two](./page-two.md), which verifies cross-page links and a second file in the same folder.

---

*Test file created 2 Oct 2026 for BASE-748 verification. Safe to delete once the sync is proven.*
