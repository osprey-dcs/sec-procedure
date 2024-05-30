# Per Test User Configuration Procedure

Configuration should be loaded prior to any Acquisition run,
and may be re-loaded at any time afterwards.

Be aware that a re-load involves pulsing all AC/DC coupling
relays, which may cause glitches in ADC data.

1. Select one of the two Workstation computers.
1. Copy a `.csv` file onto that Workstation.
1. Navigate to the `CCCR Upload` OPI.
1. Under `Select file`, either:
    1. Click on the open icon and select a file and click `Open`.
       The path of the selected file will appear in the adjacent field.
    1. Alternately, type or paste a path into the field.
1. Click on the `Load` button.
1. Wait for the `Busy` indicator to clear.
1. Under `Previous result`,
   If the `Status` indicator indicates failure,
   check the last error message and notify support.

__Note__ In case of failure, it is necessary to re-load a previously good Configuration.
