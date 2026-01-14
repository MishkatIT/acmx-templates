"# ACMX Templates

A collection of C++ templates for competitive programming, designed to streamline test case generation and brute force solution validation.

## 📁 Contents

- **gen.cpp** - Test case generator template
- **brute.cpp** - Brute force solution template

## 🎯 Purpose

These templates help competitive programmers to:
- Generate random test cases automatically
- Create brute force solutions for validation
- Test optimized solutions against brute force outputs
- Debug and verify algorithm correctness

## 📋 Prerequisites

- C++ compiler (g++ recommended)
- Basic understanding of competitive programming
- A `testcases/` directory in your working folder

## 🚀 Usage

### Test Case Generator (gen.cpp)

The generator creates random test cases and saves them to the `testcases/` folder.

**How it works:**
1. Generates test cases numbered from 10 onwards (10.in, 11.in, 12.in, etc.)
2. By default, creates 15 test cases
3. Uses Mersenne Twister random number generator for better randomness

**Customization:**
```cpp
// Modify the generation logic between the comments:
// modify from here
int n = rnd() % 100 + 1;  // Change this to your problem requirements
vector<int> v(n);
for (int i = 0; i < n; i++) {
    v[i] = rnd() % 1000;  // Adjust range as needed
    inFile << v[i] << " ";
}
inFile << '\n';
// end of modifications
```

**Parameters to adjust:**
- `testCase = 15` - Number of test cases to generate
- `generate(t + 10)` - Starting number for test case files
- Random ranges and constraints within the generation logic

**Compile and run:**
```bash
g++ -std=c++17 gen.cpp -o gen
./gen
```

### Brute Force Solution (brute.cpp)

The brute force solution reads test cases and generates answer files for validation.

**How it works:**
1. Reads `.in` files from the `testcases/` folder
2. Processes each test case with your brute force algorithm
3. Writes outputs to `.ans` files in the same folder
4. Starts from test case 10 and continues until no more files are found

**Customization:**
```cpp
// Modify the solution logic between the comments:
// modify from here
int n;
inFile >> n;
ansFile << n << '\n';
// end of modifications
```

**Features:**
- Includes debug macro support (define `LOCAL` for debugging)
- Pre-configured common constants (mod, N, inf, linf)
- Fast I/O setup

**Compile and run:**
```bash
# With debug support
g++ -std=c++17 -DLOCAL brute.cpp -o brute
./brute

# Without debug
g++ -std=c++17 brute.cpp -o brute
./brute
```

## 💡 Typical Workflow

1. **Setup**: Create a `testcases/` directory in your project folder
   ```bash
   mkdir testcases
   ```

2. **Generate test cases**: Customize and run `gen.cpp`
   ```bash
   g++ -std=c++17 gen.cpp -o gen && ./gen
   ```

3. **Create brute force solution**: Modify `brute.cpp` with a simple, correct solution
   ```bash
   g++ -std=c++17 brute.cpp -o brute && ./brute
   ```

4. **Validate optimized solution**: Compare your optimized solution's output against `.ans` files
   ```bash
   # Example: Compare outputs
   diff testcases/10.ans testcases/10.out
   ```

## 🔧 Configuration

### Constants (available in both templates)
```cpp
using ll = long long;
using ld = long double;
const ll mod = 1e9 + 7;
const ll N = 1e5 + 10;  // gen.cpp uses 1e5 + 10
const ll N = 2e5 + 10;  // brute.cpp uses 2e5 + 10
const ll inf = 1e9;
const ll linf = 1e18;
```

### File Numbering
Both templates start from file number 10. This allows you to reserve files 0-9 for manual test cases.

## 📝 Example

For a simple problem that sums an array:

**gen.cpp modification:**
```cpp
int n = rnd() % 100 + 1;  // 1 to 100 elements
inFile << n << '\n';
for (int i = 0; i < n; i++) {
    inFile << rnd() % 1000 << " ";
}
inFile << '\n';
```

**brute.cpp modification:**
```cpp
int n;
inFile >> n;
vector<int> arr(n);
ll sum = 0;
for (int i = 0; i < n; i++) {
    inFile >> arr[i];
    sum += arr[i];
}
ansFile << sum << '\n';
```

## 🤝 Contributing

Feel free to fork this repository and customize the templates for your needs. Contributions and improvements are welcome!

## 📄 License

This project is open source and available for competitive programming practice and education.

## 🔗 Related

This template works great with competitive programming tools like:
- [ACMX](https://github.com/searleser97/acmx) - Competitive programming tool
- [CP-Tools](https://github.com/agrawal-d/competitive-programming) - Various CP utilities

---

**Happy Coding! 🚀**" 
