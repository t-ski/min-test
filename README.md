# <ins>Min</ins>imal <ins>Test</ins>

A minimal test script for NodeJS that favours integration of lean unit testing capabiltiies into lean projects.

``` cli
node min-test.js <test-directory-path>?
```

The script recursively scans through a designated test directory. The path to the test directory can be provided as the first positional CLI argument (`./test/` by default). Each file whose name ends with `.test.js` is considered a test file and thus evaluated. Within each test file, the globally accessible `test()` function provides a simple, weak-deep-equal assertion interface:

``` ts
test(actual: unknown, expected: unknown);
```

## Example

``` js
test(5 + 5, 10);            // ✅
test((() => 5 + 5)(), 10);  // ✅
test(5, "5");               // ✅

test(5 + 5, 9);             // ❌

```

##

<sub>&copy; Thassilo Martin Schiepanski</sub>