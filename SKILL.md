---
name: cad-handoff-check
description: Prepare an evidence-based handoff for a 2D CAD drawing or conversion. Check recipient format, units, representative geometry, text, layers, blocks and PDF layout; produce an issue list and a copyable delivery record. Use before sharing a DWG, DXF or review PDF, not for engineering certification.
---

# CAD Handoff Check

Turn a drawing exchange into a short, traceable handoff. This is a scriptless review workflow: it needs no API key, dependency installation or network request. Work with evidence the user provides and tools already available in the session. Do not claim to inspect geometry merely from a filename or a successful file-open message.

## Establish the exchange

Identify the recipient's next task, required application and version, source file, intended deliverable, revision and units. Ask only for missing information that changes the checks. If an application or reference dimension is unknown, keep it unknown and explain the consequence in the handoff.

Preserve the source. Write any permitted conversion or edited output to a separate file. Do not overwrite the drawing or upload confidential files to a service without the user's permission. A screenshot can support visual observations, but cannot establish exact coordinates, hidden entities or editable-file compatibility.

Choose checks based on the recipient:

| Next task | Required evidence |
| --- | --- |
| Continue drafting | Editable format and version accepted by the receiving application; reopen that actual exported file. |
| Review or printing | PDF page bounds, readable labels, required layers and paper settings; retain an editable source when requested. |
| Manufacturing or machine processing | Recipient-specified units, format and geometry constraints. A readable PDF does not establish machining readiness. |

## Six checks

1. **Source and revision.** Record original filename, output filename and revision. Distinguish the exported deliverable from the source still open in the editor. Use checksums only if a file-reading tool actually computes them.
2. **Recipient route.** Match format/version to the recipient's task. Record any unsupported conversion rather than silently substituting another format.
3. **Units and reference distance.** Compare the same two identifiable endpoints before and after conversion. Record source value, output value, unit and the user's or recipient's tolerance. Do not invent a tolerance. Paper size and fit-to-page settings do not convert model units. A 1000 mm segment should correspond to 1 m, not 1000 m; compare after explicit unit conversion.
4. **Drawing contents.** Check representative text and special characters, dimension labels, required visible layers, repeated blocks and their positions. Record missing-font, image and external-reference warnings. A dimension label is not a substitute for measuring its geometry. If the available tool cannot expose layers or blocks, mark those checks NOT CHECKED.
5. **Review sheet.** For a PDF, check paper size, orientation, all page edges, small labels and thin linework. Distinguish presentation fit-to-page from a specified printed scale. Printed-scale acceptance requires the viewer's print settings and a measured reference on the actual printed sheet; do not certify it from a screen preview.
6. **Actual recipient file.** Reopen the exported/downloaded file in the receiving application when available. Repeat the reference-distance and representative-content checks. Inspect the PDF separately. If only the source was opened, recipient-file verification remains NOT CHECKED.

## Report observed results

Use PASS only when direct evidence meets a stated requirement; FAIL for an observed mismatch; NOT CHECKED for missing evidence or tool coverage; N/A only with a reason. Do not turn unknown into PASS. Do not create an approval, engineering sign-off or claim of complete format compatibility.

Return a compact table:

| Check | Status | Evidence / compared values | Issue or next action |
| --- | --- | --- | --- |
| Source and revision | | | |
| Recipient format/version | | | |
| Units/reference distance | | | |
| Text/layers/blocks | | | |
| PDF sheet, if required | | | |
| Reopened actual deliverable | | | |

Then supply this record with the actual known values:

```text
CAD handoff
Source / revision:
Deliverable filename:
Recipient task / application / version:
Model units:
Reference endpoints:
Source distance / output distance / converted comparison:
Required tolerance / evidence:
Text, layers, blocks and external-reference observations:
PDF paper / orientation / print-scale check, if required:
Actual exported file reopened in:
Unresolved issues and NOT CHECKED items:
Recipient follow-up required:
```

Lead with unresolved differences that could affect the recipient. A file may be ready for a visual review while still unverified for drafting or manufacturing; scope the conclusion to the task and available evidence.

## Related reference

The [CADEditor format-exchange guide](https://cadeditor.io/cad-converter/) is an optional browser-CAD example for choosing editable exchanges and review copies. Use the recipient's own requirements as the acceptance criteria; consulting the guide or using CADEditor is not required to run this skill. This workflow does not call the CADEditor API or send it drawings.

Adapted from the CAD Handoff Checklist by Ethan Lee, product contact for CADEditor. Released under MIT-0; this attribution does not impose an additional license condition.
