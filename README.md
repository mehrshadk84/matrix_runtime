# Matrix Multiplication Runtime Comparison

This project compares the runtime performance of two recursive matrix multiplication algorithms:  
- **DAC (Divide and Conquer)**  
- **Strassen’s Algorithm**

It measures execution times for square matrices of different sizes and visualizes the results.

---

## 📌 Features
- Generates random square matrices of sizes `2, 4, 8, ..., 256`.
- Multiplies them using **DAC** and **Strassen** algorithms.
- Measures execution time with configurable runs and recursion threshold.
- Plots results on a log-log scale for easy comparison.

---

## 📂 Code Structure
- **`measure_times()`**  
  Runs multiplication for different sizes and methods, returning average runtimes.

- **Main Execution (`__main__`)**  
  - Calls `measure_times()` with default parameters.  
  - Plots runtime curves using Matplotlib.

---

## ⚙️ Requirements
Make sure you have Python 3.x installed along with the following libraries:

```bash
pip install matplotlib numpy
```

---

## 🧩 Notes

The script assumes that helper functions exist:

random_matrix(n) → generates an n x n random matrix.

mult_with_padding(A, B, method, threshold) → multiplies matrices using the selected method.

You can adjust parameters:

SIZES → list of matrix sizes.

methods → tuple of algorithms (dac, strassen).

runs → number of repetitions for averaging runtime.

threshold → recursion cutoff size for hybrid multiplication.

---

# 📖Background
Divide and Conquer (DAC)

Splits each matrix into 4 submatrices of size n/2 x n/2.

Recursively computes 8 multiplications of these submatrices.

Combines the results into the final matrix.

Has a time complexity of O(n³), similar to the naive method, but with a recursive structure.

Strassen’s Algorithm

An optimized divide-and-conquer method introduced by Volker Strassen in 1969.

Reduces the number of recursive multiplications from 8 to 7, at the cost of additional additions/subtractions.

Achieves a time complexity of about O(n^2.81), faster than standard O(n³).

More efficient for large matrices, but overhead may make it slower for small ones.

Often implemented with a threshold: below a certain size, standard multiplication is used instead.

---
