# Industrial Gas Meter Calibration Software (G4/G6)

Professional desktop application developed in-house at **EN-AMC (later SAIEG — Sonelgaz Group)** for the calibration of **Sagem G4 and G6 gas meters** on an existing metrological test bench.

After the previous bench software became unusable, I designed and developed a replacement application that restored software-assisted calibration on that station. I also simplified the operator workflow by bringing the main data-entry, calculation, result-display and save/reset steps together on a single working screen instead of requiring repeated navigation across several windows.

![Calibration application main screen](calibration-main-screen.png)

## At a glance

| Area | Details |
|---|---|
| Professional context | EN-AMC (later SAIEG — Sonelgaz Group) |
| Application | Windows desktop calibration software |
| My role | Application design, development, functional testing and operational validation |
| Technologies | WINDEV / WLanguage, Microsoft Access |
| Meter variants | Sagem G4 and G6 |
| Main outcome | Restored the affected bench workflow and simplified the operator process |

## Project context

The test bench was one of several calibration/testing resources used in the factory. Operators performed meter measurements on the bench, and the application converted those readings into practical correction guidance.

The physical adjustment relied on changing a gear-wheel combination in the meter mechanism. Different wheel combinations produced different correction ranges, so the software had to calculate the meter error and map it to the appropriate correction reference.

## My contribution

I independently designed and developed the application, including:

- the operator-facing desktop interface;
- the mathematical correction algorithm;
- separate G4 and G6 variants within the same project family;
- mapping between calculated correction ranges and gear-wheel references;
- visual and numeric presentation of results;
- automatic serial-number progression with manual adjustment when needed;
- local storage for calibration history and related operational data;
- developer-led functional testing and validation of the application before and during operational use.

I worked with the plant technical department to understand the calibration process and also used technical input from a visiting engineer representing the meter supplier/manufacturer.

## Testing and validation

I tested the application throughout development and when putting it into use on the calibration bench. This was developer-led testing rather than a separate independent QA campaign.

The checks focused on the end-to-end operator workflow, including:

- meter and serial-number data entry;
- Qmax and 0.2 Qmax reading entry;
- error/correction calculations;
- mapping calculated ranges to the expected gear-wheel reference;
- numeric and visual result presentation;
- save/history behavior;
- reset and preparation for the next calibration cycle;
- the G4 and G6 application variants used for the intended bench workflow.

Operational use of the replacement application provided additional validation that the software supported the required calibration process.

No separate formal test plan or execution log is published in this repository. The testing description is based on first-hand project context together with the surviving application artifacts.

## How the application worked

For each meter position, the operator worked with:

- the meter position/number;
- a serial number that normally advanced automatically, with manual adjustment available when required;
- the initial index;
- the final index at **Qmax**;
- the final index at **0.2 Qmax**.

The application then:

1. calculated the error/correction from the entered readings;
2. determined the applicable correction range;
3. mapped that range to a gear-wheel reference;
4. displayed the result numerically and visually;
5. saved the operation before resetting the screen for the next cycle.

Original project material also includes a correction table linking wheel references, correction ranges and display colors.

## Operational impact

The failure of the previous software had made this calibration station unavailable for its normal software-assisted workflow.

The replacement application returned the affected test bench to operational use and removed a software blocker from one part of the factory's calibration and production process.

It also made the operator workflow more direct. The main entry, calculation, result and save/reset actions were consolidated on one screen rather than spread across several windows as in the previous software. This reduced unnecessary navigation and made each calibration cycle more practical to perform.

The bench was one of several calibration/testing resources in the factory, so the impact is presented at the workstation and process level rather than as a factory-wide production metric.

## Technical profile

| Area | Implementation |
|---|---|
| Application type | Windows desktop application |
| Development environment | WINDEV / WLanguage |
| Meter variants | G4 and G6 |
| Local storage | Microsoft Access |
| Main stored data | date/time, meter position, indexes, calculated error, wheel reference, serial number |
| Main workflow | readings → error/correction calculation → gear-wheel guidance → result display → save/history |

The original WINDEV project is kept private. This repository documents the application workflow, technical design and selected project evidence.

## Evidence

The case study is supported by original professional artifacts, including:

- separate G4 and G6 WINDEV project branches;
- the main application interface;
- the local Microsoft Access database and matching data definitions;
- the gear-wheel correction mapping;
- project windows and backup/history artifacts.

Only selected, sanitized evidence is published. Raw databases, internal project files, operational records and internal paths remain private.

See:

- [Technical Notes](docs/technical-notes.md)
- [Evidence & Confidentiality](evidence/README.md)

## Related application

A separate companion application was developed for gear-wheel consumption and supply statistics. It is a distinct project and is not documented in this repository.
