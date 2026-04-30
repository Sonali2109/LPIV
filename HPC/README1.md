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
