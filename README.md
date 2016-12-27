# C-Simple Compiler
#### By Tzahi Argaman

Created as a project for **"Introduction to Compilation"** course.

The compiler with all its parts was planned and built to be used with [CSimple Programming Language](http://www.cs.ucsb.edu/~chris/teaching/cs160/projects/language.html) - The language which the compiler was made for, as introduced [here](http://www.cs.ucsb.edu/~chris/teaching/cs160/) by Prof. Christopher Kruegel.

Please read the CSimple Manual before using the compiler to understand its structure and requirements.

#### [CSimple Programming Language Manual](http://www.cs.ucsb.edu/~chris/teaching/cs160/projects/language.html)


### Compiler Checklist

- [x] Scanner (Lexer)
- [x] Parser
- [ ] Semantics
- [ ] Finished Compiler

---

## Getting Started

Fork or download the content of the repository to your computer.
The compiler source code can be found inside the `src` folder.

### Prerequisites

To compile the compiler (:confused:) you will need the following tools:
+ flex 2.5.35
+ bison (GNU Bison) 3.0.2
+ cc 4.8.4

### Installing

Open the folder which contains the `scanner.l` and `parser.y` and run the following commands **by order** inside your terminal:

``` c
lex scanner.l // creates 'lex.yy.c'
yacc parser.y -d // creates 'y.tab.c' & 'y.tab.h'
cc lex.yy.c y.tab.c -o compiler -ll // compiles the scanner and parser into `compiler`

```

Now you have your own CSimple Compiler!

### Running the Tests:
There are two ways to test the compiler;

1. Write C-Simple code input inside your terminal:
``` c
./compiler // execute the compiler runnable file, it now waits for input
```

2. Test the compiler using a test file with C-Simple code:
``` c
./compiler < test_file.c // run the compiler with the 'test_file.c' content
```
The input (whether it’s raw input or a test file) must be at least one procedure, which contains the rest of the code, for more info see [this part of the CSimple Manual](http://www.cs.ucsb.edu/~chris/teaching/cs160/projects/language.html#description-of-program-structure) which explains the structure of the CSimple Language.

For this reason, (code must contain at least one procedure and the last statement in the procedure must be a return statement) the minimum structure of an input code, even if the test subject does not concern procedures, will be as follows:
``` c
procedure foo() return integer
{
  * Input code *

  return 0;
}
```

## Built With

* [flex](https://github.com/westes/flex)  - The Fast Lexical Analyser
* [GNU Bison](https://www.gnu.org/software/bison/) - Parser generator

## Contributing

Work in progress...

## Versioning

Work in progress...

## Authors

* **Tzahi Argaman** - *Initial work* - [GitHub](https://github.com/argamanza) | [LinkedIn](https://il.linkedin.com/in/argamanza)

## License

Work in progress...

## Acknowledgments

* Mrs. Alona Kutsyy and Mr. Alexander Shkolnik, lecturers for "Introduction to Compilation" course @ [Sami Shamoon College of Engineering](http://www.sce.ac.il/eng/).
