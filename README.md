# javascript-zero-to-advance

JavaScript from Zero to Advance

Module 0 — Orientation: What JavaScript Is and Why It Exists

- History & motivation
- The browser wars (Netscape/Microsoft), Brendan Eich, 10-day creation, naming (Mocha → LiveScript → JavaScript)
- The "Java" association myth and why it persists
- Standardization: ECMA-262, TC39, ECMAScript vs JavaScript
- Versioning: ES3, ES5 (2009), ES6/ES2015 and yearly releases
- Where JS runs
- Engines: V8 (Chrome/Node), SpiderMonkey (Firefox), JavaScriptCore (Safari)
- Browser runtimes, server/standalone runtimes (Node.js, Deno, and Bun), and edge/serverless runtimes (such as Cloudflare Workers)
- The host environment concept: JS core + host APIs (DOM, fs, fetch, etc.)
- Interpreted vs JIT-compiled — how V8 actually executes code (baseline + optimizing compiler, deopt)
- How a JS file gets executed
- Parsing → AST → bytecode → JIT → machine code
- The call stack, heap, event loop (conceptual preview — full treatment later)
- The language's design philosophy
- Prototype-based, multi-paradigm, dynamically typed, single-threaded + event loop
- "Good parts" vs historical warts (why `==` is dangerous, `var` hoisting, etc.)
- Goal: Understand what you're learning and where it lives before writing a line.

Module 1 — Setting Up and First Principles

- Running JS: browser console, Node REPL, `.js` files, `node file.js`
- `"use strict"` and module vs script mode
- How to read errors: stack traces, `ReferenceError` vs `TypeError`
- Statements vs expressions
- Semicolons, ASI (automatic semicolon insertion) — the real rules
- Comments, whitespace, identifiers, reserved words
- Case sensitivity, Unicode in identifiers

Module 2 — Values, Types, and Coercion (the foundation everything sits on)

- Primitive types: `undefined`, `null`, `boolean`, `number`, `bigint`, `string`, `symbol`
- The `typeof` operator and its famous quirks (`typeof null === "object"`)
- Numbers deep dive
- IEEE-754 double precision — why `0.1 + 0.2 !== 0.3`
- `NaN`, `Infinity`, `-0`, `Number.MAX_SAFE_INTEGER`
- `parseInt` vs `Number()` vs unary `+`
- Strings — immutability, UTF-16, surrogate pairs, template literals
- Booleans and truthiness — falsy values list, why `[]` and `{}` are truthy
- `null` vs `undefined` — semantics and when each appears
- Type coercion
- Implicit vs explicit
- `==` vs `===` — the full coercion algorithm, when `==` is acceptable
- ToPrimitive, `valueOf`, `toString`, `Symbol.toPrimitive`
- `+` overloading (string concat vs numeric add)
- Equality: `Object.is` vs `===` vs `==`
- Goal: Never be surprised by a type conversion again. This module prevents 80% of beginner bugs.

Module 3 — Variables, Scope, and Hoisting

- `var` vs `let` vs `const` — semantics, temporal dead zone, block vs function scope
- Hoisting: what actually gets hoisted (declarations, not initializations), function declarations vs expressions
- The scope chain and lexical scoping
- Global scope, module scope, function scope, block scope
- The global object (`window`/`globalThis`) and why polluting it is bad
- Closures — definition, mechanics, classic use cases (counters, private state, memoization)
- IIFE and why it existed before modules
- Shadowing and naming collisions

Module 4 — Operators and Control Flow

- All operators: arithmetic, assignment, comparison, logical, bitwise, ternary, nullish coalescing (`??`), optional chaining (`?.`), spread/rest (`...`)
- Short-circuit evaluation and its idioms (`x || default`, `x ?? default`)
- `if/else`, `switch` (and fall-through pitfalls), `try/catch` preview
- Loops: `for`, `while`, `do...while`, `for...in` (objects), `for...of` (iterables)
- `break`, `continue`, labeled statements
- Truthy/falsy in conditions and guard clauses

Module 5 — Functions (the heart of JS)

- Function declarations vs expressions vs arrow functions
- Parameters, arguments, default parameters, rest parameters
- `this` — the full rules: default binding, implicit (method), explicit (`call`/`apply`/`bind`), `new`, arrow functions (lexical `this`)
- `arguments` object vs rest params
- Higher-order functions, callbacks
- Pure functions, side effects, immutability mindset
- Recursion and stack overflow
- Closures revisited in function context
- Immediately Invoked Function Expressions (IIFE)
- Function length, `name`, `toString`

Module 6 — Objects

- Object literals, property access (dot vs bracket), computed keys
- Shorthand properties and methods
- References vs values — how objects are passed and copied (shallow)
- Object methods: `Object.keys/values/entries/assign/freeze/seal/create/getPrototypeOf`
- Property descriptors (`writable`, `enumerable`, `configurable`) and `Object.defineProperty`
- Getters and setters
- Destructuring (objects and arrays, nested, defaults, renaming)
- Spread and rest with objects
- `Object.is`, deep vs shallow equality

Module 7 — Arrays and Iteration

- Array creation, length, sparse arrays
- Mutating vs non-mutating methods (crucial distinction)
- Mutating: `push`, `pop`, `shift`, `unshift`, `splice`, `sort`, `reverse`, `fill`, `copyWithin`
- Non-mutating: `slice`, `concat`, `map`, `filter`, `reduce`, `flat`, `flatMap`, `join`, `find`, `findIndex`, `some`, `every`, `includes`, `indexOf`
- `reduce` in depth — the most powerful and misunderstood method
- Iteration protocols: iterables, iterators, `Symbol.iterator`, generators
- `for...of` vs `forEach` vs classic `for` — performance and semantics
- Array destructuring and swapping
- `Array.from`, `Array.isArray`, typed arrays (preview)

