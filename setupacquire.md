# Configuration and Acqusition

## Prerequisites

Successful completion of [Recovery and Troubleshooting](powerupdown.md).

It is necessary to repeat Recovery and Troubleshooting after
any chassis is power cycled or otherwise reset.

It is recommended to repeat [Recovery and Troubleshooting](powerupdown.md)
at the start of each day on which records will be collected.


## Loading Configuration

Configuration should be loaded prior to any Acqusition run,
and may be re-loaded at any time afterwards.

Be aware that a re-load involves pulsing all AC/DC coupling
relays, which may cause glitches in ADC data.

1. Select one of the two Workstation computers
1. Copy a `.csv` file onto the
1. Navigate to the `CCCR Upload` OPI
1. Under `Select file`, either:
    1. click on the open icon and select a file,
       which will appear in the adjacent field.
    1. Type or paste a path into the field
1. Click on the `Load` button
1. Wait for the `Busy` indicator to clear
1. Under `Previous result`,
   If the `Status` indicator indicates failure,
   check the last error message and notify support.

## Preparation

1. Ensure that the desired `ADC Sample Rate` is selected.
   Found on `Main`, `ADC Status`, and other OPIs.
    1. After changing the sampling rate, repeat [Recovery and Troubleshooting](powerupdown.md).
1. Set the desired `Run Description` string.

## Start Acqusition

1. Open the `Acq. Control` OPI
1. Ensure `System Ready?` shows `Ready`.
    1. If not, repeat [Recovery and Troubleshooting](powerupdown.md) and re-load CCCR.
    1. If not successful, contact support
1. Disable `ADC Acquire`.
    1. ADC sampling must be disabled for a synchronized re-start.
1. Ensure `Can Start?` shows `Ready`.
1. Click `Start`
1. Ensure status shows `Run` and Last Message `Acquire`.
    1. If not, contact support
1. `ADC Acquire` will switch back to `Enable` automatically
1. `Last Started Name` will update with the current run name.

Note that `Can Start?` will show `Not ready` while an acqusition is running.

## Monitor Acqusition

While acquisition is in-progress, observe that:

- On `Acq. Recording` Monitor or Expert screens.
    - Ensure `Can Start?` continues to show `Ready`.
    - Recording is in progress for selected chassis
    - Packet drop rate counters remain zero
    - File size(s) increasing
- On `ADC Status` screen.
    - `Summary` for all `In Use` shows `Ok`

## End Acqusition

1. On the `Acq. Control` OPI
1. Click `Stop`.
1. `ADC Acquire` will switch back to `Disable` automatically
1. Last Message will progress through:
    1. `Stopping...` (waiting for all samples to reach disk storage)
    1. `Post-process` while `.hdr` file is prepared for `viewer` application
    1. `Success` Successful completion
1. If Last Message shows `Failure`, contact support.
1. On `Success` the `Last Completed File` will update with the full path
   of the newly created `.hdr`.
    1. Hint: May select and copy+paste into `viewer` Open dialog.
