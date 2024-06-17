# Sequences
Script collection for data sequences

## Visualization
Data sequence visualization scripts

### Dynamic
Dynamic visualization for a data sequence

```bash
seq 0 31 | awk '{ print 50 * (1 + sin($1 / 5)) }' | dynamic
```

```
▄▅▆▇▇███████▇▆▆▅▄▃▂▁▁      ▁▁▂▃▄  45.85%
```

### Progress
Progress visualization for a data sequence

```bash
seq 16 | awk '{ print 50 * (1 + sin($1 / 4)) }' | progress
```

```
███████████████▌           62.37%
██████████████████▍        73.97%
█████████████████████      84.08%
███████████████████████    92.07%
████████████████████████▎  97.45%
████████████████████████▉  99.87%
████████████████████████▊  99.20%
███████████████████████▊   95.46%
██████████████████████▏    88.90%
███████████████████▉       79.92%
█████████████████▎         69.08%
██████████████▎            57.06%
███████████▏               44.59%
████████                   32.46%
█████▎                     21.42%
███                        12.16%
```

## Processing
Data sequence processing scripts

### SMA
Simple Moving Average

```bash
seq 0 31 | awk '{ print 50 * (1 + sin($1 / 5)) }' | sma | dynamic
```

```
▅▇██▆▄▁  ▁▃  40.94%
```

### Slope
Slope of a Linear Trend Line

```bash
seq 0 31 | awk '{ print 50 * (1 + sin($1 / 5)) }' | slope
```

```
-2.87654
```

> y = slope * x + intercept

```bash
seq 0 31 | awk -v slope=-2.87654 -v intercept=100 '{ print slope * $1 + intercept }' | dynamic
```

```
███▇▇▇▇▆▆▆▆▅▅▅▅▄▄▄▄▃▃▃▃▂▂▂▂▁▁▁   10.83%
```
