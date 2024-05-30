# Export data from the system

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
