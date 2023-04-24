# Data Loss Analysis

## Description

Determine possible reason behind data loss of about 60% using [MQTTronic](https://git.ift.tuwien.ac.at/lab/rschwaiger/mqttronic)

## Debugging

### Running Example Measurement on Local Machine

#### Requirements

- [ICOc](https://mytoolit.github.io/ICOc/)
- [ICOtools](https://github.com/MyTooliT/ICOtools)

#### Execution

```sh
python3 measure.py && icoanalyzer experiment.hdf5
```

#### Results

##### First Version

Data loss (as reported by `icoanalyzer`) (commit [`b7daa140`](https://github.com/MyTooliT/Data-Loss-Analysis/commit/b7daa1402d0b7119fb6b2f308b741876f25ffdcc)):

| OS    | 1. Attempt | 2. Attempt | 3. Attempt |
| ----- | ---------- | ---------- | ---------- |
| macOS | 0 %        | 0 %        | 0 %        |
| Linux | 0.29 %     | 0.27 %     | 0.56 %     |

##### Second Version

Data loss (as reported by `icoanalyzer`) (commit [`3ccd825d`](https://github.com/MyTooliT/Data-Loss-Analysis/commit/3ccd825d5f2612a9dbfcc0802541c360971a1902)):

| OS    | 1. Attempt | 2. Attempt | 3. Attempt |
| ----- | ---------- | ---------- | ---------- |
| macOS | 0 %        | 0 %        | 0 %        |
| Linux | 0.46 %     | 0.03 %     | 1.08 %     |
