# Topic 4: Time Complexity Reducers

When you hit the 1200+ rating mark, brute force will stop working. You will start seeing constraints like N = 200,000, meaning an O(N^2) double loop will give you a Time Limit Exceeded (TLE) verdict. 

You need to squash your time complexity down to O(N log N) or O(N). These three techniques are the ultimate bottlenecks solvers for Problem C.

### 1. Frequency Arrays (The O(1) Lookup)
Instead of nesting loops to count how many times an element appears, use the element's value as the *index* of a new array.
- **How it works:** If you see the number `5`, you just do `freq[5]++`. 
- **When to use:** When you need to count occurrences, find duplicates, or check if elements can form pairs.
- **Constraint Warning:** You can only use standard frequency arrays if the maximum value of the elements is around 10^7 or less. If elements go up to 10^9, you must use a `std::map` (which costs O(log N)) and personally I prefer maps.

### 2. Prefix Sums
If a problem asks you to calculate the sum of a subarray from index `L` to `R` multiple times, calculating it with a loop every time is O(N). If there are Q queries, your total time is O(N * Q), resulting in TLE.
- **How it works:** Precalculate a running total array where `prefix[i] = prefix[i-1] + arr[i]`. 
- **The Magic:** You can now answer ANY range sum query `[L, R]` instantly in O(1) time using the formula: `prefix[R] - prefix[L - 1]`.
- *Pro Tip:* Always use `1-based indexing` when working with prefix sums to avoid `Index Out of Bounds` errors when querying from the very beginning of the array.

### 3. Two Pointers & Sliding Window
This is the art of moving two indices (`L` and `R`) intelligently across an array to avoid double loops.
- **Two Pointers:** Often used on **sorted** arrays. Place one pointer at the start and one at the end. Move them inward based on a condition (e.g., finding two numbers that sum to X). 
- **Sliding Window:** Used on contiguous subarrays. Maintain a "window" of valid elements. As you expand the window to the right, if the condition breaks, shrink it from the left. This processes the entire array in O(N).

**Personally my understanding to both topics has improved a lot from LeetCode**

### How to Train This Topic
- **The Goal:** Recognize the constraints. If N = 2 * 10^5, immediately mentally ban O(N^2) solutions.
- **The Drill:** Solve 1100–1300 rated problems. Start with Prefix Sums, as they are the easiest to grasp. Then move heavily into Two Pointers, as it requires a bit more logical maturity to know exactly *when* to move which pointer.

