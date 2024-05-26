# Data Previewer and Exporter

## Environment

The acquistion Previewer application may be run
on either, or both, of the two Workstations computers.

Completed acquistions are found under `/data`.
The full path of the most recently completed
acquistion may be found on either the `Acq Monitor`
or `Acq Expert` OPI screens.
A full path for a `.hdr` file will have the form:

```
/data/YYYY/MM/YYYYMMDD-hhmmss-DESC/DESC-YYYYMMDD-hhmmss.hdr
```

Where the actual date and start time of the acquistion,
as well as the the run DESC string, are substituted.

Exported data files may be placed under `/export`.

## View acquistion

1. Launch the `viewer` application by one of the following means.
    1. Double-click on the `Previewer` icon on the Desktop
    1. Run `viewer` from a terminal
1. From the `File` menu, select `Open`.  An `Open File` dialog will appear.
1. Navigate through `/data` and select a `.hdr` file to `Open`.
1. Select a channel from the `Signal` dropdown.
1. (Optional) click the FFT button to recompute the frequency
  vs amplitude plot for the visible time range.

Under the `Help` menu, see `Button/Wheel Shortcuts` for details
on zooming.

## Export to file

Requires that a `.hdr` file loaded into the `viewer` application.

Note that user choices for `Out File Type`, `Time Range`,
and `Channels` are remembered by the `viewer` application.

1. From the `File` menu, select `Export`
1. Choose `Out File Type` as `UFF58b` or `CSV`
1. Choose `Time Range` as either `All Time` or `From Start/End` (Selectors on main UI)
1. Choose a list of channel numbers.  eg.
    1. `1-1024` selects all available channels.
    1. `513` selects a single channel
    1. `1-25,43` selects a range and an individual channel
    1. `500-600,800-900` selects two ranges
1. Click `OK`
1. Choose a directory under `/export` and client `Save`
1. The export process may take some time depending on
    the number of channels, time range, and sample rate.
