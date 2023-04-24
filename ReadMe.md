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
python measure.py
icoanalyzer experiment.hdf5
```

#### Results

- No data loss in three attempts on macOS
