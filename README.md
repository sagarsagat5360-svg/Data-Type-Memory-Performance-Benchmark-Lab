# Data-Type-Memory-Performance-Benchmark-Lab
[README (1).md](https://github.com/user-attachments/files/33493513/README.1.md)
# NumPy Data Type Memory & Performance Benchmark Lab

Benchmarks how NumPy dtype choice (int8 to int64, float16 to float64) affects memory usage, speed and precision on 1-million-element arrays.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](PASTE-YOUR-COLAB-LINK-HERE)

## Problem
Picking a dtype blindly either wastes memory or causes silent bugs such as integer overflow. This project measures the real trade-offs.

## Approach
1. Created the same 1M-element array in 7 dtypes (int8, int16, int32, int64, float16, float32, float64)
2. Recorded size, itemsize and nbytes for each in a table
3. Timed `sum` and `multiply` using `timeit`
4. Demonstrated integer overflow and float precision loss using `astype()`
5. Plotted memory vs time and wrote recommendations for choosing a dtype

## Results

![Benchmark chart](dtype_benchmark.png)

- int8 uses 8x less memory than int64 (0.95 MB vs 7.63 MB for 1M elements)
- float16 was the slowest dtype on CPU: [add your timing numbers here]
- Casting 200 to int8 wraps to -56, and a float16 sum of 1M values overflows to `inf`
- [Add one more finding from your own run]

## Key takeaway
Choose the smallest dtype that safely holds your data range and precision needs.

## Tech
Python, NumPy, pandas, Matplotlib, Google Colab

## Files
| File | Description |
|---|---|
| `numpy_dtype_benchmark_lab.ipynb` | Main notebook with all code, outputs and charts |
| `dtype_benchmark.png` | Saved benchmark charts |
| `requirements.txt` | Python dependencies |

## Run it
Click the Colab badge above and choose Runtime > Run all. No local setup needed.

To run locally:
```bash
pip install -r requirements.txt
jupyter notebook numpy_dtype_benchmark_lab.ipynb
```
