# 🧩 PART 1: Arrays in Python — Foundation

### 1️⃣ What is an Array in DSA?

In DSA theory:

* **Array** = fixed-size, contiguous block of memory.
* Elements stored sequentially → fast index access: **O(1)**.

In **Python**, the equivalent structure is a **List** (dynamic array):

* It’s a **dynamic, resizable array**, not a linked list.
* Internally uses a **contiguous memory block** and **auto-resizes** when full (by allocating a new larger block and copying old elements).

---

### 2️⃣ Creating Arrays / Lists

```python
# Empty list
arr = []

# With elements
arr = [10, 20, 30, 40]

# Using list constructor
arr = list((1, 2, 3))

# From range
arr = list(range(5))   # [0,1,2,3,4]
```

✅ **Best Practice:** Prefer `list(range(n))` when you need sequential values.

---

### 3️⃣ Accessing & Indexing

```python
arr = [10, 20, 30, 40]
print(arr[0])   # 10
print(arr[-1])  # 40 (negative index → from end)
```

> **Indexing:** O(1) — direct memory offset access.

---

### 4️⃣ Updating Elements

```python
arr[2] = 99
print(arr)  # [10, 20, 99, 40]
```

✅ Works because lists are **mutable**.

---

### 5️⃣ Adding Elements

```python
arr.append(50)          # Add to end → O(1) amortized
arr.insert(2, 25)       # Insert at index 2 → O(n)
arr.extend([60, 70])    # Extend list → O(k)
```

**Time Complexity:**

| Operation  | Complexity     |
| ---------- | -------------- |
| `append()` | O(1) amortized |
| `insert()` | O(n)           |
| `extend()` | O(k)           |

---

### 6️⃣ Removing Elements

```python
arr.pop()        # Remove last → O(1)
arr.pop(2)       # Remove at index → O(n)
arr.remove(20)   # Remove by value → O(n)
del arr[1]       # Delete by index → O(n)
```

---

### 7️⃣ Slicing & Copying

```python
arr = [1, 2, 3, 4, 5]
print(arr[1:4])      # [2,3,4]
print(arr[:])        # Full copy
print(arr[::-1])     # Reverse copy
```

⚠️ **Slicing creates a new list**, not a view → O(k) time, O(k) space.

---

### 8️⃣ Searching

```python
arr = [10, 20, 30, 40]
print(30 in arr)           # True (linear scan)
print(arr.index(30))       # Returns index or ValueError
```

> Searching in unsorted array → **O(n)**.

If sorted, use **binary search (O(log n))**:

```python
import bisect
arr = [10, 20, 30, 40]
pos = bisect.bisect_left(arr, 30)  # 2
```

---

### 9️⃣ Iteration Techniques

```python
# Simple for loop
for x in arr:
    print(x)

# With index
for i in range(len(arr)):
    print(i, arr[i])

# With enumerate
for i, val in enumerate(arr):
    print(i, val)
```

✅ **`enumerate()`** = Pythonic + efficient for index-value loops.

---

### 🔟 List Comprehensions

Powerful shorthand for creating or transforming lists.

```python
squares = [x*x for x in range(6)]
evens = [x for x in range(10) if x % 2 == 0]
```

> List comprehensions are **faster** than for-loops due to internal optimizations.

---
