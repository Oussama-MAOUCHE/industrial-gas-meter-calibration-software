# Technical Notes

## Application structure

The project contains parallel G4 and G6 branches with the same overall application structure. Both belong to the same calibration-software project family.

The main workflow is represented by the calibration window and a statistics/history window.

## Project chronology

Project-specific artifacts begin in 2018. The G6 branch contains updates through 2019, while the G4 branch includes later project and interface updates through January 2021.

These dates describe the surviving project artifacts; the case study does not use them as a performance or seniority claim.

## Main operator workflow

The main screen supports multiple meter positions.

The workflow includes:

- meter position/number;
- serial number, normally incremented automatically and manually adjustable when required;
- initial index;
- final index at Qmax;
- final index at 0.2 Qmax.

The interface provides a **Calculate** action and a **Save and Reset** action.

The replacement design consolidated the main operator workflow into one working screen. The previous software required navigation through several windows to complete a calibration cycle; the replacement interface reduced that navigation by keeping the key entry, calculation, result and reset actions together.

Result areas include calculated error values and visual indicators associated with the correction result.

## Correction logic

The calibration process uses replaceable gear-wheel combinations to correct meters that advance or lag.

I designed and implemented the mathematical correction algorithm used by the application to:

1. derive the meter error from the bench readings;
2. determine the applicable correction interval;
3. associate that interval with a gear-wheel reference;
4. present the result to the operator using numeric and visual cues.

The exact WLanguage implementation is not reproduced in this public case study. The portfolio focuses on the verified workflow, design and selected evidence rather than reconstructing proprietary source code.

## Correction mapping

Original project material includes a mapping between:

- wheel reference;
- correction range;
- display color.

This supports the correction-guidance workflow represented by the application. The complete operational mapping remains private.

## Local data storage

The application uses a local Microsoft Access database.

The project data definition includes fields corresponding to:

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

## Scope and evidence boundary

The public case study documents the application workflow, supported technical design and selected original evidence.

It does not claim formal legal-metrology certification or an unsupported factory-wide production KPI, and it does not publish raw operational data, proprietary project files or the complete correction mapping.
