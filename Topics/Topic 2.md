# Topic 2: Basic Math, Parity, & Bitwise Operations

CodeForces authors love hiding simple math inside complex stories. You do not need university-level calculus to reach a 1400 rating; you need sharp middle-school math intuition combined with programmer logic. 

### 1. Parity (Odd/Even Properties)
A huge portion of Div. 2 A and B problems can be solved just by looking at whether numbers are odd or even. 
- Odd + Odd = Even
- Even + Even = Even
- Odd + Even = Odd

**The Trick:** Always ask yourself, "If I apply the problem's operation, does the parity change?" Often, the parity is an **Invariant** (a property that never changes no matter how many operations you do), which instantly dictates if a solution is possible or not.

### 2. Modulo Arithmetic
When a problem asks you to output the answer "modulo 10^9 + 7", it's simply because the actual answer is too massive to fit in a 64-bit integer. Use these rules at every step to avoid overflow:
- **Addition:** `(A + B) % M = ((A % M) + (B % M)) % M`
- **Multiplication:** `(A * B) % M = ((A % M) * (B % M)) % M`
- *Warning:* Subtraction can result in negative numbers in C++, which messes up the modulo. Always use: `((A - B) % M + M) % M`.

### 3. Bitwise Operations
You do not need to be a bit-manipulation wizard, but you must know the core mechanics:
- **XOR (`^`):** The most frequently tested bitwise operator. Remember the golden rule: `X ^ X = 0`. If you XOR a number by itself, it destroys it. Also, `X ^ 0 = X`.
- **Bit Checking:** To check if the `i`-th bit of a number `N` is set to 1, use `(N >> i) & 1`.
- **Power of 2:** A fast way to multiply by 2 is `X << 1`, and to divide by 2 is `X >> 1`.

### 4. Basic Number Theory
- **GCD and LCM:** Do not write these from scratch. Just use C++'s built-in `std::gcd(a, b)`. For LCM, always use the formula: `LCM(a, b) = (a / std::gcd(a, b)) * b` (divide first to prevent integer overflow).
- **Prime Checking / Divisors:** You can check if a number is prime or find all its divisors in `O(sqrt(N))` time. You only need a loop running up to `i * i <= N`, not all the way to `N`.

### How to Train This Topic
**Get off the keyboard.** For math and parity problems, the solution is almost never found by staring at your IDE. Grab a pen and paper, write out the first 4 or 5 manual test cases, look for the pattern, and deduce the simple rule before writing a single line of code.

