---
title: "Learn Complete Linux Bash Scripting in One Article"
date: 2021-05-04T00:59:14+05:30
draft: false
tags: ["Linux", "Programming", "Bash"]
categories: ["Guide"]
---

![](https://images.pexels.com/photos/745266/pexels-photo-745266.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940)
-- Photo by **[Iván Rivero](https://www.pexels.com/@osho?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)** from **[Pexels](https://www.pexels.com/photo/tractor-with-trailer-under-cloudy-skies-during-day-745266/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)**

In this article I'll be discussing about linux bash scripting (shell scripting) and I will cover every fundamental concept that you need to get started with bash scripting under linux environment.  
Bash scripting is a critical skill for every programmer.

First of all you will need a **linux machine** to execute these scripts.  
You can use any of the below techniques to get a linux machine:

- Install a linux distribution
- Install WSL
- Install Cygwin or MSYS
- Installing _git for bash_ will provide a bash prompt but this prompt is not a complete linux environment

I'll suggest you to install **WSL2** with **Ubuntu-2020.04** (_same is installed on my machine_).

This one article will cover all the basics and some advanced concepts about bash (shell) scripting, so read it completely.

## Very Basics

### 1. Hello World

Every programmer start by writing a program to print _'Hello World'_ on the console.  
Create a file named `hello.sh` and open it with your favourite text editor (notepad, sublime, atom, vscode, nano, vim, etc).  
Write the following code into the file and save.

```bash
 echo "Hello World :)"
```

Now run the script by using following command

```sh
$ bash ./hello.sh
```

This will print

> Hello World :)

### 2. Comments

We can write comments by using `#` symbol.

```bash
# This is a comment and will not be executed
# The below command will print "Hello World" to the console
echo "Hello World"
```

> Hello World

### 3. What is shebang (#! /bin/bash)

The **shebang is used** if you run the script directly as an executable file (for example with the command ./script.sh ). In this case it tells the operating system which executable to run. It's not required and has no effect if you for example write `bash ./script.sh` or source the script.  
We write the below line at the top of every script
`#!/bin/bash`
or
`#!/usr/bin/env bash`

##### Hello World with shebang

```bash
#!/usr/bin/env bash
# hello.sh
echo "Hello World :)"
```

> Hello World :)

### 4. Variables

Creating variables in bash script is as simple as

```bash
name="Vikash"
```

**NOTE:** Remember there is no space around _=_ operator.

##### Hello World with variables

-- `hello2.sh` --

```bash
#!/usr/bin/env bash
msg="Hello World from a variable"
echo $msg
```

`$ ./hello2.sh`

> Hello World from a variable

### 5. Command line arguments

We can pass arguments while executing the script and use them in the script.  
A simple example is below.

-- `params.sh`--

```bash
#!/usr/bin/env bash
name=$1
website=$2
echo "Hello I am $name"
echo "My website is $website"
```

`$ ./params.sh "Vikash" "Villageprogrammer.blogspot.com"`

> Hello I am Vikash
> My website is Villageprogrammer

| Parameter Name | Description              |
| -------------- | ------------------------ |
| $0             | Script name and path     |
| $1             | First argument           |
| $2 - $9        | Second to ninth argument |
| ${10} - ${...} | More than tenth argument |

You can execute a standard linux command and store the result in the variable.
-- `params2.sh`--

```bash
#!/usr/bin/env bash
today=$(date)
directory=$(pwd)
echo "Today is : $today"
echo "Directory : $directory"
```

`$ ./params2.sh`

> Today is : Thu Feb 18 17:05:56 IST 202
> Directory : /mnt/d/Xplore-Training/UNIX/bash-scripting/scripting

## Controls

### 1. If statement

The syntax of if statement is similar to other programming languages like _C, C++_.  
Syntax

```bash
if [ condition ]
then
	# write your code here
fi
```

Example:

--`if.sh `--

```bash
#!/usr/bin/env bash
num=10
if [ $num -lt 20 ]
then
	echo "$num is less than 20"
fi
```

`$ if.sh`

> 10 is less than 20

You can combine parameter and variable logic with if to write complex scripts.

### 2. if-else

Syntax

```bash
if [ condition ]
then
	# write your code here
else
	# write your code here
fi
```

Example:

--`if-else.sh `--

```bash
#!/usr/bin/env bash
num=10
if [ $num -eq 50 ]
then
	echo "$num is equal to 50"
else
	echo "$num is not equal to 50"
fi
```

`$ ./if-else.sh`

> 10 is not equal to 50

### 3. if-elif-else

Syntax

```bash
if [ condition ]
then
	# write your code here
elif [ condition ]
then
	# write your code here
fi
```

Example:

--`if-elif-else.sh `--

```bash
#!/usr/bin/env bash
num=10
if [ $num -eq 20 ]
then
	echo "$num is equal to 20"
elif [ $num -lt 20 ]
then
	echo "$num is less than 20"
else
	echo "$num is greater than 20"
fi
```

`$ ./if-elif-else.sh`

> 10 is less than 20

## Looping

Repetition of a code block can be done using while loop and for loop.

### 1. while loop

Syntax

