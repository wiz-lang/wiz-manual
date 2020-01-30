# Introduction

The reference manual for **Wiz**, a high-level assembly language.

Wiz is an assembly language for writing low-level code, that aims to be user-friendly and have a modern high-level syntax.

Wiz has several high-level programming constructs to enable more efficient development and better organization: if/while/for statements, expression-style syntax for runtime instructions, functions, modules, namespaces, compile-time expression folding, and a type system. At the same time, Wiz is an assembler which can interface directly with platform-specific hardware such as registers, memory, and I/O ports.

The intended result is a language that has a bunch of nice organizational conveniences, while still having the ability to run on extremely limited hardware, such as old 8-bit and 16-bit game consoles. Wiz is intended for when even something like C is not really an option to write efficient programs, but you still want a slightly nicer environment to write low-level code.

This language avoids the mnemonics and restricted syntax of other assemblers and replaces it with a new syntax, while still mapping directly to machine code. It gives the direct control like any other assembly language, but with the syntactic flavoring of a higher-level language.

**More information soon...**

_\(NOTE: everything in this document intends to describe the as-yet-unreleased language revamp + C++ compiler rewrite, and not the earlier version of the Wiz language that has a compiler written in D. This is large revision of the language. I'm drafting some manual text here, but not sure when I'll release the rewritten language. So, for now, check out the D version of Wiz on the wiz-lang github, and keep posted for a future time when I eventually release the remake, and possibly remove this disclaimer!\)_

_\(NOTE: this document is a heavy work-in-progress\)_

