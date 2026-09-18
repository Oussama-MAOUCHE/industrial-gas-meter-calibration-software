# Technical Notes

## Application structure

The surviving project contains parallel G4 and G6 branches with the same overall application structure. Both belong to the same calibration-software project family.

The main workflow is represented by the calibration window and a statistics/history window.

## Main operator workflow

The main screen accepts readings for multiple meter positions.

Observed input fields include:

- meter number;
- serial number;
- initial index;
- final index at Qmax;
- final index at 0.2 Qmax.

The interface provides a **Calculate** action and a **Save and Reset** action.

The replacement design consolidated the main operator workflow into one working screen. The previous software required navigation through several windows to complete a calibration cycle; the replacement interface reduced that navigation by keeping the key entry, calculation, result and reset actions together.

Result areas include calculated error values and visual indicators associated with the correction result.

## Correction logic

The calibration process uses replaceable gear-wheel combinations to correct meters that advance or lag.

The application was designed to:

1. derive the meter error from the entered bench readings;
2. determine the applicable correction interval;
3. associate that interval with a gear-wheel reference;
4. present the result to the operator using numeric and visual cues.

The mathematical algorithm was designed and implemented by the developer of this application.

The exact WLanguage implementation is not reproduced in this public case study. The surviving project is stored in WINDEV's native project format, and the portfolio focuses on the verified workflow, design and evidence rather than reconstructing source code.

## Correction mapping evidence

A surviving spreadsheet maps:

- wheel reference;
- correction range;
- display color.

This supports the correction-guidance workflow represented by the application.

The complete operational mapping is kept private rather than copied into the public repository.

## Local data storage

The project uses a local Microsoft Access database (`Data.mdb`).

The surviving data definition identifies fields corresponding to:

- date/time;
- meter position;
- initial index;
- Qmax final index;
- 0.2 Qmax final index;
- calculated error;
- gear-wheel reference;
- meter serial number.

This data supports calibration history and related operational/statistical use.

The raw database is not published.

## Evidence boundary

The portfolio documents the observable application design, supported workflow and surviving data structure.

It does not claim:

- formal legal-metrology certification;
- a specific quantified production increase;
- a precise development duration;
- source-code availability in a modern text/Git format;
- that this test bench was the factory's only or main production resource.