```bash
while [ condition ]
do
	# write your code here
done
```

Example

-- `while.sh`--

```bash
count=1
while [ $count -lt 5 ]
do
	echo $count
	((count++))
done
```

`$ ./while.sh`

> 1
> 2
> 3
> 4
> 5

### 2. for loop

We can pass an array of elements from command line and use them in the script by creating an array
**`array=$@`**
Syntax:

```bash
for num in $container
do
	echo $num
done
```

Example:

--`for.sh`--

```bash
#!/usr/bin/env bash
nums=$@
for num in $nums
do
	echo $num
done
```

`$ ./for.sh 1 2 3 `

> 1
> 2
> 3

### 3. break and continue

--`break-continue.sh`--

```bash
#!/usr/bin/env bash
# use '@' for entering more than one inputs (simply an array)
# Pass the values from command line arguments
names=$@
# use of break
for name in $names
do
    if [ $name = "Andy" ]
    then
        echo "End found"
        break
    else
        echo "Hello, $name"
    fi
done

echo "for <break> loop terminated"
# use of continue
for name in $names
do
    if [ $name = "Andy" ]
    then
        echo "Skip found"
        continue
    else
        echo "Hello, $name"
    fi
done

echo "for <continue> loop terminated"
exit 0
```

`$ break-continue.sh "Vikas" "Andy" "Mark"`

> Hello, Vikas
> End Found
> for \<break\> loop terminated
> Hello, Vikas
> Skip found
> Hello, Mark
> for \<continue\> loop terminated

## Working with environment variables

We can access any of the environment variable from the bash script.

--`vars.sh`--

```bash
#!/usr/bin/env bash
# environment variables

echo "The path is : $PATH"
echo "The terminal is : $TERM"
echo "The editor is : $EDITOR"

# -z checks for empty
if [ -z $EDITOR ]
then
    echo "The Editor variable is empty"
fi
exit 0
```

`$ ./vars.sh`

> The path is : \<very long list of all paths will be printed\>
> The terminal is : xterm-256color
> The editor is :
> The Editor variable is empty

##### Environment variables and their meaning

HOME : user's home directory
PATH : executable binary's path
HOSTNAME : hostname of the machine
SHELL : shell that is being used
USER : user of this session
TERM : type of command line terminal that is being used

##### write a program to print user's name, computer name, and home directory

```bash
echo "$USER@$HOSTNAME in [$HOME]"
```

> vikas@DAVE in [/home/vikas]

## Functions in bash

There are two ways to create functions in _bash_ :

#### 1. Function declaration syntax with _function_ keyword

-`function1.sh`-

```bash
#!/usr/bin/env bash
function greeting(){
	echo "Hello"
}
```

#### 2. Function declaration without keyword

-`function2.sh`-

```bash
#!/usr/bin/env bash
greeting(){
	echo "Hello"
}
```

#### 3. Calling the function

To call the function we just need to use the name of the function, we do not use parentheses as we use in other programming languages (e.g. C, C++, Java, Python, etc.).  
-`function1.sh`-

```bash
#!/usr/bin/env bash
# declare the function
function greeting(){
	echo "Hello"
}
# calling the function
greeting
```

**`$ bash ./function1.sh`**

> Hello

#### 4. What about passing parameters ?

It's a two step process

1. **Access the parameter value**
   To access the parameter use :  
   _`$1`_: for first parameter,  
   _`$2`_: for second parameter,  
    ... ,  
    _`$n`_: for nth parameter.  
   You can either create a local variable and save the value by _`local variable=$n`_ or directly access the value by _`$n`_ (n is the parameter number 1, 2, 3, etc).
2. **Pass the parameter value**
   To pass the value write the value after the function name while calling the function (seperate by space).
   `add 2 3`

#### 5. Complete example

-`function.sh`-

```bash
#!/usr/bin/env bash
function add(){
	local num1=$1
	local num2=$2
	sum=`expr $num1 + $num2`
	echo "Sum=$sum"
}

# call the function
add 2 3 # 5
add 4 5 # 9
add -10 30 # 20
# or use command line arguments (uncomment if used)
# add $1 $2
```

**`$ bash ./function.sh`**

> 5
> 9
> 20

## Working with prompt message

You can write a message when asking the user for input.  
It can be done by using **`read`** command.

-`user-prompt.sh`-

```bash
#!/usr/bin/env bash
read "Hey, What's your name ?" name
echo "Hello, $name"
```

**`$ bash ./user-prompt.sh`**

> Hey, What's your name ?
> Vikash
> Hello, Vikash

If you want the input to be in the same line use **`-p`**..

-`user-prompt2.sh`-

```bash
#!/usr/bin/env bash
read -p "Hey, What's your name ?" name
echo "Hello, $name"
```

**`$ bash ./user-prompt2.sh`**

> Hey, What's your name ? Vikash
> Hello, Vikash

---

_Now you have enough understanding to get started with bash (shell) scripting. Go ahead an read a book or two on bash scripting and you will be good at it._

**_Keep Learining, Keep Practicing. :) :)_**

---

That's All. 😅

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned with CS111.

This post was originally posted on [Village Programmer](https://villageprogrammer.blogspot.com)
