# Design Defence

## Prompt 1 – Named Row Explanation

### T-2011 / T-2911

My design displays these records as a single trip with a renamed identifier rather than two separate trips. Expanding the row reveals the complete v1 → v2 → v3 history and shows that T-2011 became T-2911 during the lifecycle.

This avoids misleading users into thinking a trip was deleted and recreated when the evidence suggests a system migration or identifier update.

### T-2014

T-2014 is displayed as a review-required case. The original trip disappears, while a later trip associated with a different traveller appears using the same ID.

Because the intent cannot be determined confidently from the data alone, the interface highlights the row and explicitly requests user attention instead of making an automatic assumption.

### T-2017 and T-2018

These trips share the same traveller name and identical dates, which makes them appear potentially duplicated.

The design keeps them as separate records but highlights the relationship. This allows users to investigate the similarity without incorrectly merging two potentially independent trips.

### T-2020

T-2020 remains the same trip across all snapshots, but the approver changes in the final version.

The design treats this as a meaningful administrative update and highlights the specific field that changed rather than the entire row.

---

## Prompt 2 – My Own Pick

I selected T-2009 because it represents one of the most significant corrections in the dataset.

The estimated cost changes from €4,500 to €450. Unlike formatting adjustments or capitalisation fixes, this modification could affect approvals, budgets, and reporting. For that reason, it receives a high-priority visual treatment and appears prominently in both design directions.

---

## Prompt 3 – Filter Under €50

The design includes a "Hide cost Δ < €50" filter.

When enabled, rows whose only change is a cost difference smaller than €50 are hidden from the main review list. This helps users focus on larger corrections and workflow-relevant updates.

The underlying colour hierarchy and change classification remain unchanged. High-priority cases such as status changes, Trip ID migrations, additions, removals, and review-required records remain visible regardless of the filter because they represent different categories of change.

---

## Prompt 4 – Questions for the Admin Team

### 1. Is T-2011 → T-2911 officially considered a rename?

The design currently treats this as an identifier migration, but I would want confirmation that historical references should remain linked.

### 2. What happened with T-2014?

The T-2014 case suggests possible ID reuse. Understanding whether this is expected behaviour would influence how aggressively the interface flags similar cases.

### 3. Should column reordering, capitalization fixes, and similar formatting changes be treated as meaningful changes?

During the comparison, I noticed several changes that appeared visually different but did not alter the underlying meaning of the data, such as capitalization corrections (e.g., "anna becker" → "Anna Becker") and potential structural changes like column reordering.

Before finalizing the design, I would want to understand whether administrative users consider these changes relevant. My current assumption is that they represent noise rather than meaningful workflow changes, so they receive little or no visual emphasis. Confirming this assumption would help determine which changes should be surfaced prominently and which should remain hidden by default.
