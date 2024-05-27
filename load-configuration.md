# CCCR Configuration Loader

Reads CCCR Configuration CSV file to EPICS Database, and outputs CSV of put values.

## 1. Prerequisites

Conditions necessary to load CCCR Configuration

- CCCR Configuration CSV must be formatted correctly, see below
- EPICS Database must be running

### EPICS Database Requirements

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

