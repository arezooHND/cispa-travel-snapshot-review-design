# CISPA – Take-home Design Exercise

## Frontend Design & Visualisation

This repository contains my submission for the CISPA Frontend Design & Visualisation take-home exercise.

The task focuses on designing a user experience that enables administrative staff to efficiently review and understand changes across three lifecycle snapshots of a travel-booking spreadsheet:

- Planning (v1)
- Approved (v2)
- Reconciled (v3)

## Initial Analysis

As a first step, I manually reviewed and compared all three spreadsheet versions to understand how travel records evolved throughout the workflow.

This analysis helped identify different categories of changes, including newly added trips, removed entries, corrected values, status updates, Trip ID changes, and potential data-quality issues. I also annotated the spreadsheets to highlight the relative importance of each change and to separate significant modifications from minor corrections or noise.

### Spreadsheet Annotation Strategy

To support the comparison process, I annotated the spreadsheet snapshots directly using a color-coding system.

**Snapshot colors**

- Light blue: Planning snapshot (v1)
- Medium blue: Approved snapshot (v2)
- Dark blue: Reconciled snapshot (v3)

**Change annotations**

- Green: Newly added records
- Red: Removed records
- Orange: Modified values compared to the previous snapshot

The intensity of the orange highlight reflects the perceived importance of the change:

- Light orange: Minor updates or potential noise
- Medium orange: Relevant changes that should remain visible
- Dark orange: High-impact changes requiring user attention

Examples of high-impact changes include Trip ID migrations, major cost corrections, destination changes, workflow status updates, and other modifications that could affect administrative decisions.

This annotation process helped distinguish meaningful changes from low-priority updates and directly influenced the visual hierarchy, filtering strategy, and prioritization approach explored in the wireframes.

## Design Exploration

Before developing the final solution, I explored several interface concepts based on:

- Manual analysis of the spreadsheet snapshots
- Observed change patterns in the data
- AI-assisted brainstorming and design exploration
- Personal design iterations and usability considerations

The wireframes below represent the first design concepts created during the exploration phase. Their purpose was to evaluate different ways of visualising changes across spreadsheet versions and to better understand the strengths and weaknesses of each approach.

These concepts were later refined and evolved into the final design presented in this submission.

### Early Wireframes

- wireframe_v1.pdf — Side-by-side spreadsheet comparison
- wireframe_v2.pdf — Unified audit table

### Editable Source

Figma:
https://www.figma.com/design/16zSGlybfUYxlOwXEbhShl/CISPA-%E2%80%93-Take-home-Design-Exercise?node-id=24-666&m=dev&t=LJ2K1ALkMnyONuv7-1

### Final Wireframes

- wireframe_v1.pdf — Unified change table
- wireframe_v2.pdf — Changes-first digest

Figma:
https://www.figma.com/design/16zSGlybfUYxlOwXEbhShl/CISPA-%E2%80%93-Take-home-Design-Exercise?node-id=13-1831&m=dev&t=ynHeB0mVAn0zw80G-1
