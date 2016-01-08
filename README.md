# JAVA FROM SCRATCH

## Comments in Java:
Before we start, we should discuss comments in Java. When writing code, sometimes it is useful to write english text along side it. Comments are used to explain complex lines or blocks of code to other developers or even to your future self. Comments are ignored by the Java compiler. You can write pretty much anything you want and Java won't care.

```java
// when you see two forward slashes together in Java, the text after the slashes is a single-line comment.
CODE CODE CODE //Even if there was code before the slashes, the text after the slashes is a comment.
// single-line comments cannot be stopped once started. To write code again, you need to create a new line.

/* multi-lined comments however start with the characters '/' and '*' and ends with '*' and '/' put together.
    In a multi-lined comment, you can write as many lines as you want, but 
    the 
    comment 
    won't
    end
    unti
    you 
    type: */
```

It's important to know what is code and what is a comment as I will be using comments to help explain things in this document.

## This is a class:
```java
public class Main
{
}
```

- In Object Oriented languages, everything is either an object or a value.
- values are things like: `int`, `char`, `boolean`
- Objects are things that you create using `new` (eg. `new StringBuilder`)
- Objects are complex things, whereas values are usually quite small, simple things.
- Most objects are defined using classes. A class is like a blueprint for an object.
- If that is confusing (it usually is to most), don't worry, you'll learn about it later.
- Methods and properties have an ability to be `static`. 
- I won't try to explain static, because I think you need to learn about classes and objects first.
- But conveniently, using static methods without actually learning what they are allows you to write code without needing to learn the fundimentals of Object Oriented Programming (OOP) first.
- This allows us to focus on learning the basics of programming first.

When you run a Java application, Java will run a method of your choice (usually called main).
This method must be static, and it must take one parameter (String args[])

## Here is a method:

```java
public static void main(String args[])
{
}
```

A method is also known in some languages as a `function` or `routine`.

##### `public`
The word public is known as an access modifier. When your programs become more complex, you will start seeing code in more than one class. Splitting your code into classes (when done properly) helps to keep your codebase smaller and easier to understand - just take my word for it.

The most common access modifier are: `public` and `private`. For now, we will use `public` always. When you learn concepts such as encapsulation, you will start to understand the benefit of using `private  ` as well as the other access modifiers.

##### `static`
As mentioned before, java looks for a static method to run, this is how you declare a method to be static. The word static **must** come **after** the access modifier. *If a method should not be static, you simply don't write this word*.

##### `void`
This is the *return type* of your method. Java looks for a method with no return type and a method with no return type uses the keyword `void`.  
If you wanted your method to return a value, you would put the type of that value here (eg. `String` or `Boolean` or `int`)

##### `main`
This is the name of your method. Method names are usually **verbs** and can consist of one or more words. (`getInput`, `reorderList`, `getRandomNumber`, `explode`, `joinValues`).  
Method names should be **camelCase** in Java, and I prefer methods with at least two words since they tend to be more self-explanatory than single word methods (especially for static methods).  
There are exceptions to the rule of method names, and `main` is one of them.

##### `(...)`
All methods have brackets after them. the `...` indicates that there is usually stuff inside those brackets. Those "stuff" are called parameters and parameters are optional (you can have 0 or more of them).  
An example of a method without parameters looks like this: `public static void myMethod() {...}`

##### `String args[]`
This is the parameter(s). Here there is only 1 parameter. Parameters are in this format:  
```
{TYPE} {variableName}, {TYPE} {variableName}, ...
```
The commas are used to separate each parameter and arrays are special in that an array of integers would read `int myNumber[]`. By putting `[]` after the variable name, Java knows you expect an array of integers not just one integer.

You are allowed to ask for 0 or more parameters. The code calling your method must provide values for each of your parameters when doing so; don't worry, if they don't Java will throw compiler errors.

##### `{ ... }`
The curly brackets signify a **"block"**. A block is a multiline section of a file that contains lines of executable code. This is where you write your actual code. Keep in mind that every `{` must be accompanied by a `}` to end the block.

## Here is a variable declaration:
```java
String myVariable;
```

- This line will go inside a code block. 
- `String` indicates the type of this variable. Once set, the type cannot change.   
- `myVariable` is the name of the variable. Once again, it is written in **camelCase**.
- Every executable line of code inside a code block must end with a `;`. 
- Although a compiler is usually smart enough to guess when you forgot it, it won't fix it for you because sometimes, a line of code can take multiple lines in a file, and if that was what you were trying to achieve, the compiler might be hiding your bugs from you.

