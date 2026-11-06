# How this repository was made (Kogi State)

This file is written by the build on 2026-11-05, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Kogi State Government: Bills & Laws (PDF) | <https://kogistate.gov.ng/bills-laws-odc/> | 2026-11-01 | Laws of Kogi State, from the copies the Kogi State Government publishes at kogistate.gov.ng ("Bills & Laws"). Official texts of a legislative nature are not eligible for copyright: Copyright Act, 2022 (Nigeria), s. 3(b). |
| Kogi State Government: Executive Order No. 3 of 2025, official gazette | <https://kogistate.gov.ng/wp-content/uploads/KOGI-STATE-EXECUTIVEORDER-NO-3-2025-GAZETTED.pdf> | 2026-11-05 | Official legislative texts are excluded from copyright by Nigeria Copyright Act 2022, section 3(b). |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `revenue-administration-law-2024` | Kogi State Revenue Administration Law, 2024 | 1 | 2024-01-24 to 2024-01-24 |
| `executive-order-no-3-2025-haulage-fees` | Executive Order on the Removal and Prohibition of Haulage Fees, Levies, and Multiple Charges on the Movement of Goods within, into, and through Kogi State | 1 | 2025-12-12 to 2025-12-12 |

The build made 2 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-05.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (Africa/Lagos) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Law here states its own commencement, and its version is dated by it; no general rule is applied. https://kogistate.gov.ng/bills-laws-odc/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `28de82f3dbdf00136f114f474ddaa3b031c32993453db4fefde8569ecee2ed88` (136867 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `3024ff164c261807dfc4d5b7b1b4a2cde4357da1`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

2 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

A second build from the same corpus into an empty folder gave identical hashes for all 2 history commits and 3 tags (history tip `11dbe1a9753f44c361cb6f104d54dd80576cbf5b`).

## Decisions made by hand

- Revenue Administration Law 2024 is dated 2024-01-24: section 1 says it "shall come into operation on the 24th day of January 2024".
- Each Law is one version: the text as enacted, credited to the Law itself (first_law) and dated by its commencement. Later amendments are not in this record.
- One file per section. The title lines printed before the enacting formula are "000-title", the enacting formula (where printed) is "001-enacting-formula", and schedules follow the sections. Each section's heading is its printed margin note (or, where there is none, "Section N") and stands as the file's first line; it is not part of the checked text.
- The text layer is read with line positions: running heads, page numbers and margin notes are set apart by their place on the page, and the pieces of one printed row are joined left to right. Lines wrapped by the printer are joined into one paragraph per line; a new paragraph starts at a section number, a bracketed (sub)paragraph letter or number, a quoted definition, a Part heading or a schedule heading. A Part heading printed after a section is placed at the head of the next section. Typing errors in the source stay as printed.
- Executive Order No. 3 of 2025: In-force basis is clause 1, which says "shall take effect immediately", together with the gazette notice identifying the issue date as 12 December 2025. Gazette No. 3, Vol. 1 is dated 12 December 2025. The retrieval date is not used as the in-force date.
- One current-text version, first_law null, credited to the official publisher as oldest version available. No reconstruction or unlisted amendments are asserted.
- Single-file act: complete official gazette text including all recitals, clauses 1–8 and execution text. Printed spelling and punctuation are preserved; only whitespace is normalized.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- none: the text is the PDF text layer, parsed by rules; no model wrote or corrected legal text.
- A model chose extraction and verification rules and reviewed source page images. Legal text is extracted unchanged from the official PDF text layer; no OCR or model-corrected words.
