# Train/Test Split Strategy


We used `StratifiedShuffleSplit` on `uplift_label`:


| Label   | Group |
|---------|-----------------------------|
| 0       | Control – No conversion |
| 1       | Control – Conversion |
| 2       | Treated – No conversion |
| 3       | Treated – Conversion |


This maintains group balance in both sets, critical for fair uplift learning.
