# Industrial Gas Meter Calibration Software (G4/G6)

Desktop software developed for the calibration workflow of **Sagem G4 and G6 gas meters** on an existing metrological test bench used in an industrial production environment.

The previous software used with this bench had become unusable. I designed and developed a replacement application that restored the bench's software-assisted calibration workflow and allowed operators to resume work on that station. I also simplified the operator flow by consolidating the main calibration tasks into a single working screen instead of requiring repeated navigation across several windows.

![Calibration application main screen](calibration-main-screen.png)

## Project context

The test bench was one of the calibration/testing resources used in the factory. Operators performed meter measurements on the bench and entered the resulting readings into the application.

The application processed those readings, calculated the meter error and translated the result into practical correction guidance for the operator.

The physical adjustment relied on changing a gear-wheel combination in the meter mechanism. Different wheel combinations produced different correction ranges.

## My contribution

I independently designed and developed the application, including:

- the operator-facing desktop interface;
- the mathematical correction logic;
- separate G4 and G6 variants within the same project family;
- mapping between calculated correction ranges and gear-wheel references;
- visual and numeric presentation of results;
- local storage of calibration history and related operational data.

I worked with the plant technical department to understand the calibration process and used technical input from a visiting engineer representing the meter supplier/manufacturer.

## How the application worked

For each meter position, the operator entered the relevant bench readings, including:

- meter/serial information;
- initial index;
- final index at **Qmax**;
- final index at **0.2 Qmax**.

The application then:

1. calculated the error/correction from the entered readings;
2. determined the appropriate correction range;
3. mapped that range to a gear-wheel reference;
4. displayed the result numerically and visually;
5. allowed the operation to be saved before resetting the screen for the next cycle.

The surviving project data also includes a correction table linking wheel references, correction ranges and display colors.

## Operational impact

The failure of the previous software had made this calibration station unavailable for its normal software-assisted workflow.

The replacement application returned the affected test bench to operational use and removed a software blocker from one part of the factory's calibration and production process.

Beyond restoring the function of the station, the new interface made the operator workflow more direct: the main data-entry, calculation, result-display and save/reset steps were brought together on one screen rather than spread across several windows as in the previous software. This reduced unnecessary navigation and made each calibration cycle more practical to perform.

The bench was one of multiple calibration/testing resources in the factory, so the impact is presented at the workstation and process level rather than as a factory-wide production metric.

## Technical profile

| Area | Implementation |
|---|---|
| Application type | Windows desktop application |
| Development environment | WINDEV |
| Meter variants | G4 and G6 |
| Local storage | Microsoft Access (`Data.mdb`) |
| Main stored data | date/time, meter position, indexes, calculated error, wheel reference, serial number |
| Main workflow | readings → error/correction calculation → gear-wheel guidance → result display → save/history |

The original project survives in WINDEV's native project format. This repository therefore focuses on the verified application workflow, technical design and selected evidence rather than republishing proprietary project files or recreating source code.

## Evidence

The project is supported by surviving professional artifacts, including:

- separate G4 and G6 WINDEV project branches;
- the main application interface;
- the local Access database and matching data definitions;
- the gear-wheel correction mapping;
- project windows and backup/history artifacts.

Only selected, sanitized evidence is published. Raw databases, internal project files, operational records and internal paths remain private.

See:

- [Technical Notes](docs/technical-notes.md)
- [Evidence & Confidentiality](evidence/README.md)

## Scope note

This case study covers the G4/G6 calibration application itself. A separate companion application for gear-wheel consumption and supply statistics is outside the scope of this repository.
