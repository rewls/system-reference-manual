# CLANG(1)

## NAME

- the Clang C, C++, and Objective-C compiler

## DESCRIPTION

- clang is a C, C++, and Objective-C compiler which encompasses preprocessing, parsing, optimization, code generation, assembly, and linking.

- Depending on which high-level mode setting is passed, Clang will stop before doing a full link.

- While Clang is highly integrated, it is important to understand the stages of compilation, to understand how to invoke it.

- These stages are:

	- Driver

		- The clang executable is actually a small driver which controls the overall execution of other tools such as the compiler, assembler and linker.

	- Preprocessing

		- This stage handles tokenization of the input source file, macro expansion, #include expansion and handling of other preprocessor directives.

		- The output of this stage is typically called a ".i" (for C) file.

	- Parsing and Semantic Analysis

		- This stage parses the input file, translating preprocessor tokens into a parse tree.

		- Once in the form of a parse tree, it applies semantic analysis to compute types for expressions as well and determine whether the code is well formed.

		- This stage is responsible for generating most of the compiler warnings as well as parse errors.

		- The output of this stage is an "Abstract Syntax Tree" (AST).

	- Code Generation and Optimization

		- This stage translates an AST into low-level intermediate code (known as "LLVM IR") and ultimately to machine code.

		- This phase is responsible for optimaing the generated code and handling target-specific code generation.

		- The output of this stage is typically called a ".s" file or "assembly" file.

		- Clang also supports the use of an integrated assembler, in which the code generator produces object files directly.

	- Assembler

		- This stage runs the target assembler to translate the output of the compiler into a target object file.

		- The output of this stage is typically called a ".o" file or "object" file.

	- Linker

		- This stage runs the target linker to merge multiple object files into an executable or dynamic library.

		- The output of this stage is typically called an "a.out", ".dylib" or ".so" file.

	- Clang Static Analyzer

		- The Clang Static Analyzer is a tool that scans source code to try to find bugs through code analysis.

## OPTION

### Stage Selection Options

- `-E`: Run the preprocessor stage.

- `-fsyntax-only`: Run the preprocessor, parser and type checking stages.

- `-S`: Run the previous stages as well as LLVM generation and optimization stages and target-specific code generation, producing an assembly file.

- `-c`: Run all of the above, plus the assembler, generating a target ".o" object file.  
