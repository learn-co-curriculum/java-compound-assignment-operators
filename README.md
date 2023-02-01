# Compound Assignment Operators

## Learning Goals

- Learn about compound assignment operators.
- Show how they work within memory using the browser-based Java Visualizer.

## What is a Compound Assignment Operator?

A **compound assignment operator** combines both an arithmetic operator, like
the `+` operator and the `-` operator, with the assignment operator `=`. It is a
shortcut way of writing certain expressions. Consider the following table of
compound assignment operators:

| Operator | Description                                 |
|----------|---------------------------------------------|
| `++`     | Increment                                   |
| `--`     | Decrement                                   |
| `+=`     | Addition Compound Assignment Operator       |
| `-=`     | Subtraction Compound Assignment Operator    |
| `*=`     | Multiplication Compound Assignment Operator |
| `/=`     | Division Compound Assignment Operator       |
| `%=`     | Modulus Compound Assignment Operator        |

These operators can be applied to numerical data types, like `int` and
`double`. Let's look at the increment and decrement operators first. But to help
us, consider the following variables when reading about each operator:

```java
int firstNumber = 20;
int secondNumber = 10;
```

- `++` is the increment operator. The increment operator is a unary operator
  and increases the value of the single operand by 1:
  - `firstNumber++` returns `21`.
  - Notice that the increment operator is placed directly after the variable
    name with no space between the variable name and the operand.
- `--` is the decrement operator. The decrement operator is a unary operator and
  decreases the value of the single operand by 1:
  - `secondNumber--` returns `9`
  - Notice that the decrement operator is placed directly after the variable
    name with no spaces between the variable name and the operand.

Note that both the increment and decrement operators operate on the operand
and assign it the new value. For example:

```java
firstNumber++; 
```

Has the exact same result as:

```java
firstNumber = firstNumber + 1; 
```

Another thing we should note about the increment and decrement operators is that
the operator could be placed directly before or after the variable. In the
examples above, we placed the operators after the variable. But we could have
also done this:

```java
++firstNumber;
--secondNumber;
```

When we place the operator before the variable, it will still have the same
result as before: `++firstNumber` will return `21` and `--secondNumber` will
return `9`. But order still matters! Let's take a look at an example of when
the placement of the increment or decrement operator would make a difference:

```java
int result = ++firstNumber;
System.out.println(result);

// Reset firstNumber to 20
firstNumber = 20;
result = firstNumber++;
System.out.println(result);
```

Now let's look at the output of the code above:

```text
21
20
```

So why are the outputs different? When the first line is run with the `++`
preceding the variable, Java will first perform the operation of
`firstNumber = firstNumber + 1;` before assigning the value of `firstNumber`
to `result`. The next time when the increment operator is used is in the
format of `firstNumber++`. When the `++` follows the variable, Java will
access the value of `firstNumber` before completing the increment. This is
because:

```java
result = firstNumber++;
```

is equivalent to

```java
result = firstNumber;
firstNumber = firstNumber + 1;
```

Therefore, `result` will be assigned the value 20 before `firstNumber` is
incremented.

To avoid these types of issues, it is best to not combine the assignment
operator, `=`, with the increment or decrement operators in the same statement.

Now let's discuss the other compound assignment operators:

- `+=` is the addition compound assignment operator. It is a binary operator
  where the value of the expression on the right-hand side will be added to the
  variable on the left-hand side of the operator and then stored in that
  variable. Consider the example:
  - `firstNumber += secondNumber;` is the same as
    `firstNumber = firstNumber + secondNumber;`
  - In the example above, the addition compound operator will first add the
    value of `secondNumber` to the value stored in `firstNumber` and then
    re-assign the result of that expression to `firstNumber`. So after the
    statement has been executed,`firstNumber` will have a value of 30.
  - The addition compound assignment operator is an abbreviated statement of
    variable = variable + right-hand expression.
  - To see this played out in memory, consider the following:

    <iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%20firstNumber%20%3D%2020%3B%0A%20%20%20%20%20%20int%20secondNumber%20%3D%2010%3B%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20firstNumber%20%2B%3D%20secondNumber%3B%0A%20%20%20%20%20%20System.out.println%28firstNumber%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=3&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

