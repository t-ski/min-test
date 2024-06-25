# MinTest

A <ins>min</ins>imal <ins>test</ins> script in favour of lean unit testing with lean NodeJS projects.

<sub>**Download**</sub>

``` cli
curl -o min-test.js https://raw.githubusercontent.com/t-ski/min-test/main/min-test.js
```

<sub>**Via NPM**</sub> <sub>`package.json`</sub> <sub>→</sub> <sub>`npm i`</sub>
``` json
"scripts": {
  "prepare": "curl -o min-test.js https://raw.githubusercontent.com/t-ski/min-test/main/min-test.js"
}
```

### Usage

MinTest recursively scans and evaluates test files in the `./test` directory. Each file named according to the pattern `*.test.js` is a test file and subject to evaluation. The global scope defines the `test()` function that provides a simple, yet powerful (weak-deep-equal) assertion interface:

> Optionally, a different test directory path may be specified through the first positional CLI argument. 

``` cli
node min-test.js <test-directory-path>?
```

``` ts
test(actual: unknown, expected: unknown);
```

### Example

<sub>test/example.test.js</sub>
``` js
test(5 + 5, 10);            // ✅
test((() => 5 + 5)(), 10);  // ✅
test(5, "5");               // ✅

test(5 + 5, 9);             // ❌
```

##

<sub>&copy; Thassilo Martin Schiepanski</sub>
