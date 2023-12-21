# Emscripten Tutorial - A Quick Guide

This README serves as a quick guide and reminder on how to set up and use Emscripten. Emscripten is a powerful tool that allows you to compile C and C++ code into WebAssembly (WASM). The power of WASM lies in its ability to run at near-native speed in web browsers, opening up a whole new realm of possibilities for web development.

## Getting Started

1. **Installation**: Download and install Emscripten. The installation process varies depending on your operating system (Linux, Windows, or Mac).

2. **Accessing Emscripten**: Use the Emscripten Compiler Frontend (emcc) to build your code. This can replace standard compilers like gcc or clang. Use `./emcc` or `./em++` on the command line. On Windows, the syntax is slightly different: `emcc` or `em++`.

3. **Command Prompt**: Open a command prompt to navigate to the Emscripten directory under the SDK. On Linux or macOS, open a Terminal. On Windows, open the Emscripten Command Prompt.

## Verifying Emscripten

Run `./emcc -v` to verify your Emscripten installation. If you see warnings about missing tools, refer to the Emscripten Development Environment documentation for debugging help.

## Running Emscripten

Compile your first C/C++ file to JavaScript using Emscripten. Here's a simple example:

```c
#include <stdio.h>

int main() {
  printf("hello, world!\n");
  return 0;
}
```

To compile this to JavaScript, use the command `./emcc test/hello_world.c`. This will generate two files: `a.out.js` and `a.out.wasm`. The latter is a WebAssembly file containing the compiled code, and the former is a JavaScript file containing the runtime support to load and execute it. Run them using node.js with the command `node a.out.js`.

## Notes

- Older versions of node.js may not support WebAssembly. In such cases, build with `-sWASM=0` to disable WebAssembly.
- If an error occurs when calling `emcc`, run it with the `-v` option to print out useful debug information.
- Some files from the `test/` folder must be run through the test harness itself. Refer to the Emscripten Test Suite for more information.

Remember, the power of WASM is its ability to bring high-performance applications to the web, making it a crucial tool for modern web development.