# Topic 5: Binary Search & Binary Search on Answer

You already know what standard Binary Search is: finding a target number in a sorted array in O(log N) time instead of O(N). But standard binary search alone won't get you to a 1400 rating. 

What will get you there is a technique called **Binary Search on Answer**. This is arguably the most powerful algorithmic pattern for Div. 2 C and D problems.

### 1. The Paradigm Shift (Guessing the Answer)
Instead of trying to logically deduce or construct the exact optimal answer (which might require complex logic), what if you just **guessed** the answer?
- If I guess the answer is `X`, can I write a simple function to check if `X` is possible?
- If `X` is valid, maybe I can find a better (smaller/larger) answer.
- If `X` is invalid, then anything worse than `X` is also invalid.

### 2. The Monotonicity Requirement
For Binary Search on Answer to work, the problem's search space must be "monotonic". This means if you test all possible answers from minimum to maximum, their validity will look like a solid block of `False` followed by a solid block of `True` (or vice versa):
`False, False, False, True, True, True`

Once it becomes `True`, it stays `True`. Your job is to binary search the exact boundary where it flips.

### 3. The `check(mid)` Function
This is the heart of the technique. You separate the problem into two parts:
1. **The Binary Search:** Define your bounds `L` (minimum possible answer) and `R` (maximum possible answer, usually a huge number like 10^14). Calculate `mid = L + (R - L) / 2`.
2. **The Checker:** Write a boolean function `check(mid)` that simulates if `mid` is a valid answer. This function usually uses a Greedy approach and runs in O(N).
3. If `check(mid)` is true, you update `R = mid` (or `L = mid` depending on what you are optimizing). 

Your total time complexity becomes `O(N * log(Search Space))`, which easily passes the 2-second time limit.

### 4. Keyword Triggers
When you see these phrases in a problem statement, your brain should immediately scream "Binary Search on Answer":
- *"Minimize the maximum..."*
- *"Maximize the minimum..."*
- *"Find the smallest possible X such that..."*
- *"What is the maximum amount of Y you can get..."*

### How to Train This Topic
- **The Goal:** Build the instinct to stop looking for a direct math formula and start thinking, "Can I just check if a guessed answer works?"
- **The Drill:** Solve 1200–1400 rated problems explicitly tagged with "binary search". Focus heavily on writing clean `check()` functions and mastering how to update your `L` and `R` boundaries so you do not get stuck in infinite loops (`Time Limit Exceeded`).