#### variables can be declared and assigned at the same time:
```java
String myVariable = "This is the value of my variable";
```
#### or separately:
```java
String myVariable;
// some code goes here...
myVariable = "This is the value of my variable";
```
This is useful if you need to calculate your value before you can set it, but it is rarely used. It's just nice to know you can do this sometimes.

A variable can be set and re-set multiple times. This is useful for progressively changing a variable value:
```java
int number = 5;
number = number + 5; //number = 10
System.out.println(number);
number = number * 2; //number = 20
//ask for a new number
int newNumber = BIO.getInt();
number = number + newNumber; //number is 20 plus the number given by the user.
System.out.println(number);
```

It is important to note the difference between declaring a variable, and assigning to a variable. You cannot assign to a variable that has not yet been declared, and although you can re-assign values to a variable, you cannot redeclare a variable.

## Lets write some code:
**just a quick note, `System.out.println(val)` is a method that takes any value (usually a string) and displays it in the console window.**
```java
public class Program 
{
    public static void main(String args[]) 
    {
        String message = "Hello world!";
        System.out.println(message);
    } 
}
```
It is a tradition to write a "hello world" application for every first application in any language. In most languages, the simplest thing to do is to write out a string, so whilst we are still unsure of how to write "bootstrap" our application, we attempt to write the simplest logic that we can visually test in order to verify that we have written the rest of the code correctly.

Had we written a more complex piece of logic, the errors and problems that we are looking out for may have been caused by that logic instead of the bootstrapping code/process. We could have written this code as one line, but I wanted to show variable *declaration*, *assignment* and *usage* in action.

In our case, we can take this application and attempt to run it. If we mispelled a word like `public` or if our java runtime was attempting to call a method named `execute` due to some sort of misconfiguration somewhere else, we would safely know the application was not working because we would not be able to see our **"Hello world"** message.

## Methods being called by methods:
TODO...

## This is an if statement:
```java
if(5 + 10 == 15)
{
    System.out.println("Five plus ten is fifteen!");
}
```
If statements start with the word `if` followed by brackets `(...)`. Inside the brackets should be an **expression**.  
An expression is one line of code that returns a `Boolean` value (that is `true` or `false`).
Here are some examples of expressions:

- `true`
- `false`
- `true == false`
- `true == true`
- `5 == 10`
- `myVariable == 20`
- `myVariable < 100`
- `myBooleanVariable`
- `functionThatReturnsABoolean()`
 
Any variable that has a type of `Boolean` or function call that returns a `Boolean` or even just the keywords `true` and `false` are expressions. However, most of the time, these are the least useful types of expressions. An expression can get interesting when using **Equality and Relational Operators** (more later).

### Code Blocks:
After any if statement, is usually a code block `{...}`. If the code inside the if statement will simply be one line of code, the curly braces may be ignored, and the line that follows the if statement is treated as the block of code. The proceeding line of code is treated as outside of the if statement.

```java
if(false)
    System.out.println("I pooped myself.");
System.out.println("Hello world.");
```
In the above snippet of code, the program evaluates the expression `false` and refuses to run the line of code directly after it. However, the message "Hello world." will be printed to the console.

It is common to use indentation to separate code blocks from one another in order to clearly visualise **scope** as discussed further on.

#### Don't be fooled by new lines and indentation:
```java
if(false) System.out.println("I pooped myself."); System.out.println("Hello world.");
```
The above code is exactly the same as before. A line of code in Java is terminated by a `;`. This is why it is easy to get confused when using this short hand syntax as a beginner. Especially when you are not fully accustomed to best practices regarding proper white-spacing (using new lines, spaces, and tabs appropriately). 

### Equality and Relational Operators
In Java, operators can do a fair amount of things. There is a list of valid operators listed on their site: https://docs.oracle.com/javase/tutorial/java/nutsandbolts/opsummary.html.   
#### Here is a list of Equality and Relational operators:

- ==      Equal to
- !=      Not equal to
- \>       Greater than
- \>=      Greater than or equal to
- <       Less than
- <=      Less than or equal to