- `-=` is the subtraction compound assignment operator. It is a binary operator
  where the value of the expression on the right-hand side will be subtracted
  from the variable on the left-hand side of the operator and then stored in
  that variable. Consider the example:
  - `firstNumber -= secondNumber;` is the same as
    `firstNumber = firstNumber - secondNumber;`
  - In the example above, the subtraction compound operator will first subtract
    the value of `secondNumber` from the value stored in `firstNumber` and then
    re-assign the result of that expression to `firstNumber`. So after the
    statement has been executed,`firstNumber` will have a value of 10.
  - The subtraction compound assignment operator is an abbreviated statement of
    variable = variable - right-hand expression.
  - To see this played out in memory, consider the following:

    <iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%20firstNumber%20%3D%2020%3B%0A%20%20%20%20%20%20int%20secondNumber%20%3D%2010%3B%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20firstNumber%20-%3D%20secondNumber%3B%0A%20%20%20%20%20%20System.out.println%28firstNumber%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=3&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
  
- `*=` is the multiplication compound assignment operator. It is a binary
  operator that multiples the value of the expression on the right-hand side
  with the variable on the left-hand side of the operator and then stores the
  result in that variable. Consider the example:
  - `firstNumber *= secondNumber;` is the same as
    `firstNumber = firstNumber * secondNumber;`
  - In the example above, the multiplication compound operator will first
    multiply the value of `secondNumber` with the value stored in `firstNumber`
    and then re-assign the product of that expression to `firstNumber`. So after
    the statement has been executed,`firstNumber` will have a value of 200.
  - The multiplication compound assignment operator is an abbreviated statement
    of variable = variable * right-hand expression.
  - To see this played out in memory, consider the following:

    <iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%20firstNumber%20%3D%2020%3B%0A%20%20%20%20%20%20int%20secondNumber%20%3D%2010%3B%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20firstNumber%20*%3D%20secondNumber%3B%0A%20%20%20%20%20%20System.out.println%28firstNumber%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=3&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

- `/=` is the division compound assignment operator. It is a binary operator that
  divides the variable on the left-hand side of the operator with the value of the
  expression on the right-hand side of the operator. It then will store the result
  in the variable on the left-hand side. Consider the example:
  - `firstNumber /= secondNumber;` is the same as
    `firstNumber = firstNumber / secondNumber;`
  - In the example above, the division compound operator will first perform the
    division of `firstNumber / secondNumber` and then re-assign the quotient of
    that expression to `firstNumber`. So after the statement has been executed,
    `firstNumber` will have a value of 2.
  - The division compound assignment operator is an abbreviated statement of
    variable = variable / right-hand expression.
  - To see this played out in memory, consider the following:

    <iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%20firstNumber%20%3D%2020%3B%0A%20%20%20%20%20%20int%20secondNumber%20%3D%2010%3B%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20firstNumber%20/%3D%20secondNumber%3B%0A%20%20%20%20%20%20System.out.println%28firstNumber%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=3&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>
  
- `%=` is the modulus compound assignment operator. It is a binary operator
  that takes the variable on the left-hand side of the operator mod the value of
  the expression the right-hand side of the operator. Remember, the modulus or
  mod operator will return the remainder value of dividing two numbers. Once the
  expression has been evaluated, it will be stored in the variable on the
  left-hand side of the operator. Consider the example:
  - `firstNumber %= secondNumber;` is the same as
    `firstNumber = firstNumber % secondNumber;`
  - In the example above, the modulus compound operator will first perform
    `firstNumber % secondNumber` and then re-assign the result of that
    expression to `firstNumber`. So after the statement has been executed,
    `firstNumber` will have a value of 0.
    - It is 0 because 20 / 10 is 2 with no (or 0) remainder.
  - The modulus compound assignment operator is an abbreviated statement of
    variable = variable % right-hand expression.
  - To see this played out in memory, consider the following:

    <iframe width="800" height="500" frameborder="0" src="https://pythontutor.com/iframe-embed.html#code=public%20class%20Main%20%7B%0A%20%20%20%20public%20static%20void%20main%28String%5B%5D%20args%29%20%7B%0A%20%20%20%20%20%20int%20firstNumber%20%3D%2020%3B%0A%20%20%20%20%20%20int%20secondNumber%20%3D%2010%3B%0A%20%20%20%20%20%20%0A%20%20%20%20%20%20firstNumber%20%25%3D%20secondNumber%3B%0A%20%20%20%20%20%20System.out.println%28firstNumber%29%3B%0A%20%20%20%20%7D%0A%7D&codeDivHeight=400&codeDivWidth=350&cumulative=false&curInstr=3&heapPrimitives=nevernest&origin=opt-frontend.js&py=java&rawInputLstJSON=%5B%5D&textReferences=false"> </iframe>

## Resources

- [Java, How To Program (Early Objects), Tenth Edition](https://learning.oreilly.com/library/view/java-how-to/9780133813036/ch04lev1sec12.html#ch04lev1sec12)
