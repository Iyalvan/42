# Communication and block management

Editable Power Platform diagrams for the requirements discussion. Business rules that have not been agreed are marked **TBD**.

## Files

```text
communication-management/
├── README.md
├── requirements.md
└── diagrams/
    ├── source/
    │   └── communication-management.drawio
    ├── library/
    │   └── communication-components.xml
    └── exports/
        ├── 01-system-architecture.png
        ├── 01-system-architecture.svg
        ├── 02-daily-workflow.png
        └── 02-daily-workflow.svg
```

[Open the editable master](diagrams/source/communication-management.drawio). It contains two pages: **System architecture** and **Daily processing workflow**.

The `.drawio` file uses native shapes, editable text, containers and connectors attached to their endpoints. Connector labels belong to the connectors and move with them. The source is uncompressed XML, so changes can also be reviewed in Git. It contains no diagram screenshots or external image dependencies.

## Edit or expand

1. Open the `.drawio` file in draw.io Desktop or diagrams.net using **File > Open From > Device**.
2. Select the page using the tabs at the bottom. Double-click text to edit it; move or resize blocks using their handles.
3. Duplicate an existing block or load the reusable library through **File > Open Library From > Device**, selecting `diagrams/library/communication-components.xml`.
4. Drag a component from the library onto the canvas. Use draw.io's connection handles to attach new arrows to the blocks.
5. Move a container to move its contents together. Enlarge a container or page when adding more processing steps. Add another page when a new subject needs its own diagram.
6. Save changes to the `.drawio` master, then refresh the exports. Update `requirements.md` when a TBD is resolved.

The library provides Canvas app, Dataverse, Power Automate, daily recurrence, CSV document, API, eligibility decision, milestone, requirement note and environment container components. These are editable shapes with the same styles as the diagrams.

## Edit after exporting

Both supplied PNGs and both SVGs embed the **complete two-page draw.io source**, while displaying their named page. Open one through **File > Open From > Device** in draw.io to recover the shapes and connections. Editing the PNG in an image editor changes pixels; opening it in draw.io restores the diagram.

When exporting future PNG or SVG versions, keep **Include a copy of my diagram** selected. Retain the `.drawio` master: image conversion, resizing or publishing tools can strip the embedded diagram data. The embedding option is described in the [draw.io export documentation](https://www.drawio.com/docs/manual/export/export-diagram/).

The preview images were rendered from the same shape and connector definitions without Chromium. XML structure, references, reusable library entries and recovery of the embedded source were checked. The diagrams have not been opened in the draw.io editor during this session.

## Scope

The architecture covers source CSV intake, Dataverse storage, the Canvas app, daily Power Automate processing, third-party delivery APIs, block state changes and the proposed CSV return. The workflow includes all six communication milestones. The number of flows, exact connectors, table schema and processing order remain design decisions.

The named Power Automate features are documented by Microsoft: [scheduled flows](https://learn.microsoft.com/en-us/power-automate/run-scheduled-tasks), [Dataverse actions](https://learn.microsoft.com/en-us/power-automate/dataverse/overview), [Apply to each](https://learn.microsoft.com/en-us/power-automate/apply-to-each) and [Data Operations](https://learn.microsoft.com/en-us/power-automate/data-operations). CSV parsing and the third-party API connector are deliberately left TBD.
