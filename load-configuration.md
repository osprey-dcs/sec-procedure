# CCCR Configuration Loader

Reads CCCR Configuration CSV file to EPICS Database, and outputs CSV of put values.

## 1. Prerequisites

Conditions necessary to load CCCR Configuration

- CCCR Configuration CSV must be formatted correctly, see below
- EPICS Database must be running

### 1.1 CCCR Configuration CSV Format

Each row represents a channel and each non-identifying column represents a domain. Domain column headers map to \<DOMAIN\> in the signal name pattern and are case sensitive.

CSV Table Headers
| Column Header     | Description                       | Data Type |
| -------           | -------                           | -----     |
| CHASSIS           | Chassis/ Node number              | int       |
| CONNECTOR         | Chassis's Connector ID            | int       |
| CHANNEL           | Chassis's Channel number          | int [1-32]|
| SIGNAL            | Signal number                     | int       |
| USE               | Is this channel enabled?          | str [yes, no]|
| CUSTNAM           | Full channel name with Customer-requested designator| str                                                     |
| DESC              | UFF58 requirement                 | str       |
| IDLINE5           | UFF58 requirement                 | str       |
| RESPNODE          | UFF58 requirement                 | str       |
| EGU               | Engineering Units                 | str       |
| ESLO              | Slope in engineering units (EGU/V)| float [0.0]|
| EOFF              | Offset in engineering units (EGU) | float [0.0]|
| LOLOlim           | Low alarm                         | float [0.0]|
| LOlim             | Low warning                       | float [0.0]|
| HIlim             | High warning                      | float [0.0]|
| HIHIlim           | High alarm                        | float [0.0]|

### 1.2 EPICS Database Requirements

Record pattern: "FDAS:\<CHASSIS\>:SA:Ch\<CHANNEL\>:\<DOMAIN>"

Alarm pattern:  "FDAS:\<CHASSIS\>:ACQ:\<DOMAIN\>:\<CHANNEL\>"

## 2 Configurer script

1. To run script `configurer.py` from console with arguments for input and output:

```
$ python configurer.py -i /path/to/<file_name>.csv -o /path/to/output/ -v
Input file: /path/to/<file_name>.csv
Output file: /path/to/output/output.csv
...
```

The script will create `output.csv` in the folder to which `-o` points. Add `-v` for verbose output.

2. Configurer opens csv file, and converts values in cells according to their data type in the table above. 

3. If the column "USE" indicates "yes", Configurer will put the value to the EPICS record.

4. Finally, Configurer writes the output table.

