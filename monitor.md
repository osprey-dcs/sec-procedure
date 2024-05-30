# Monitor a Data Channel in Real Time

## Prerequisites

Previous completion of [Inspecting the Current State and Health](healthcheck.md).

## Selecting a channel to monitor

1. From the `Main` OPI, click on `Chassis Scope`
1. From the two rows of buttons on the left hand side of the pane,
   select the desired Chassis (`Chas`) and Channel (`Chan`)
1. If upper, time domain plot is not updating.
    1. Enable `ADC Acquire` from the `Main` OPI (or other screens on which this control appears)
1. If the lower, frequency domain plot is not updating
    1. Click on `Enable` by the `FFT Enable` control below this plot
