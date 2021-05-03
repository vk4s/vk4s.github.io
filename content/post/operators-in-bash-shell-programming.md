---
title: "Operators in Bash Shell Programming"
date: 2021-05-04T01:16:10+05:30
draft: false
tags: ["Linux", "Programming", "Bash"]
categories: ["Tutorial"]
---

![A Picture of Pluto by NASA featured on Village Programmer](https://images.unsplash.com/photo-1614314107768-6018061b5b72?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1334&q=80)
Photo by [NASA](https://unsplash.com/photos/-5V6VZxSQRo) on Unsplash

---

If you want to learn bash bash scripting please read this article.  
 [Learn complete Linux bash (shell) scripting in one article](/post/learn-complete-linux-bash-scripting-in-one-article/)

Operators help us perform various types of operations such as addition, multiplication etc.  
There are following types of operators present in bash:

- Arithmetic,
- Relational,
- Boolean,
- File Test,
- String Test

## 1. Arithmetic Operators

All the arithmetic operators present in bash are discussed below with examples.  
These operators work with integers.

#### 1.1 Addition Operator

It's a **`+`** that adds operands together.  
Shown in the below example:

```bash
$x=20
$y=30
a=`expr $x + $y`
echo $a
```

This will display:

> 50

##### NOTE:

> 1. The **`expr `** command evaluates the expression.
> 2. There is `<space>` before and after the **`+`** operator .

#### 1.2 Subtraction Operator

It's a **`-`** that subtracts second operand from first operand.  
Shown in the below example:

```bash
$x=40
$y=30
a=`expr $x - $y`
echo $a
```

This will display:

> 10

#### 1.3 Multiplication Operator

It's a **`*`** that multplies operands together.  
Shown in the below example:

```bash
$x=2
$y=3
a=`expr $x * $y`
echo $a
```

This will display:

> 6

#### 1.4 Division Operator

It's a **`/`** that performs division operation.  
Shown in the below example:  
 -Example 1-

```bash
$x=200
$y=50
a=`expr $x / $y`
echo $a
```

This will display:

> 4

-Example 2-

```bash
$x=20
$y=3
a=`expr $x / $y`
echo $a
```

This will display:

> 6

#### 1.5 Modulus Operator

It's a **`%`** that performs modulus operation and returns the remainder.  
Shown in the below example:

```bash
$x=10
$y=3
a=`expr $x % $y`
echo $a
```

This will display:

> 1

#### 1.6 Equality Check Operator

It's a **`==`** that performs equality check operation and returns 1 if both sides are equal otherwise returns 0.  
Shown in the below example:

-Example 1-

```bash
$x=10
$y=10
a=`expr $x == $y`
echo $a
```

This will display:

> 1

-Example 2-

```bash
$x=10
$y=5
a=`expr $x == $y`
echo $a
```

This will display:

> 0

#### 1.7 Not Equal Check Operator

It's a **`!=`** that performs equality check operation and returns 0 if both sides are equal otherwise returns 1.  
Shown in the below example:  
-Example 1-

```bash
$x=10
$y=10
a=`expr $x == $y`
echo $a
```

This will display:

> 0

-Example 2-

```bash
$x=10
$y=5
a=`expr $x == $y`
echo $a
```

This will display:

> 1

## 2. Relational Operators

Relational operators are used to perform comparison among given operands.

### -eq (Equals to operator)

This checks whether the operands are equal.  
This operator is used to perform comparison in the `if` condition.

```bash
a=10
b=10
if [ $a -eq $b ]
	then
	echo "Equal"
else
	echo "Not Equal"
fi
```

> Equal

### -ne (Not equals to operator)

This checks whether the operands are equal.  
This operator is used to perform comparison in the `if` condition.

```bash
a=10
b=20
if [ $a -ne $b ]
	then
	echo "Not Equal"
else
	echo "Equal"
fi
```

> Not Equal

### -gt (Greater than operator)

This checks whether the first operand is greater than the second operand.  
This operator is used to perform comparison in the `if` condition.

```bash
a=40
b=20
if [ $a -gt $b ]
	then
	echo "$a is greater than $b"
else
	echo "$a is not greater than $b"
fi
```

> 40 is greater than 20

### -lt (Less than operator)

This checks whether the first operand is less than the second operand.  
This operator is used to perform comparison in the `if` condition.

```bash
a=20
b=40
if [ $a -lt $b ]
	then
	echo "$a is less than $b"
else
	echo "$a is not less than $b"
fi
```

> 20 is greater than 40

### -ge (Greater than or equals to operator)

This checks whether the first operand is greater than or equals to the second operand.  
This operator is used to perform comparison in the `if` condition.

```bash
a=40
b=20
if [ $a -ge $b ]
	then
	echo "$a is greater than or equals to $b"
else
	echo "$a is not greater than $b"
fi
```

> 40 is greater than or equals to 20

### -le (Less than or equals to operator)

This checks whether the first operand is greater than or equals to the second operand.  
This operator is used to perform comparison in the `if` condition.

```bash
a=40
b=200
if [ $a -le $b ]
	then
	echo "$a is less than or equals to $b"
else
	echo "$a is not less than $b"
fi
```

> 40 is less than or equals to 200

## 3. Boolean Operators

### ! (Not operator)

This changes `true` into `false` and vice versa.  
We have used this operator in _Not equal operator_ under arithmetic operators.
Shown in the below example:  
-Example 1-

```bash
$x=10
$y=10
a=`expr $x == $y`
echo $a
```

This will display:

> 0

-Example 2-

```bash
$x=10
$y=5
a=`expr $x == $y`
echo $a
```

This will display:

> 1

### -o (OR operator)

Checks whether one of the operands is true and executes the statements.

```bash
a=40
b=20
c=10
if [ $a -gt $b -o $c -gt $b]
	then
	echo "$a or $c is greater than $b"
else
	echo "$a is not less than $b"
fi
```

> 40 or 10 is greater than 20

### -a (AND operator)

Checks whether all of the operands are true and executes the statements.

```bash
a=40
b=20
c=100
if [ $a -gt $b -a $c -gt $b]
	then
	echo "$a and $c are greater than $b"
else
	echo "$a is not less than $b"
fi
```

> 40 and 100 are greater than 20

## 4. String Test Operators

These operators are used to perform string related comparisons.

### = (Equality Operator)

Check whether two strings are equal.

```bash
user="VIKAS"
defaultUser="VIKAS"
if [ $user = $defaultUser ]
then
	echo "User is allowed"
else
	echo "User is not allowed"
fi
```

> User is allowed

### != (Not equal operator)

Check whether two strings are not equal.

```bash
user="VIKAS"
defaultUser="DAVE"
if [ $user != $defaultUser ]
then
	echo "User is not allowed"
else
	echo "User is allowed"
fi
```

> User is not allowed

### -z (Zero length string)

Checks whether the string is zero length.

```bash
s=""
if [ -z $s ]
then
	echo "String is zero length"
else
	echo "String is non zero length"
fi
```

> String is zero length

### -n (Non zero length string)

Checks whether the string is empty.

```bash
s="Village Programmer"
if [ -n $s ]
then
	echo "String is non zero length"
else
	echo "String is zero length"
fi
```

> String is non zero length

### Empty string check

```bash
s=""
if [ $s ]
then
	echo "String is not empty"
else
	echo "String is empty"
fi
```

> String is not empty

---

_**Keep Learining, Keep Practicing. :) :)**_

---

That’s All. 😅

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned with CS111.

This post was originally posted on [Village Programmer](https://villageprogrammer.blogspot.com)
