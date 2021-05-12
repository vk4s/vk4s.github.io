---
title: "Learn Dart Programming"
date: 2021-05-12T16:28:37+05:30
draft: false
author: Vikash Patel
tags: ["Dart", "Programming"]
categories: ["Tutorial"]
featuredImage: >-
  https://images.unsplash.com/photo-1576504164753-8fd338cd450b?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=727&q=80
---

Good Evening,
Here are the Hands-on notes for Dart Programming Language.  
I created these notes when I was learning Dart Language. So, these notes might help you too.
You can use these notes as a quick reference to Syntax and Demo.  
I've covered almost every fundamental concept of Dart in this article.

![](https://images.unsplash.com/photo-1576504164753-8fd338cd450b?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=727&q=80)
Photo by Birmingham Museums Trust

---

# 1. Basics

## 1.1 The Main Function

Every Dart program starts execution from `main()` functions.

### The syntax of main function

_We use this version when we want to use command line arguments._

```dart
void main(List<String> args){
    // do your stuff here
}
```

Or simple version  
_Generally we use this version of main._

```dart
void main(){
    // do your stuff here
}
```

### Demo

```dart
void main() {
  // say hello world
  print("Hello World!");
  // print some numbers, integer expression
  print(1 * 2 + 34 - 12 / 5);
  // print double
  print(2.53);
  // boolean
  print(true);
}
```

---

## 1.2 Data Types

Literals in Dart.

```dart
// literals in Dart
"Dan"; // String literal
23; // int literal
45.6; // double literal
true; // bool literal
```

There are 4 built-in data types in Dart.

| SN  | Data Type | Description            |
| --- | --------- | ---------------------- |
| 1.  | int       | Integer value          |
| 2.  | double    | Floating point value   |
| 3.  | String    | String value           |
| 4.  | bool      | `true` , `false` value |

### Syntax creating variables in Dart

**Use explicit way to declare the variable.**

`typename variable_name;`

Or initialize while creating.  
`typename variable_name = initial_value;`

```dart
int intVariable;
int anotherIntVariable = 111;
String name = "Vikas";
double pi = 3.14;
bool isdeveloper = true;
```

**Use implicit way to declare the variable.**

Use `var` to create any type of variable.  
`var variable_name;`

Or initialize while creating.  
`var variable_name = intial_value`;`

### Demo

**Note: _In Dart all the data types are objects and their initial value is `null`._**

Create the variables

```dart
  // numbers: int
  int score = 90;
  // store hexadecimal value
  int hexValue = 0xEAEAEA;

  // numbers: double
  double length = 24.6;
  double exponentValue = 1.4e5;

  // String
  String name = "Dave";

  // boolean
  bool going = false;

  // use var
  var name2 = "Vikas"; // String
  var age = 20;        // int
  var score2 = 45.6;   // double
  var isHere = true;   // bool
  var exp = 2.5e6;     // exponential (double)
  var hex2 = 0xEC43AB; // hex (int)
  var data;            // will have null
```

Print the values

```dart
print(score);        //int
print(hexValue);     //int
print(length);       //double
print(exponentValue);//double
print(going);        //bool
print(name);         //String
print(name2);        //String
print(age);          //int
print(score2);       //int
print(isHere);       //bool
print(exp);          //double
print(hex2);         //int
print(data);         //null value
```

---

## 1.3 String and String Interpolation

Ways to define a String variable

```dart
 // ways to define string
  String s1 = 'Vikas'; // with single quote
  String s2 = "Dave"; // with double quote
  String s3 = "It's Easy"; // can use both
  String s4 = 'It\'s Easy'; // excape sequence
  String s5 = 'This is a very very long string '
      'and exceeding the line.'; // long string
  // auto concatenation of strings
```

String Interpolation

```dart
// Normal Concatenation
String name = "Vikas";
String msg = name + ", We are heading to the west";

// Interpolation
String msg2 = "$name We are heading to the west";
String msglen = "Length of msg = ${msg2.length}";

// Print
print(msg2);
print(msglen);
```

We can interpolate any data type with String in `print(...)` using `$varname`.

```dart
int BoxLength = 123;
double BoxWeight = 4522.4545;
print("Length of box = $BoxLength \nWeight of Box = $BoxWeight");
```

---

## 1.4 Constant and Final Variables

In dart we can create constants using
-> final
-> const

1. **final vs const:**

- `final` variable can only be set once and it is initialized when accessed
- `const` is internally final in nature but it is a `compile-time constant`  
   -> i.e. it is initialized during compilation

2. Instance variable can be final but cannot be constant
3. If you want a Constant class level then make it
   `static const` .

### Demo

```dart
void main() {
  // final
  final city = "Toronto";
  // or
  // final String city = "Toronto";
  // city = "NY"; // Error: Can't assign to the final variable 'city'.

  const PI = 3.1415;
  const double gravity = 9.8;
}
```

Class level constant

```dart
class Circle {
  final color = "RED"; // OK
  // const PI = 3.1415; // Not OK
  static const PI = 3.1415; // OK
}
```

**Only static fields can be declared as `const`.
Try declaring the field as `final`, or adding the keyword `static`.**

---

---

# 2. Control Statements

These statements are use to control the execution flow of the program and add various logics to the program.

## 2.1 If - Else Statements

Simple condition checking.  
**Syntax**

#### IF alone

```dart
if(condition){
    // block 1
    // execute the code
}
```

When the condition is `true` the code inside `block 1` gets executed.
Otherwise nothing happens to the code inside `block 1`.

#### IF and ELSE together

```dart
if(condition){
    // block 1
    // execute the code
} else{
    // block 2
    // execute the code
}
```

#### IF-ELSE ladder

```dart
if(condition){
    // block 1
    // execute the code
} else if(condition2){
    // block 2
    // execute the code
} else if(condition3){
    // block 3
    // execute the code
}
.
.
.
else if(condition n){
    // block n
    // execute the code
} else{
    // block last
    // execute the code
}
```

When the condition is `true` the code inside the respective `block` gets executed. Otherwise `block last` is executed.

### Demo

```dart
void main() {
  var salary = 250000;
  if (salary > 200000) {
    print("You, can get the Credit Card");
  } else if (salary > 150000) {
    print("You can apply for the Credit Card");
  } else {
    print("You cannot get the Credit Card");
  }
}
```

Check code inside `01 basics/05if_else.dart`.

---

## 2.2 Conditional Expression

Conditional expression is a simple alternative to `if-else`.  
There are two conditional expressions

1. **`condition ? expr1 : expr2;`**  
   returns `expr1` if condition is true else returns `expr2`
   ```dart
   int a = 12, b = 45;
   print("Small Number = ${(a < b) ? a : b}");
   int c = (a < b) ? a : b;
   print("Small Number = $c);
   ```
2. **`expr1 ?? expr2`**  
   if `expr1` is not-null, returns its value; otherwise, evaluates and returns the value of `expr2`

   ```dart
   int x, y = 345; // x = null;
   print("Value = ${x ?? y}");
   int z = x ?? y;
   print(z);
   ```

---

## 2.3 Switch Case

If we have constant conditions like ids as `1, 2, 3, 4, 5`  
Instead using many `if-else` statements we can use `switch-case` statement.

The case can be a constant `int` or a constant `String`.

#### Syntax

```dart
switch(variable){
    case 1:
    // code
    break; // this is must

    case 2:
    // another code
    break;

    default:
    // will execute if no case matches
}
```

`break` is must to stop execution after every `case`.

### Demo

With integer cases.

```dart
// Integer (int)
var option = 2;
switch (option) {
case 1:
    print("Option 1");
    break;
case 2:
    print("Option 2");
    break;
default:
    print("Invalid option");
}
```

With String cases.

```dart
String name = "Andy";
switch (name) {
case "Andy":
    print("Hello, Andy");
    break;
case "Dave":
    print("Hello, Dave");
    break;
default:
    print("No name");
}
```

---

# 3. Looping

We can repeat the statements using looping.  
There are 3 loops in Dart :

- For
- While
- Do ...While

## 3.1 For loop

1. The loop first initializes the `iteration_var`
2. then checks `breaking_condition`
3. then executes the `Statements` and
4. increments or decrements the `iteration_var` and
5. 2,3,4, are repeated until `breaking_condition` remains `true`.

### Syntax

```dart
for(iteration_var; breaking_condition;  increment/decrement)
{
    // Statements
}
```

### Demo

```dart
// print even nums
for (var i = 1; i <= 10; i++) {
    if (i % 2 == 0){
        print(i);
    }
}
```

### 3.1.1 For ... in Loop

#### Syntax

`for(var varname in IterableList){....}`

#### Demo

```dart
// for ..in loop
List names = ["Dave", "Andy", "Vikas", "Mark"];
for (var name in names) {
    print(name);
}

```

This loop is very useful when using List and other data containers.

### 3.1.2 Variation in for

we can omit the `initial`, `breaking` and `incr/decr` statements.

```dart
for (; x < 20; x++) {
    print(x);
}

for(;;x++){
    print(x);
    if(x==10){
        break;
    }
}

for(var x = 0;;){
    x++;
    print(x);
    if(x==10){
        break;
    }
}

```

---

## 3.2 While Loop

While loop is an `entry controlled` loop.  
The code inside `{...}` of while loop will execute only when the condition is `true`.

### Syntax

`while(condition){...}`

Here we declare a condition or breaking condition for the loop.  
See the demo

### Demo

```dart
// while loop
// print 0...9
var k = 0; // this is must
while (k < 10) {
    print(k);
    k++;
}
```

---

## 3.3 Do ...While Loop

Do ...while Loop is an `exit controlled` loop.  
Here the `Statement` will run for the first time regardless the `condition` is `true` or `false`.  
Then it will check the `condition` if it is `true` the the loop will continue execution otherwise it will jump out of the loop.

### Syntax

`do{...} while(conditon);`
Here the semicolon(`;`) is must.

### Demo

```dart
// print 0...9
// do ..while loop
int x = 0;
do {
    print(x);
    x++;
} while (x < 10);

```

### While vs Do...While

Both work in similar manner.  
But, `do...while` will execute at least once and `while` won't.

---

## 3.4 Break and Continue

These are two loop control statements.  
Which are used to _forcefully control_ the flow of loop execution.

### Break

`break` is used to stop the execution, and jump out of the loop.

#### Demo

```dart
// break after printing 5
for(int i = 0; i < 10; i++){
    print(i);
    if(i==5){
        break;
    }
}

// run and observe
// break -> stop execution of loop
for (int i = 0; i < 5; i++) {
    for (int j = 0; j < 5; j++) {
        print("$i $j");
        if (i == 2 && j == 2) {
            break; // will break inner loop
        }
    }
}
```

**We have already used `break` in `switch...case` program above.**

### Continue

`continue` is used to skip current iteration.

#### Demo

```dart
// continue -> skip an iteraion in a loop
for (var i = 0; i < 10; i++) {
    if (i == 5) {
        // skip when i==5
        continue;
    }
    print(i);
}
```

---

## 3.5 Label

Label is a new concept in Dart (we have seen it in `C` language with its buddy `goto`).  
This is not a magical spell from _Hogwarts_ that will do amazing magical things.  
It is just a way to make loop more controlled than before.  
We can name a block of code using label.  
Take a look at below code snippet.

### Demo

```dart
print("i j");

outerLoop:
for (int i = 0; i < 5; i++) {
  // ignore: unused_label
  innerloop:
  for (int j = 0; j < 5; j++) {
    print("$i $j");
    if (i == 2 && j == 2) {
      break outerLoop; // will break outerloop
    }
  }
}
```

Try doing this and observe the result of `i j`.

```dart
print("i j");

outerLoop:
for (int i = 0; i < 5; i++) {
  // ignore: unused_label
  innerloop:
  for (int j = 0; j < 5; j++) {
    print("$i $j");
    if (i == 2 && j == 2) {
      break innerLoop; // will break innerloop
    }
  }
}
```

---

# 4. Functions

Functions are used to group the code statements that do something.  
e.g. You want to calculate the area of a rectangle then the formula will be `area = length * width`.  
You can do it where you want to use the `area`. _But, if you want to double the area and add 20 to the result then what ?  
Will you write all the code again and again or find some convenient solution._
So, the solution is using functions.  
Your code will be

```dart
var area = length * width;
area = area * 2;
area = area + 20;
```

Now you are able to use the final value of `area`.
So, let's declare a simple function that says `Hello World!` to the user (after learning the simple function we will continue with our `area` calculation)

```dart
void sayHello(){
  print("Hello World!");
  // That's common saying hello to the world
  // let's say 'Hello Dart, Welcome to Earth'
  print("Hello Dart, Welcome to Earth");
}
```

## 4.1 Breakdown of function (Syntax)

**`void`** : It is the return type as you know Dart is a statically typed language like Java, C++ and C. This tells the compiler that we will return a value of the given type `(int, double, String, bool, other user defined types)`.  
Here `void` tells that the function will not return any value.

**`sayHello`** : It is the name of the function. It can be anything but, should be relevant to the work of the function like: `multiplyBy2(), makeHalf(), doubleThevalue(), reduceThree(), calculateSI() etc.`

**`()`** : It is called parameter. we can pass values that we want to work on. Like a `name` that should be printed instead of `Dart` or `World` in the above example.  
Let's assume we want to say Hello to you and we don't know your name then we will pass a `String` called `name` and interpolate it with the word `Hello` and print it.  
Look at the code below..

```dart
void sayHello(String name){
  print("Hello, $name");

}

void main(){
  sayHello("Vikas"); // Hello, Vikas
  sayHello("Dart"); // Hello, Dart
  sayHello("World"); // Hello, World
}
```

Copy the above code and run it.

You can also return the string.

```dart
String sayHello(String name){
  return "Hello, $name";
  // don't forget to change the return type
}

void main(){
  print(sayHello("Vikas")); // Hello, Vikas
  print(sayHello("Dart")); // Hello, Dart
  print(sayHello("World")); // Hello, World
}
```

Now, let's work on our `area` example:

```dart
int smartAreaOfRectange(int length, int width) {
  int area = length * width;
  area = area * 2;
  area = area + 20;
  return area;
}
```

Put this code in your file and call it in the main function as we've done in `sayHello(...)` function.

Another Example:

```dart
int doubleIt(int x) {
  return x * 2 + 17;
}

void main() {
  for (int i = 1; i <= 10; i++) {
    print(doubleIt(i));
  }
}
```

---

## 4.2 Function Expression (Fat Arrow `=>`)

The function expression or _Fat Arrow `=>`_ is used to make the function definition shorter and simpler.  
**It can only be used when there is only one statement in the function.**
Like , double the value

```dart
int doubleIt(int x) => x*2;
```

we don't use the `return` keyword here.  
So ,

```dart
int doubleIt(int x) => return x*2;
```

will be wrong.

---

## 4.3 Types of function parameters

PARAMETERS:

- Required
- Optional:
  - Positional
  - Named
  - Default:
    - Positional
    - Named

### 4.3.1 Required Parameters

These are the required parameters that cannot be omitted.

```dart
// required parameters
void requiredParameters(String c1, String c2, String c3) {
  print("Required Parameters");
  print("$c1, $c2, $c3");
}
void main() {
  // required parameters
  requiredParameters("NY", "Toronto", "San Diego");
}
```

### 4.3.2 Optional Parameters

We can omit passing these parameters.  
Blank value is considered as `null`.

#### 4.3.2.1 Optional Positional Parameters

We pass the value based on the portion of the parameter in the function.  
These parameters are surrounded by brackets `[ ... ]`.

```dart
// optional positional parameters
void optionalPositionalParameters(String c1, String c2, [String c3]) {
  print("Optional Positional Parameters");
  print("$c1, $c2, $c3");
}
void main() {
  // optional positional parameters
  optionalPositionalParameters("NY", "Toronto"); // 2 values
  optionalPositionalParameters("NY", "Toronto", "San Diego"); // 3 values
}
```

#### 4.3.2.2 Optional Named Parameters

we can give the name of parameter while passing the value.  
These parameters are surrounded by braces `{ ... }`.

```dart
// optional named parameters
void optionalNamedParameters(String c1, String c2, {String c3}) {
  print("Optional Named Parameters");
  print("$c1, $c2, $c3");
}
void main() {
  // optional named parameters
  optionalNamedParameters("NY", "Toronto");
  optionalNamedParameters("NY", "Toronto", c3: "San Diego");
}

```

#### 4.3.2.3 Default Parameters

These are the `positional and named` parameters with default value.

**Default Positional**
We pass the default value of the Positional Parameter while defining the function `[String name = "Dart", int id = 1111]`.

```dart
// default positional parameters
void defaultPositionalParameters(String c1, String c2, [String c3 = "Mumbai"]) {
  print("deafault positional Parameters");
  print("$c1, $c2, $c3");
}
void main() {
  // default positional
  defaultPositionalParameters("NY", "Toronto");
  defaultPositionalParameters("NY", "Toronto", "San Diego");
}
```

**Default Named**
We pass the default value of the Named Parameter while defining the function `{String name = "Dart", int id = 1111}`.

```dart
// default named parameters
void defaultNamedParameters(String c1, String c2, {String c3 = "Mumbai"}) {
  print("default Named Parameters");
  print("$c1, $c2, $c3");
}

void main() {
  // default named
  defaultNamedParameters("NY", "Toronto");
  defaultNamedParameters("NY", "Toronto", c3: "San Diego");
}
```

---

# 5. Exception Handling

_What are exceptions ?_  
An **Exception** is a runtime error which occurs when the program is running due to some error that the compiler was unable to detect.  
If an exception occurs the program crashes.  
If not handled may cause serious issues.

Below table showing some exceptions in Dart

<div class="scrollme" markdown="block">

| S.N. | Exception                      | Description                                                                                                           |
| ---- | ------------------------------ | --------------------------------------------------------------------------------------------------------------------- |
| 1.   | DeferredLoadException          | Thrown when a deferred library fails to load.                                                                         |
| 2.   | FormatException                | Exception thrown when a string or some other data does not have an expected format and cannot be parsed or processed. |
| 3.   | IntegerDivisionByZeroException | Thrown when a number is divided by zero.                                                                              |
| 4.   | IOException                    | Base class for all Input-Output related exceptions.                                                                   |
| 5.   | IsolateSpawnException          | Thrown when an isolate cannot be created.                                                                             |
| 6.   | Timeout                        | Thrown when a scheduled timeout happens while waiting for an async result.                                            |

</div>

## 5.1 Example of Exception

Simplest example will be dividing a number by _Zero_.

```dart
  void main(){
    // integer division
    int result = 12 ~/ 4; // OK
    int badResult = 15 ~/ 0; // NOT OK

  }
```

So, the line `double badResult = 15 / 0;` raises an `IntegerDivisionByZeroException` exception.

## 5.2 Handling of Exception

We can handle the exceptions by surrounding the exception occurring code inside a `try` block.  
And handle the exception using `on`, `catch`, and `finally` blocks.

### 5.2.1 Try Block

This is the place where we write an exception occurring statement.

#### Demo

```dart
try {
    int answer = 12 ~/ 0;
    print("Division = $answer");
}
```

If the statement inside `try` block raises an exception the program will not crash this time instead it will throw the exception out of the `try` block which we'll have to catch.

### 5.2.2 On Block

We can use `on` to catch the exception _if we know the thrown exception._

```dart
// CASE1: Handle with "on"
// use on when we know the exception
try {
  int answer = 12 ~/ 0;
  print("Division = $answer");
} on IntegerDivisionByZeroException {
  print("Cannot divide by zero");
}
```

Here we know the thrown exception `IntegerDivisionByZeroException`.

### 5.2.3 Catch Block

If we don't know the exception we can simply catch it using `catch` block.

```dart
// CASE2: Handle with "catch"
// use catch(e) when we don't know the exception
try {
  int answer = 12 ~/ 0;
  print("Division = $answer");
} catch (e) {
  print("The exception : $e");
}
```

Here the unknown exception is successfully handled.

### 5.2.4 Stack Trace

We can use the Stack Trace to find the events that threw the exception.

```dart

// CASE3: using STACK TRACE to know the events occured
// before exception was thrown
try {
  int answer = 12 ~/ 0;
  print("Division = $answer");
} catch (e, stackTraceObject) {
  print("The exception : $e");
  print("Stack Trace:\n$stackTraceObject");
}
```

### 5.2.5 Finally Block

This Block is always executed regardless the occurance of the exception.  
**No exception:**

```dart
// CASE4: finally clause
try {
  int answer = 12 ~/ 4;
  print("Division = $answer");
} catch (e, stackTraceObject) {
  print("The exception : $e");
  print("Stack Trace:\n$stackTraceObject");
} finally {
  print("This will always execute No exception)");
}
```

**With Exception:**

```dart
// CASE4: finally clause
try {
  int answer = 12 ~/ 0;
  print("Division = $answer");
} catch (e, stackTraceObject) {
  print("The exception : $e");
  print("Stack Trace:\n$stackTraceObject");
} finally {
  print("This will always execute (With exception)");
}
```

## 5.3 Custom Exception

**Q. Can we have our iwn exceptions ?**  
**A. Yes, we can define our own exception class using the following method.**

First create a class with `YourCustomExceptionName` and _implement_\* the built-in `Exception` class.  
Then _override_ the `errorMessage()` method to display "Your custom error message".

\*_We will learn about Object Oriented Programming later in the article._

#### Demo

```dart
// custom exception class
class DepositAmountLessThanZeroException implements Exception {
  String errorMessage() {
    return "Ammount cannot be less than 0";
  }
}
```

Let's use the custom exception class.  
Create a function which throws the exception.

```dart
void depositMoney(int amount) {
  if (amount < 0) {
    throw new DepositAmountLessThanZeroException();
  } else {
    print("Successful, Deposited $amount");
  }
}
```

Now call the function in the try block.

```dart
void main() {
  // OK
  try {
    depositMoney(1500);
  } catch (e, s) {
    print(e.errorMessage());
    print(s);
  }

  // OK
  try {
    depositMoney(0);
  } catch (e, s) {
    print(e.errorMessage());
    print(s);
  }

  // Exception
  try {
    depositMoney(-1233);
  } catch (e, s) {
    print(e.errorMessage());
    print(s);
  }
}
```

That's all from my side on basic exception handling.  
We will discuss the topic in detail later in another blog.

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned.