operators are used in this format: `{value1} {operator} {value2}` where `value1` could be a variable, or a raw value such as `10` or `"a string value"`. As mentioned before, Java contains values types and objects. Technically, this is an expression:
```java
new StringBuilder() == new StringBuilder()
```
However, when working with objects, most operators will not work and others may not work as expected. For example, the above expression compares the location in memory of both objects and verifies if they are in the same location. This will be false.

### Here are conditional operators:

- &&      Conditional-AND
- ||      Conditional-OR

Conditional operators can be used to chain expressions together to create longer expressions. In order to explain these, I'll keep the expressions simple in my examples.
##### Conditional-OR: 
Checks to see if the left expression is true, if not, then checks to see if the right expression is true. If either of these expressions are true, the final result will be true, otherwise, will be false.

- `true || false` => `true`
- `false || true` => `true`
- `false || false` => `false`
- `true || true` => `true`
 
##### Conditional-AND: 
Checks if the left expression is false, if not, then checks to see if the right expression is false. If either of these expressions are false, the final result will be false, otherwise, will be true.

- `true && false` => `false`
- `false && true` => `false`
- `false && false` => `false`
- `true && true` => `true`

##### Brackets() and NOT!:
Firstly, I want to talk about NOT. In Java, `!` is the symbol for NOT. You put it before any expression, and it reverses the value of that expression. Here are some examples:

- `!true` => `false`
- `!false` => `true`
- `!false && true` => `true`
- `!false || false` => `true`
- `!true && true` => `false`

Just like in maths, writing long expressions can get quite confusing. Similar to BODMAS, each operator has its priority which affects how expressions are evaluated. For example:  

- `true || (true && false && true)` => `true`
- `(true || true) && false && true` => `false`
 
In the first example, all the Conditional-AND's are executed first: `true && false && true ==> false`. Then the Conditional-OR: `true || false ===> true`. Yet in the second example, the Conditional-OR is executed first: `true || true ==> true` and then the Conditional-AND's: `true && false && true ==> false`.

For my final trick, I want to show how brackets and NOT can work together when you want to check if two things are false. If you recall, both `true && true` and `true || true` will return true. Lets give each of these values a name: `isLoud` and `isAfterMidnight`. We want to know if our neighbours are doing ok; we like to party, but we've been told its ok so long as its not loud after midnight.
```java
Boolean neighboursAreOkay = !(isLoud && isAfterMidnight);
//reads: neighboursAreOkay if NOT isLoud AND isAfterMidnight.
//same as: Boolean neighboursAreOkay = !isLoud && !isAfterMidnight;
```
So what did I just write? If it is loud and it is after midnight, our neighbours are NOT okay. But we don't want to know when they are NOT okay, we want to know when they ARE okay. Since there is no operator that can take two `true`'s and return a `false`, we have to improvise. So when are the neighbours okay? when they are not NOT okay (I hope you are following). We make the assumption that the neighbours are either okay or not. They can't be sort of okay so if we try to calculate if the neighbours are not okay: `isLoud && isAfterMidnight` and we find out the answer is false, that means they are okay and the variable `neiboursAreOkay` should be true. By wrapping the expression in brackets and including a `!` before it, we take whatever value `isLoud && isAfterMidnight` gives us and return the opposite. Lets test the scenarios:

| isLoud  | isAfterMidnight | isLoud && isAfterMidnight | neighboursAreOkay |
|---------|-----------------|---------------------------|-------------------|
| `true`  | `true`          | `true`                    | `false`           |
| `true`  | `false`         | `false`                   | `true`            |
| `false` | `true`          | `false`                   | `true`            |
| `false` | `false`         | `false`                   | `true`            |

## The magic of scope:
When you declare a variable, it belongs to a thing called 'scope'. Scopes are like russian dolls, they nest into one another. When you try to access a variable, the program will look in the current scope, and if it can't find it, it will step out to the parent scope (outer doll) and look there until there are no more dolls to find. If that variable can't be found anywhere, the program would crash; fortunately, Java is good at detecting problems related to scope when it compiles and it will give you an error instead of building your application.

The outermost scope in an application is usually the class itself; however we have not yet learnt how to put "variables" in the class scope. The next scope is the method itself. After the method, if statements, and other statements such as loops which have their own **code blocks** will introduce their own scopes.