Module 8 — Prototypes and the Object Model

- Prototype chain — how property lookup actually works
- `__proto__` vs `Object.getPrototypeOf` vs `prototype` (the three confusing things)
- Constructor functions and `new` — what `new` does step by step
- `Object.create` and prototype-based inheritance
- ES6 `class` syntax — syntactic sugar over prototypes, `extends`, `super`, static methods, private fields (`#`)
- Mixins and composition vs inheritance
- `instanceof` and how it works internally
- `Object.prototype` methods: `hasOwnProperty`, `toString`, `isPrototypeOf`
- Goal: Understand that JS has no real classes — everything is prototype chains. This unlocks reading any JS codebase.

Module 9 — Errors and Debugging

- `Error` types: `SyntaxError`, `ReferenceError`, `TypeError`, `RangeError`, `EvalError`, `URIError`
- `throw`, `try/catch/finally`, custom error classes
- Error propagation and stack traces
- Debugging: `console.*` methods, `debugger`, breakpoints, devtools basics
- Defensive programming: validating inputs, failing fast

Module 10 — Asynchronous JavaScript (deep)

- The single-threaded model and why async exists
- The event loop — call stack, task queue (macrotasks), microtask queue, render queue; run-to-completion
- Callbacks and "callback hell"
- Promises
- States, `then`/`catch`/`finally`, chaining, error propagation
- `Promise.all`, `allSettled`, `race`, `any`
- Creating promises, promisification
- `async`/`await` — how it desugars to promises, error handling with try/catch
- Microtasks vs macrotasks — the ordering rules with examples
- `setTimeout`, `setInterval`, `queueMicrotask`
- Concurrency vs parallelism in JS
- AbortController and cancellation patterns (language-level)
- Goal: Predict the exact output order of any async snippet. This is where most developers stay shallow.

Module 11 — Modules

- Script vs module mode
- CommonJS (`require`/`module.exports`) — Node's historical system
- ES Modules (`import`/`export`) — static analysis, live bindings, tree-shaking implications
- Default vs named exports, re-exports, namespace imports
- Dynamic `import()` and code splitting concept
- Circular dependencies
- `import.meta`

Module 12 — Advanced Language Features

- Symbols — unique keys, well-known symbols (`Symbol.iterator`, `Symbol.toPrimitive`, etc.)
- Generators — `function*`, `yield`, lazy evaluation, `yield*`
- Iterators — building custom iterables
- Map, Set, WeakMap, WeakSet — when to use over plain objects; memory/GC implications
- Proxies and Reflect — meta-programming, traps, use cases (validation, logging)
- Tagged template literals
- Regular expressions — syntax, groups, flags, lookahead/lookbehind, `match`/`replace`/`exec`, named groups
- Dates — `Date` object quirks, timestamps, `Intl` for formatting
- JSON — `parse`/`stringify`, revivers/replacers, pitfalls
- Bitwise operators — real use cases (flags, performance)
- `eval` and `Function` constructor — why to avoid them

Module 13 — Memory, Performance, and the Engine

- Garbage collection basics (mark-and-sweep), memory leaks (unintended closures, globals, detached DOM — conceptual)
- The heap and stack — what lives where
- Hidden classes / shapes and why object property order matters for V8
- Inline caching and megamorphic code (conceptual)
- Deoptimization triggers (changing types, `delete`, etc.)
- Profiling with `console.time`, `performance.now()`, Node `--prof` (intro)
- When optimization matters vs premature optimization

Module 14 — Language Patterns and Idioms

- Module pattern, revealing module pattern
- Factory functions vs constructors vs classes
- Currying and partial application
- Debounce, throttle (language-level implementations)
- Memoization
- Observer/pub-sub pattern (plain JS)
- Command, strategy, singleton (plain JS)
- Functional patterns: map/filter/reduce pipelines, composition, `pipe`/`compose`
- Immutability patterns and structural sharing concept

Module 15 — Edge Cases, Warts, and "You Don't Know JS" Topics

- ASI traps, `==` coercion table, `NaN` comparisons
- Floating point edge cases
- `this` in every context recap
- Hoisting gotchas
- `delete` operator behavior
- `with` statement (why it's banned)
- Octal literals, legacy syntax
- Automatic boxing (`"str".length` — what happens)
- `Array.prototype.sort` default lexicographic behavior
- Sparse arrays and `forEach` skipping holes
- Numeric separators, `BigInt` interop with `Number`

Module 16 — Tooling Around the Language (light, not ecosystem)

- How JS is linted (ESLint concepts), formatted (Prettier)
- What a transpiler does (Babel) and why (target older engines)
- What a bundler does (concept only — full treatment later)
- Source maps
- The `package.json` and `node_modules` concept (just enough to run code)
- Semantic versioning basics

Module 17 — Capstone Projects (language-only)

These use only JavaScript (run in Node or browser console), no frameworks:

- Utility library — implement `map`, `filter`, `reduce`, `debounce`, `throttle`, `deepClone`, `deepEqual` from scratch
- Promise implementation — build a Promises/A+ compliant `Promise` from scratch
- Event emitter — pub/sub with `on`/`off`/`once`/`emit`
- Router/state machine — pure JS, no DOM needed (test via console)
- Async task queue — run N async tasks with concurrency limit, using promises
- Custom iterable + generator — e.g., a lazy range, infinite sequence
- Regex-based parser — e.g., parse a simple expression grammar

- Each project forces you to use closures, prototypes/classes, async, iterators, and error handling together.
