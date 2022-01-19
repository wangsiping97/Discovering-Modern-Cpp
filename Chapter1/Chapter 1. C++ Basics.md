# Chapter 1. C++ Basics

## 1.1 Our First Program

“In C++, every expression has a type. Sometimes we as programmers have to declare the type explicitly and other times the compiler can deduce it for us.”

“KDevelop is a free IDE from the KDE community written in C++. It is probably the most efficient IDE on Linux and integrates well with git, subversion, and CMake.”

Excerpt From: Peter Gottschling. “Discovering Modern C++, 2nd Edition.” Apple Books. 

## 1.2 Variables

```c++
double x = -1.5e6; // -1500000
```

- The non-decreasing length property:
  - char <= short <= int <= long <= long long
  - float <= double <= long double
  - Typical float: 32 bits; double: 64 bits; long double: 128 bits

### Intrinsic Types

“Using char or unsigned char for small numbers, however, can be useful when there are large containers of them.”

Excerpt From: Peter Gottschling. “Discovering Modern C++, 2nd Edition.” Apple Books. 

### Characters and Strings

```c++
char name[8] = "Herbert";
```

**Danger:** 

1. “These old C strings all end with a binary 0 as a char value. If the 0 is missing, algorithms keep going until the next memory location with a 0-byte is found. ”
2. Appending to strings would corrupting memory or cutting off  longer strings

Excerpt From: Peter Gottschling. “Discovering Modern C++, 2nd Edition.” Apple Books. 

C++ 14: differentiate char array and string with the suffix s, e.g., "Herbert"s. 

### Declaring Variables

**Declare variables as late as possible**

C++11 can deduce the type of a variable for us with `auto`. 

### Constants

Values already known during compilation --> enables optimizations

### Literals

“Every number with a dot or an exponent (e.g., 3e12 ≡ 3· 10^12) is considered a double.”

```c++
std::complex<float> z(1,3, 2.4), z2;
z2 = 2 * z; // Error: 2 is not float
z2 = 2.0f * z; // Correct
```

```c++
long double third1 = 0.3333333333333333333;     // may lose digits
long double third2 = 0.3333333333333333333l;    // accurate
```

“Integer literals starting with a zero are interpreted as octal numbers”

```c++
int o1 = 042; // 34
int h1 = 0x42; // 66
```

“C++14 introduces binary literals, which are prefixed with 0b or 0B.”

“To improve readability of long literals, C++14 allows us to separate the digits with apostrophes:”

Excerpt From: Peter Gottschling. “Discovering Modern C++, 2nd Edition.” Apple Books. 

**C++17** allows us to write hexadecimal floating-point literals: 

```c++
float f1 = 0x10.1p0f; // 16.0625 * 2^0 = 16.0625
double d2 = 0x1ffp10; // 511 * 2^10 = 523264
```

