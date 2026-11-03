# How this repository was made (Garissa County)

This file is written by the build on 2026-11-03, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| County Assembly of Garissa: "Acts", Kenya Gazette Supplements (Government Printer) as PDF with a text layer | <https://garissaassembly.go.ke/acts/> | 2026-10-31 | Text of the Garissa County Acts as published in the Kenya Gazette Supplement (Government Printer, Nairobi) and posted on the website of the County Assembly of Garissa (garissaassembly.go.ke). Written law is not a literary work under the Copyright Act, 2001 (Cap. 130, Laws of Kenya), section 2, definition of "literary work", which ends: "but does not include a written law or a judicial decision". |
| County Assembly of Garissa: "Acts", Kenya Gazette Supplements (Government Printer) as PDF with a text layer | <https://garissaassembly.go.ke/acts/> | 2026-11-03 | Text of the Garissa County Acts as published in the Kenya Gazette Supplement (Government Printer, Nairobi) and posted on the website of the County Assembly of Garissa (garissaassembly.go.ke). Written law is not a literary work under the Copyright Act, 2001 (Cap. 130, Laws of Kenya), section 2, definition of "literary work", which ends: "but does not include a written law or a judicial decision". |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `garissa-county-climate-change-act-2025` | The Garissa County Climate Change Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |
| `garissa-county-disaster-risk-management-act-2025` | The Garissa County Disaster Risk Management Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |
| `garissa-county-livestock-marketing-act-2025` | The Garissa County Livestock Marketing Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |
| `garissa-county-environmental-restoration-and-livelihood-improvement-act-2023` | The Garissa County Environmental Restoration and Livelihood Improvement Act, 2023 | 1 | 2026-11-03 to 2026-11-03 |
| `garissa-county-financing-of-cities-and-urban-areas-act-2026` | The Garissa County Financing of Cities and Urban Areas Act, 2026 | 1 | 2026-11-03 to 2026-11-03 |
| `garissa-county-health-facility-improvement-financing-act-2024` | The Garissa County Health Facility Improvement Financing Act, 2024 | 1 | 2026-11-03 to 2026-11-03 |

The build made 6 commits:

| Commits | Kind |
| ---: | --- |
| 6 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-11-03.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 6 tags.

## Dates

Each commit is dated at noon (Africa/Nairobi) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Act is dated by the "Date of Commencement" its Gazette Supplement prints; where that is not a date (for example "See Section 1"), by the date of the Gazette Supplement, and never before the Date of Assent. https://garissaassembly.go.ke/acts/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `a3b0672ec65bc443e0a1956aaff258206c7f9991ea29cd035372d0fa4571366f` (217974 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `5d0eabdf207e7a114e8dbc8112ed3b044537b711`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

Not yet run for this build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Text as enacted only: the county assembly posts each Act as its Kenya Gazette Supplement, with no consolidated text, so each Act is one version ("oldest version available", first_law null), credited to the publisher, not to an amending law. Amending Acts in this record are separate Acts; their amendments are not applied to the Acts they amend.
- Each version is dated by the Date of Commencement the Supplement prints; where that is not a date ("See Section 1"), by the date of the Supplement, and never before the Date of Assent.
- One file per section; the long title and enacting words are "000-title", and each Schedule its own file. Part headings and section headings (bold rows or margin notes) stand above the section they head.
- Left out: the Supplement cover, the title block (number, Dates of Assent and Commencement, which go into the version note) and the arrangement of sections, running heads and page numbers.
- An Act is left out when its PDF is a scan with no text layer, is not a Gazette Supplement, cannot be read reliably (tables or forms that the independent check does not find in the same order), or its parsed sections differ from its arrangement of sections.
- Each new Act has first_law null and one oldest-version-available record, dated 2026-11-03 and credited to the publisher because the latest amendment-in-force day is not established. The source supplements are as enacted, without a verified current consolidation; amendments are not inferred or applied.
- Each new Act uses one whole-document unit retaining every text-layer line of its official supplement, including cover, commencement and assent statements, arrangement, page furniture and tables. These fixed source statements are retained to avoid dropping words in a provisional section split.
- Whitespace alone is normalized in the recorded text. The independent comparison reads the unchanged official PDF with pypdf, compares every non-whitespace character in source order, and normalizes repeated dot leaders in tables only. It does not use parser headings or furniture exclusions.
- The source inconsistencies in the Health Facility and Environmental Restoration supplements are retained verbatim; no section number, Act year or date is corrected.
- The Investment and Development Authority scan is excluded because its text layer disagrees between independent engines.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Gazette Supplement PDFs.
- GPT-6 wrote the local preparation and checking code. No model output is used as legal text; every recorded text character comes from the official assembly PDF.
