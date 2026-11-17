Sylva JS 

A lightweight, high-performance JavaScript Engine Built from scratch in Rust.

Sylva JS is designed specifically to serve as the execution environment for Sylva, an upcoming AI-Native Web Browser. By rolling a custom engine, we bypass Heavy OS webviews, Achieving tighter memory control, lightning fast execution, and seamless integration with Sylva's custom Search Engine and Edge Computed AI backend. 

Unlike traditional tree-walk interpreters, Sylva JS is designed from Day one to operate as a high-performance Stack-Based Virtual Machine, heavily inspired by modern engine architectures like V8 and SpiderMonkey. 

1. Frontend: Parsing Pipeline
 > A Tokenizer that utilizes Rust's string slices (&str) to scan raw JavaScript source code without allocating new memory for every token. 
 > It implements a Top-Down Operator Precedence to efficiently parse JavaScript's complex expression rules, outputting a cleanly structured Abstract Syntax Tree (AST)
2. Middle-End: Bytecode Compiler 
 > The Bytecode emitter flattens the AST into a linear array of highly optimized VM instructions (Opcodes)
 > The Symbol Table resolves variable scopes and hoisting at a compile-time to eliminate expensive string lookups during runtime
3. Backend: Execution & Runtime
 > Using a highly optimized Stack-based Virtual Machine (VM) to execute bytecode with minimal overhead. 
 > Using NaN boxing technique, it packs 64-bit JavaScript values (pointers, Booleans, Nulls) into the unused bits of IEEE 754 double-precision float, radically improving CPU cache utilization. 
4. Interop & API
 > Native Rust implementations for built-in objects (Math, console, Array, etc.)
 > A robust FFI (Foreign Function Interface) bridging JavaScript runtime with Sylva's Core Rust Browser Backend and Search Engine.

 
