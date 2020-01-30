# Statements \(Old\)

## Control Flow

* `if` statements allow executing a block of code conditionally, when a provided condition is true:

  ```text
  if condition {
      code;
  }
  ```

  These can contain an `else` clause which executes whenever the condition is false:

  ```text
  if condition {
      code;
  } else {
      code;
  }
  ```

  They can also contain any number of `else if` clauses:

  ```text
  if condition {
      code;
  } else if condition {
      code;
  } else {
      code;
  }
  ```

* `while` loops evaluate some condition first, then execute some code, and repeat as long their condition remains true.

  ```text
  while condition {
      code;
  }
  ```

* `do` ... `while` loops execute some code first, then evaluate a condition, and repeat as long their condition remains true.

  ```text
  do {
      code;
  } while condition;
  ```

* `for` loops
* Loops can use `break` to terminate a loop early, or `continue` to skip ahead to the next iteration of the loop.
* `goto` statements allow jumping execution to a label.
* Blocks / compound statements: `{ code; }`
* Assignment: `a = b;` `a += b;` `a -= b;` `a *= b;` `a /= b;` `a %= b;` `a &= b;` `a |= b;` `a ^= b;` `a <<= b;` `a >>= b;` `a <<<= b;` `a >>>= b;` `a <<<#= b;` `a >>>#= b;`
* Increment/decrement: `a++;` `a--;` `--a;` `++a;`
* Function call: `f();`

## Declarations

* `bank` declarations are used to reserve a bank of storage within the program, for holding variables, constants or code. Once a bank is declared, it can be selected with the `in` directive to use.

  ```text
  bank prg @ 0x8000 : [prg; 32768];
  ```

* `var` declarations are used for runtime variables that can be written to and possibly read back later.

  ```text
  var hp : u8;
  ```

* `const` declarations are used for constant read-only data that can be accesssed by the program.

  ```text
  const data : [u8] = [1, 2, 3, 4, 5];
  ```

* `let` declarations are used for compile-time expressions, which are non-addressable constants that substituted inline wherever they are referenced:

  ```text
  let x = 5;
  ```

* `func` declarations are used for functions that contain code which can be executed and called by the program.

  ```text
  func f() {
      a = a + 5;
  }
  ```

* label declarations are possible by placing a `:` colon after a name, they reference a particular position in the code.

  ```text
  func f() {
  loop:
      goto loop;
  }
  ```

* `namespace` declarations allow organizing various symbols into a specific named group:

  ```text
  namespace enemy {
      let MAX_ENEMIES = 8;
  }
  ```

## Directives

* `import` directives are used to bring symbols from other modules into the current module. After an import, all the public symbols from the other module are visible and can be referenced by name by the code.

  ```text
  import "banks"; // a module that defines a 'prg' bank, for code.
  import "nes"; // a module that defines a 'nes' namespace.

  in prg {
      func disable_screen() {        
          nes.ppu.ctrl = a = 0;
      }
  }
  ```

* `in` directives select a `bank` to be used for allocating parts of the program. `rom` banks \(or `prg` or `chr`\) can be used for reserving read-only constant data and executable code. `ram` banks can be used to reserve variable storage.

  ```text
  in prg {
      const data : [u8] = "HELLO WORLD\0";
  }

  in ram {
      var hp, mp, attack, defense, mana, gold : u8;
  }
  ```

TODO: missing things, more elaboration, better examples, etc

