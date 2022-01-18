# Kotlin Smart Calculator
Proyecto de evaluación para el título de Kotlin Developer en Jetbrains Academy. Consiste en realizar una calculadora con memoria para BigIntegers.

[![Kotlin](https://img.shields.io/badge/Code-Kotlin-blueviolet)](https://kotlinlang.org/)
[![LISENCE](https://img.shields.io/badge/Lisence-MIT-green)]()
![GitHub](https://img.shields.io/github/last-commit/joseluisgs/Kotlin-SmartCalculator)


![imagen](https://www.adesso-mobile.de/wp-content/uploads/2021/02/kotlin-einfu%CC%88hrung.jpg)

## Acerca de
Este proyecto de la academia Jetbrains fue realizado con el fin de evaluar la capacidad de desarrollo de Kotlin. Consiste en realizar una calculadora con Big Integers.

- [Kotlin Smart Calculator](#kotlin-smart-calculator)
  - [Acerca de](#acerca-de)
  - [Enunciado](#enunciado)
    - [Parte 1](#parte-1)
      - [Description](#description)
    - [Parte 2](#parte-2)
      - [Description](#description-1)
    - [Parte 3](#parte-3)
      - [Description](#description-2)
    - [Parte 4](#parte-4)
      - [Description](#description-3)
    - [Parte 5](#parte-5)
      - [Description](#description-4)
    - [Parte 6](#parte-6)
      - [Description](#description-5)
    - [Parte 7](#parte-7)
      - [Description](#description-6)
    - [Parte 7](#parte-7-1)
      - [Description](#description-7)
  - [Autor](#autor)
    - [Contacto](#contacto)
  - [Licencia](#licencia)

## Enunciado
### Parte 1
#### Description
Write a program that reads two integer numbers from the same line and prints their sum in the standard output. Numbers can be positive, negative, or zero.

### Parte 2
#### Description
Write a program that reads two numbers in a loop and prints the sum in the standard output. If a user enters only a single number, the program should print the same number. If a user enters an empty line, the program should ignore it.

When the command /exit is entered, the program must print Bye! , and then stop.

### Parte 3
#### Description
At this stage, the program should read an unlimited sequence of numbers from the standard input and calculate their sum. Also, add a /help command to print some information about the program. If you encounter an empty line, do not output anything.



### Parte 4
#### Description
At this stage, your calculator should support the addition + and subtraction - operators.

The program must calculate expressions like these: 4 + 6 - 8, 2 - 3 - 4, and so on. It must support both unary and binary minus operators. If the user has entered several same operators following each other, the program still should work (like Java or Python REPL).

Consider that the even number of minuses gives a plus, and the odd number of minuses gives a minus! Look at it this way: 2 -- 2 equals 2 - (-2) equals 2 + 2.

Modify the result of the /help command to explain these operations.

Decompose your program using methods to make it easy to understand and edit later.

### Parte 5
#### Description
Modify your program to handle different cases when the given expression has an invalid format. The program should print Invalid expression in such cases. The program must never throw the NumberFormatException or any other exception.

If a user enters an invalid command, the program must print Unknown command.

All messages must be printed without quotes.

Do not forget to write methods to decompose your program.


### Parte 6
#### Description
At this stage, your program should support variables. We suppose that the name of a variable (identifier) can contain only Latin letters. The case is also important; for example, n is not the same as N. The value can be an integer number or a value of another variable.

### Parte 7
#### Description
At this stage, your program should support for multiplication *, integer division / and parentheses (...). They have a higher priority than addition + and subtraction -. Do not forget about variables; they, and the unary minus operator, should still work. Modify the result of the /help command to explain all possible operators.

Here is an example of an expression that contains all possible operations:

3 + 8 * ((4 + 3) * 2 + 1) - 6 / (2 + 1)
The result is 121.

A general expression can contain many parentheses and operations with different priorities. It is difficult to calculate such expressions if you do not use special methods. Fortunately, there is a fairly effective and universal solution, using a stack, to calculate the most general expressions.

From infix to postfix

Earlier we processed expressions written in infix notation. This notation is not very convenient if an expression has operations with different priorities, especially when brackets are used. But we can use postfix notation, also known as reverse Polish notation (RPN). In this notation, operators follow their operands. See several examples below.

Infix notation 1:

3 + 2 * 4
Postfix notation 1:

3 2 4 * +
Infix notation 2:

2 * (3 + 4) + 1
Postfix notation 2:

2 3 4 + * 1 +
To better understand the postfix notation, you can play with a converter here.

As you can see, in postfix notation operations are arranged according to their priority and parentheses are not used at all. So, it is easier to calculate expressions written in postfix notation.

You can use a stack (LIFO) to convert an expression from infix to postfix notation. The stack is used to store operators for reordering. Here are some rules that describe how to create an algorithm that converts an expression from infix to postfix notation.

Add operands (numbers and variables) to the result (postfix notation) as they arrive.
If the stack is empty or contains a left parenthesis on top, push the incoming operator on the stack.
If the incoming operator has higher precedence than the top of the stack, push it on the stack.
If the incoming operator has lower or equal precedence than or to the top of the stack, pop the stack and add operators to the result until you see an operator that has a smaller precedence or a left parenthesis on the top of the stack; then add the incoming operator to the stack.
If the incoming element is a left parenthesis, push it on the stack.
If the incoming element is a right parenthesis, pop the stack and add operators to the result until you see a left parenthesis. Discard the pair of parentheses.
At the end of the expression, pop the stack and add all operators to the result.
No parentheses should remain on the stack. Otherwise, the expression has unbalanced brackets. It is a syntax error.

Calculating the result

When we have an expression in postfix notation, we can calculate it using another stack. To do that, scan the postfix expression from left to right:

If the incoming element is a number, push it into the stack (the whole number, not a single digit!).

If the incoming element is the name of a variable, push its value into the stack.
If the incoming element is an operator, then pop twice to get two numbers and perform the operation; push the result on the stack.

When the expression ends, the number on the top of the stack is a final result.

### Parte 7
#### Description
Description
At this stage, your program must support arithmetic operations (+, -, *, /) with very large numbers as well as parentheses to change the priority within an expression.

There are two ways to solve it. As an easy way, you may use the standard class for working with large numbers, just correctly apply it to your solution. If you want to practice algorithms, you may develop your own class for large numbers and implement algorithms for the listed arithmetic operations.


## Autor

Codificado con :sparkling_heart: por [José Luis González Sánchez](https://twitter.com/joseluisgonsan)

[![Twitter](https://img.shields.io/twitter/follow/joseluisgonsan?style=social)](https://twitter.com/joseluisgonsan)
[![GitHub](https://img.shields.io/github/followers/joseluisgs?style=social)](https://github.com/joseluisgs)

### Contacto
<p>
  Cualquier cosa que necesites házmelo saber por si puedo ayudarte 💬.
</p>
<p>
    <a href="https://twitter.com/joseluisgonsan" target="_blank">
        <img src="https://i.imgur.com/U4Uiaef.png" 
    height="30">
    </a> &nbsp;&nbsp;
    <a href="https://github.com/joseluisgs" target="_blank">
        <img src="https://distreau.com/github.svg" 
    height="30">
    </a> &nbsp;&nbsp;
    <a href="https://www.linkedin.com/in/joseluisgonsan" target="_blank">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/ca/LinkedIn_logo_initials.png/768px-LinkedIn_logo_initials.png" 
    height="30">
    </a>  &nbsp;&nbsp;
    <a href="https://joseluisgs.github.io/" target="_blank">
        <img src="https://joseluisgs.github.io/favicon.png" 
    height="30">
    </a>
</p>


## Licencia

Este proyecto está licenciado bajo licencia **MIT**, si desea saber más, visite el fichero [LICENSE](./LICENSE) para su uso docente y educativo.