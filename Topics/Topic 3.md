# Topic 3: C++ STL Mastery

To solve Problems C and D efficiently, you need the C++ Standard Template Library (STL) working for you, not against you. Writing your own sorting algorithms, binary searches, or dynamic arrays during a contest is a massive waste of time. 

The goal here is not to learn every feature of C++, but to master the tools that make implementation fast and painless.

### 1. `std::vector` (The Default Array)
Forget about standard C-style arrays (e.g., `int arr[100];`)(Note that I talk about in your level but C-styles array is faster in many things but has no helper operations and also needs to master the ordinary operations befor, if you read Grandmasters sols you usually see a global arrays, but it is not our step now). Use `std::vector` for everything.
- It resizes dynamically.
- It is easy to pass into functions.
- You can easily assign all elements to a specific value or sort it completely using `sort(v.begin(), v.end())`.

### 2. `std::set` & `std::map`
These are your best friends for uniqueness and frequencies, but they come with a warning label: **Every operation costs O(log N)**.
- **`std::set`**: Keeps elements sorted and strictly unique. Use it when you need to answer "Has this number appeared before?" or when you need to find the smallest/largest active element dynamically.
- **`std::map`**: Use this to count the frequency of massive numbers (e.g., up to 10^9) or strings. If constraints are small (N <= 10^5), use a standard Frequency Array instead of a map to avoid the `O(log N)` overhead.

### 3. `std::pair` & Custom Comparators
Many Greedy problems require you to sort data based on multiple conditions. 
- Use `std::pair<int, int>` to tie two pieces of data together (like a value and its original index).
- **Custom Sorting:** Learn how to write a custom comparator function for `std::sort`. For example, sorting an array of pairs by the second element in descending order. This is a mandatory skill for Div. 2 B and C.

### 4. `std::lower_bound` & `std::upper_bound`
Do not write a manual binary search just to find an element in a sorted array.
- `lower_bound`: Returns an iterator to the first element that is **greater than or equal to** a target.
- `upper_bound`: Returns an iterator to the first element that is **strictly greater than** a target.
- *Pro Tip:* Subtract `v.begin()` from the result to get the actual index in your vector.

### How to Train This Topic
- **The Goal:** Make STL syntax pure muscle memory. You should never have to Google "how to iterate through a map" during a contest.
- **The Drill:** Solve 1000–1200 rated problems that explicitly require sorting pairs, counting frequencies with maps, or querying sets. 

