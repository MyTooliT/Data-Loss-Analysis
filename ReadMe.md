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

##### Third Version

- Collect data for a longer time (three minutes instead of 10 seconds) (commit [`9530a279`](https://github.com/MyTooliT/Data-Loss-Analysis/commit/9530a279dd74cd6aaf080c744a07dc1c1e8e2048))

| OS    | 1. Attempt | 2. Attempt                           | 3. Attempt                             |
| ----- | ---------- | ------------------------------------ | -------------------------------------- |
| macOS | 33.09 %    | Error (CAN Controller Read Too Late) | 33.68 % (CAN Controller Read Too Late) |
| Linux | 33.93 %    | 34.07 %                              | 33.43 %                                |

##### Fourth Version

- Collect data for an even longer time (10 minutes) (commit [`b26b447d`](https://github.com/MyTooliT/Data-Loss-Analysis/commit/b26b447d903514fe65a56f44073f747df549f54c))

| OS    | 1. Attempt | 2. Attempt | 3. Attempt |
| ----- | ---------- | ---------- | ---------- |
| Linux | 33.72 %    | 33.81 %    | 33.68 %    |

##### Fifth Version

- Collect data for 10 minutes
- Decrease sample rate (1681 Hz)
- Commit [`4a33699e`](https://github.com/MyTooliT/Data-Loss-Analysis/commit/4a33699e71d0783c0604458a627313e0c3619d5c)

| OS    | 1. Attempt | 2. Attempt | 3. Attempt |
| ----- | ---------- | ---------- | ---------- |
| Linux | 0.02 %     | 0.03 %     | 0.03 %     |
| macOS | 0.0 %      | 0.0 %      | 0.0 %      |
