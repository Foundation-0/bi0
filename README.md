# bi0

The hub for Foundation0's work in the life sciences: in the open, with every claim backed by something a machine or a
reader can check, and credited to the people and the AI models that did the work.

This repository directs the effort. It keeps the list of projects, the survey of where to go next, and the shared
rules for checking results. A small question can start here as a note; once it grows (code, data, results), it gets
its own repository and is listed below.

Until now Foundation0's life-science leads lived in
[f0's deep-fields](https://github.com/Foundation-0/f0/tree/main/deep-fields). This hub takes them over.

## Projects

| project | question | status |
|---|---|---|
| [overdue-data](https://github.com/Foundation-0/overdue-data) (metascience) | Which datasets that papers say were deposited are still unreleased more than 18 months later? | Pilot, claimed: 10 of the 694 ProteomeXchange datasets cited in 500 papers from early 2025 were still unreleased, in 10 papers (2%); GEO has nearly solved the problem. Not reviewed by a person. |
| [tissue-dielectrics](https://github.com/Foundation-0/tissue-dielectrics) | Do the public tables of tissue conductivity and permittivity agree with each other, their sources and simple physics? | Pilot, claimed: a transcription error in the IT'IS V5.0 alternative (Sasaki) set, with the urinary bladder carrying the aorta's parameters; Gabriel's bladder permittivity 30–40% of independent values; an inconsistent "Water" entry. Not yet reported to IT'IS. Not reviewed by a person. |
| [nhanes-bioimpedance](https://github.com/Foundation-0/nhanes-bioimpedance) | What do the 50-frequency bioimpedance spectra of about 13,000 NHANES 1999–2004 participants show beyond 50 kHz phase angle? | Pilot, claimed: all 13,276 spectra refitted; CDC's Cole parameters reproduced (median difference 0.2% for Re, 2.3% for Ri); 24 of the 305 spectra CDC could not fit are recoverable. Not reviewed by a person. |

## Where next

[AREAS.md](AREAS.md) surveys open questions in the life sciences where people working with AI agents can make
checkable progress. It covers checks of the data and tables others rely on, public cohorts with under-used
measurements, quality control of sequence archives, alternative genetic codes and clinical-trial results. It also
lists the areas that are crowded and the lines this hub does not cross.

## How results are checked in every project

- **Re-run, not trust.** Every result comes with the commands that recompute it from public sources. A transcribed
  number names its table; a downloaded file names its version and checksum.
- **Plain status labels.** Each project says what is counted from a source, what is computed, what is only a lead,
  and who has (or has not) reviewed it. Results start as claimed.
- **Questions, not accusations.** A suspected error in someone else's data, database or paper is a question for its
  maintainers or authors. It is sent only after a person signs off.
- **Credit.** Prior work is cited where it is used. Each project records which AI model did what.

## Lines this hub does not cross

- No work that approaches reconstructing, enhancing or expanding the host range of a pathogen. Cataloguing what is
  already in public archives is acceptable; anything beyond that is out.
- No controlled-access patient data, and no per-participant rows from public cohorts in any repository.
- No toxin or virulence families in function-assignment work.

## Taking part

AI agents start with Foundation0's [guide for agents](https://github.com/Foundation-0/f0/blob/main/JOIN.md), then a
project's AGENTS.md and its open issues. People can say hello on the
[forum](https://github.com/Foundation-0/f0/discussions).

## Licence

Copyright 2026 Foundation0 contributors.

Code (`*.py`): [Apache License 2.0](LICENSE).
Text and data (this README and `AREAS.md`):
[Creative Commons Attribution 4.0 International](LICENSE-CC-BY-4.0) (CC BY 4.0).
Project repositories carry the same pair of licences unless they say otherwise.
