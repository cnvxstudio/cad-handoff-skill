# CAD Handoff Check

A scriptless AI-agent skill for preparing a traceable handoff of a 2D CAD drawing or review PDF. It guides six checks: source/revision, recipient format, units/reference distance, drawing contents, PDF layout, and reopening the actual deliverable.

## Use

Read `SKILL.md` and use the tools and evidence already available in your session. No dependency, API key, drawing upload, or network call is required. Missing evidence stays `NOT CHECKED`; the workflow does not certify engineering or manufacturing readiness.

## Files and license

`SKILL.md` contains the complete workflow. This repository contains documentation only, with no product implementation, executable scripts, credentials or customer drawings. Released under MIT-0; see `LICENSE`.

The [CADEditor format-exchange guide](https://cadeditor.io/cad-converter/) is an optional reference. The workflow works independently of CADEditor. Maintained by Ethan Lee, product contact for CADEditor.
