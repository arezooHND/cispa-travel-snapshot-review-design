# Design Rationale

## Why Two Designs?

I explored two final design directions because they optimise for different review workflows.

**Design 1 – Unified Change Table** focuses on traceability. Each trip appears only once, and users can inspect the full v1 → v2 → v3 history directly from the row. This design prioritises auditability and makes it easier to understand how a record evolved over time.

**Design 2 – Changes-First Digest** focuses on speed. Instead of presenting every trip equally, it groups changes by importance and surfaces items that require attention first.

If I had to recommend one design, I would choose **Design 1**. The trade-off is that it requires slightly more visual scanning than the digest view, but it provides a complete audit trail while still allowing users to filter and focus on meaningful changes.

---

## Five Snapshot Differences and How They Are Treated

### T-2009 (v1 → v2)

The estimated cost changed from €4,500 to €450.

This is treated as a **real change** because it is a major correction rather than a routine update. The magnitude of the difference suggests either a data-entry error or a significant correction that could affect reporting and approval decisions.

### T-2010 (v2 → v3)

The trip status changed from approved to no-show.

This is treated as a **real change** because workflow status directly affects administrative outcomes, reimbursement processes, and reporting.

### T-2011 → T-2911 (v1 → v2)

The Trip ID changed while the underlying trip appears to remain the same.

This is treated as a **real change** and highlighted separately because identifier migrations can create confusion when tracking historical records. The design represents this as a rename rather than a deletion followed by an addition.

### T-2014

The original T-2014 trip disappears, while another trip later appears using the same ID.

This is treated as a **high-priority review case** because the same identifier is associated with different travellers. The system cannot safely determine intent without human validation.

### T-2001

The traveller name changes from "anna becker" to "Anna Becker".

This is treated as **noise** rather than a meaningful business change. The underlying traveller remains the same and no administrative action is required. The design suppresses this type of update by default.

---

## Edge Case

The most ambiguous case is **T-2014**.

In v1, T-2014 belongs to Tim Krüger and is later removed. In v3, the same Trip ID appears again, but this time it is associated with Leon Roth.

From the data alone, it is not clear what happened. The same ID is linked to two different travellers, and the notes do not provide a definitive answer.

Instead of automatically deciding whether this is a renamed trip or a completely new one, my design highlights it as a review-required case and brings it to the user's attention.

---

## Scaling to 500 Rows

With 500 rows, showing every record equally would create significant visual noise.

The design therefore prioritises changed records and collapses unchanged trips into summary groups. Search, department filters, change-type filters, and the "Hide cost Δ < €50" option reduce the visible dataset further.

In the Unified Change Table, row histories are loaded only when expanded. This preserves context without overwhelming the user. The design remains usable because attention is directed toward exceptions rather than requiring users to scan hundreds of stable records.