### Here are some scopes:
```java
public class Program 
{
    //SCOPE#A
    public static void main(String args[]) 
    {
        Int funcVariable = 10;
        //SCOPE#A1
        if(3 + 4 == funcVariable) //false
        {
            Int ifVariable = 1;
            //SCOPE#A11
        }
        else if(4 + 12 == 412) //false
        {
            Int ifVariable = funcVariable + 2; //ifVariable = 12
            //SCOPE#A12
        }
        else //true
        {
            Int ifVariable = 3;
            funcVariable = 1000;
            //SCOPE#A13
            if(false)
            {
                Int nestedIfVariable = funcVariable + ifVariable + 10; //nestedIfVariable = 1013
                //SCOPE#A131
            }
        }
        
        Int funcVariable2 = funcVariable + 30; //funcVariable2 = 1030
    } 
}
```
As mentioned before: it is common, and it is encouraged, to use indentation to help us visualise scope. 

Next to each assignment/re-assignment of a variable that includes the use of another variable, I have added a comment to show what the value of that variable will be after the line has been executed. A program will run through your code from top to bottom, line by line. As it reads, it will naturally enter and exit the scopes shown in the above code snippet.

We can read and interpret the code by reading the method we are executing from top to bottom with our eyes, keeping track of variables and their values in our minds. Interpreting is the act of reading code as a machine would in order to understand the code and even predict its outcomes. Remember, code blocks after if statements that evaluate to false will be skipped; so don't bother reading them when interpreting.

Even though we know that certain blocks of code will not execute in this program, the compiler will still be able to tell us if errors would occur had those blocks executed. The code above is valid compiles without errors; what can we infer from this?

- Variables can be declared and assigned in any scope.
- Variables can be accessed by the expression of any if statements in that scope.
- Variables from an outer scope can be accessed by its inner scopes.
- You can declare two variables with the same name as long as each declaration belongs to separate scopes that are not nested within one another.
- Variables from an outer scope can be re-assigned a value by any inner scope.
- Variables from an outer scope can be accessed by its inner-inner.. scopes also (as deep as you want to go).
- Even after leaving the scope where a variable has been re-assigned, the variable keeps its new value.

Oh, and remember how methods can have parameters? This method has a parameter called `args` and when the function is being executed, `args` is already declared as a variable and assigned a value. The same rules apply to this variable as any other variable.

Here are some things that you can't do:  
>Attempt to do these things in your own java program and compile after each change in order to see the errors you recieve from the Java compiler.

- Variables cannot be re-declared in the same scope, or within any of its child scopes.
- Even if you declare a variable after a scope has been opened and closed, the declaration is invalid if any  child scope already declared or will later declare the same variable.
- Variables that have been declared in a child scope cannot be accessed by an outer scope.
- When calling another method from a given scope, that method does not inherit your scope, it instead is given its own fresh scope (with its class as the parent scope).

>When you start to learn about class fields (not covered in this document), you should re-visit this section and experiment to see how the class' scope affects the function's scope.

>If you find this section hard to grasp, read it again, theorise and test your understanding of scopes, and keep re-visiting this section as you need to. Understanding scope is very important for interpreting your own code and being able to debug problems. Fortunately, there isn't much more to scopes in Java than what is written above.

>Unfortunately, the rules of scope are not always the same across other languages; Javascript is known for having its own scope rules that catch out most developers who may know other languages, but are new to Javascript. Fortunately, C, C#, C++, Java and most other object oriented languages have the same rules regarding scopes.

## Loops:
Loops are useful, powerful and dangerous. Loops allow us to write code once and run that code multiple times. Imagine you needed to write out numbers 1 through 100. You could write this:
```java
System.out.println(1);
System.out.println(2);
System.out.println(3);
System.out.println(4);
//.... (etc) ....
System.out.println(100);
```
That's 100 lines of code right there! Or we can learn to love loops. However, there is a dark side: loops can go on for ever and never stop. This is hardly ever the intention of the developer, but it is really easy to create infinite loops; too easy. With enough testing and sense checking, you'll be fine, but always keep an eye out for infinite loops. (read more here: https://www.cs.umd.edu/~clin/MoreJava/ControlFlow/infinite.html)

### This is a while loop:
```java
    while( expression )
    {
        //code goes here.
    }
```

### This is a do-while loop:
```java
    do
    {
        //code goes here.
    } while( expression )
```

### This is a for loop:
```java
    for(int i = 0; i < 10; i++)
    {
        //code goes here.
    }
```
`for(a;b;c)`
```java
    int i = 0; //a
    while(i < 10){ //b
        //code goes here
        i++; //c
    }
```
