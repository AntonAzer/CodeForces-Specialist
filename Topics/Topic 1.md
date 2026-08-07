# Topic 1: Implementation & Brute Force

Implementation is not an algorithm you memorize—it is a muscle you build. In Problems A and B, there is rarely a hidden trick. The problem statement simply tells you to do something, and your job is to translate those instructions into working code as fast as possible without bugs.

### What is Brute Force?
Brute force means trying every single possible combination to find the valid answer. If you look at the constraints and see they are very small (e.g., N <= 100), **do not waste time looking for a genius mathematical formula.** 

Write two or three nested loops, simulate the process, and take your Accepted (AC) verdict. Codeforces gives you 1 or 2 seconds, and a modern CPU can easily handle ~10^8 operations per second. Use that raw power to your advantage.

### The Two Pillars of Implementation

1. **Language Fluency:** C++ (or your chosen language) needs to be second nature. You cannot afford to pause in the middle of a contest to remember how to slice a string, sort an array, or write a custom comparator.
2. **The Edge Case Shield:** This is where most Wrong Answers (WA) come from. Always ask yourself these questions before hitting submit:
   - What happens if N = 1?
   - What if all numbers in the array are negative or zeros?
   - Are there out-of-bounds array indices?
   - Do I need `long long` instead of `int`?

### How to Train This Topic
- **The Goal:** Get an AC on the first try without any bugs or compilation errors.
- **The Drill:** Solve 30 to 50 problems rated between 800 and 900. 
- **The Benchmark:** Once you can consistently read, code, and solve these problems in under 10 to 15 minutes, you are ready to move on. Do not stay here longer than necessary once your hands are used to the code.

*(Note: Add your selected links to 800-900 rated implementation problem sheets or Codeforces tags here).*
