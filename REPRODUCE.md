# How this repository was made (Garissa County)

This file is written by the build on 2026-10-31, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| County Assembly of Garissa: "Acts", Kenya Gazette Supplements (Government Printer) as PDF with a text layer | <https://garissaassembly.go.ke/acts/> | 2026-10-31 | Text of the Garissa County Acts as published in the Kenya Gazette Supplement (Government Printer, Nairobi) and posted on the website of the County Assembly of Garissa (garissaassembly.go.ke). Written law is not a literary work under the Copyright Act, 2001 (Cap. 130, Laws of Kenya), section 2, definition of "literary work", which ends: "but does not include a written law or a judicial decision". |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `garissa-county-climate-change-act-2025` | The Garissa County Climate Change Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |
| `garissa-county-disaster-risk-management-act-2025` | The Garissa County Disaster Risk Management Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |
| `garissa-county-livestock-marketing-act-2025` | The Garissa County Livestock Marketing Act, 2025 | 1 | 2025-08-08 to 2025-08-08 |

The build made 3 commits:

| Commits | Kind |
| ---: | --- |
| 3 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `future`: laws not yet in force on 2026-10-31.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 3 tags.

## Dates

Each commit is dated at noon (Africa/Nairobi) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Each Act is dated by the "Date of Commencement" its Gazette Supplement prints; where that is not a date (for example "See Section 1"), by the date of the Gazette Supplement, and never before the Date of Assent. https://garissaassembly.go.ke/acts/

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `f321063a69634ffe847f75805bf8c9d75b224dc8006cb4ebd24509dfbd9414a8` (137255 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

3 versions of 3 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Text as enacted only: the county assembly posts each Act as its Kenya Gazette Supplement, with no consolidated text, so each Act is one version ("oldest version available", first_law null), credited to the publisher, not to an amending law. Amending Acts in this record are separate Acts; their amendments are not applied to the Acts they amend.
- Each version is dated by the Date of Commencement the Supplement prints; where that is not a date ("See Section 1"), by the date of the Supplement, and never before the Date of Assent.
- One file per section; the long title and enacting words are "000-title", and each Schedule its own file. Part headings and section headings (bold rows or margin notes) stand above the section they head.
- Left out: the Supplement cover, the title block (number, Dates of Assent and Commencement, which go into the version note) and the arrangement of sections, running heads and page numbers.
- An Act is left out when its PDF is a scan with no text layer, is not a Gazette Supplement, cannot be read reliably (tables or forms that the independent check does not find in the same order), or its parsed sections differ from its arrangement of sections.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- Claude Code (claude-opus-5-5) wrote Lexifina's code and chose the sources. No model output is used as legal text or dates: every word comes from the Gazette Supplement PDFs.
