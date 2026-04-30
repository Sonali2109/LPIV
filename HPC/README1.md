1.txt :
Parallel Bubble Sort  --->
    👉 Normal bubble sort:
    Compare adjacent elements
    Swap if needed
    👉 Parallel version:
    #pragma omp parallel for
    ✔ Multiple threads run loop together
    ✔ Faster than normal (but still not best)
2. Parallel Merge Sort --->
  👉 Steps:
  Divide array into 2 parts
  Sort both parts in parallel
  Merge them :
  #pragma omp parallel sections
  ✔ Each section runs on different thread
  ✔ Much faster than bubble sort

📊 ⏱️ TIME COMPLEXITY
🔹 1. Bubble Sort
    👉 Worst / Average Case:
    O(n²)
    👉 Why?
    Outer loop runs n times
    Inner loop runs n times
    So: n × n = n²
    👉 Parallel effect:
    OpenMP speeds execution practically
    BUT theoretical complexity still O(n²)
🔹 2. Merge Sort
    👉 Time Complexity:
    O(n log n)
    👉 Why?
    Divides array into halves → log n levels
    Each level does merging → O(n)
    👉 So:
    n × log n = O(n log n)
    👉 Parallel effect:
    Sorting halves runs simultaneously
    So faster in real execution

📦 💾 SPACE COMPLEXITY
🔹 Bubble Sort
    O(1)
    👉 Why?
    No extra memory
    Only swapping elements
🔹 Merge Sort
    O(n)
    👉 Why?
    Uses extra array temp[1000] for merging

==========================================================================================================================================================================================================================================================================================================================================================

🎯 SUMMARY TABLE
Algorithm	Time	Space
BFS	O(V + E)	O(V)
DFS	O(V + E)	O(V)

==========================================================================================================================================================================================================================================================================================================================================================

Here’s a **clear, exam-ready explanation** of your Parallel Reduction code 👇

---

# 📊 ⏱️ TIME COMPLEXITY

## 🔹 Overall Time Complexity

```text
O(n)
```

---

## 🔹 WHY?

👉 Your loop runs:

```cpp
for(int i = 0; i < n; i++)
```

✔ Every element is processed **once**
✔ Operations inside loop:

* comparison (min, max)
* addition (sum)

👉 These are **constant time operations (O(1))**

---

## 🔹 So:

```text
Total = n × O(1) = O(n)
```

---

## 🔹 PARALLEL EFFECT

👉 With OpenMP:

```cpp
#pragma omp parallel for
```

✔ Work is divided among threads

👉 If `p` threads:

```text
Time ≈ O(n / p)
```

⚠ BUT in theory:
👉 Complexity is still written as **O(n)**

---

# 📦 💾 SPACE COMPLEXITY

## 🔹 Space Complexity

```text
O(1)
```

---

## 🔹 WHY?

👉 Only variables used:

* `min_val`
* `max_val`
* `sum`
* `avg`

✔ No extra data structures
✔ No recursion
✔ No additional memory

---

## 🔹 Note (Important)

👉 Even though threads use private copies (due to reduction):

```cpp
reduction(min:min_val)
```

✔ These are temporary
✔ Do NOT increase asymptotic space

👉 So still:

```text
O(1)
```

---

# 🎯 FINAL SUMMARY

| Complexity    | Value  |
| ------------- | ------ |
| Time          | O(n)   |
| Parallel Time | O(n/p) |
| Space         | O(1)   |

---

# 💬 VIVA ANSWER (PERFECT)

👉 *“The time complexity is O(n) as each element is processed once. With parallel execution, it reduces to approximately O(n/p), where p is the number of threads. The space complexity is O(1) since only a constant number of variables are used.”*

---

# 🧠 EASY MEMORY

👉 Time → O(n)
👉 Parallel → faster
👉 Space → O(1)

==========================================================================================================================================================================================================================================================================================================================================================


