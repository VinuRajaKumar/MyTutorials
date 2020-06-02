=============================
GNU Compiler Collection (GCC)
=============================
Historically, GCC used to stand for the GNU C Compiler, but since then the compiler has evolved to support several other languages aside from C, the current official meaning is **GNU Compiler Collection**. The term "GNU C Compiler" is still used sometimes in the context of C programming. It is, basically, a compiler suite, an integrated distribution of compilers for several major programming languages. These languages currently include C, C++, ADA, D, Go and many other languages.

Components of GCC
=================
GCC, specifically, have a number of programs that do the compilation work. There is a top-level program, called 'gcc', that is the compiler driver; it parses a myriad command line options and orchestrates the other phases of the compiler - the parser/analyzer, the optimizer, the assembler and the linker, typically (the preprocessor is not usually a separate phase these days, unless you request only preprocessing). It (the compiler driver) is quite a complex program, even though it never touches a C source file itself.

The part of a compiler that is specific to a particular language is called the “front end”. The language-independent component (code shared among the compilers for all supported languages) of GCC includes the majority of the optimizers, as well as the “back ends” that generate machine code for various processors.

Most of the compilers for languages other than C have their own names. The C++ compiler is G++, the Ada compiler is GNAT, and so on. When we talk about compiling one of those languages, we might refer to that compiler by its own name, or as GCC. Either is correct.

https://gcc.gnu.org/onlinedocs/gcc/G_002b_002b-and-GCC.html

Compiling with gcc and g++
==========================

Even though they automatically determine which backends (cc1 cc1plus ...) to call depending on the file-type, unless overridden with -x language, they have some differences.

The probably most important difference in their defaults is which libraries they link against automatically. According to GCC's online documentation link options and how g++ is invoked, ``g++`` is equivalent to ``gcc -xc++ -lstdc++ -shared-libgcc`` (the 1st is a compiler option, the 2nd two are linker options). This can be checked by running both with the -v option (it displays the backend toolchain commands being run).


the g++ default behavior is naturally aligned to a C++ development.

https://gcc.gnu.org/onlinedocs/gcc/Invoking-G_002b_002b.html
Compiling C++ Programs

C++ source files conventionally use one of the suffixes ‘.C’, ‘.cc’, ‘.cpp’, ‘.CPP’, ‘.c++’, ‘.cp’, or ‘.cxx’; C++ header files often use ‘.hh’, ‘.hpp’, ‘.H’, or (for shared template code) ‘.tcc’; and preprocessed C++ files use the suffix ‘.ii’. GCC recognizes files with these names and compiles them as C++ programs even if you call the compiler the same way as for compiling C programs (usually with the name gcc).

However, the use of gcc does not add the C++ library. g++ is a program that calls GCC and automatically specifies linking against the C++ library. It treats ‘.c’, ‘.h’ and ‘.i’ files as C++ source files instead of C source files unless -x is used. This program is also useful when precompiling a C header file with a ‘.h’ extension for use in C++ compilations. On many systems, g++ is also installed with the name c++.

When you compile C++ programs, you may specify many of the same command-line options that you use for compiling programs in any language; or command-line options meaningful for C and related languages; or options that are meaningful only for C++ programs. See Options Controlling C Dialect, for explanations of options for languages related to C. See Options Controlling C++ Dialect, for explanations of options that are meaningful only for C++ programs. 

