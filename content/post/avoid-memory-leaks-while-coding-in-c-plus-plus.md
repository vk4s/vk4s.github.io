---
title: "Avoid Memory Leaks While Coding in C Plus Plus"
date: 2021-05-04T01:24:39+05:30
draft: false
tags: ["Programming", "C++"]
categories: ["Tutorial"]
---

**Instructions**

Things You'll Need

- Proficiency in C++
- C++ compiler
- Debugger and other investigative software tools

# Part 1

Understand the operator basics. The C++ operator `new` allocates heap memory. The `delete` operator frees heap memory. For every `new`, you should use a `delete` so that you free the same memory you allocated:

```cpp
char* str = new char [30]; // Allocate 30 bytes to house a string.
delete [] str; // Clear those 30 bytes and make str point nowhere.

```

# Part 2

Reallocate memory only if you've deleted. In the code below, `str` acquires a new address with the second allocation. The first address is lost irretrievably, and so are the 30 bytes that it pointed to. Now they're impossible to free, and you have a memory leak:

```cpp
char* str = new char [30]; // Give str a memory address.
// delete [] str; // Remove the first comment marking in this line to correct.
str = new char [60]; /* Give str another memory address with the first one gone forever.*/
delete [] str; // This deletes the 60 bytes, not just the first 30.

```

# Part 3

Watch those pointer assignments. Every dynamic variable (allocated memory on the heap) needs to be associated with a pointer. When a dynamic variable becomes disassociated from its pointer(s), it becomes impossible to erase. Again, this results in a memory leak:

```cpp
char* str1 = new char [30];
char* str2 = new char [40];
strcpy(str1, "Memory leak");
str2 = str1; // Bad! Now the 40 bytes are impossible to free.
delete [] str2; // This deletes the 30 bytes.
delete [] str1; // Possible access violation. What a disaster!

```

# Part 4

Be careful with local pointers. A pointer you declare in a function is allocated on the stack, but the dynamic variable it points to is allocated on the heap. If you don't delete it, it will persist after the program exits from the function:

```cpp
void Leak(int x){
char* p = new char [x];
// delete [] p; // Remove the first comment marking to correct.
}

```

# Part 5

Pay attention to the square braces after "delete." Use `delete` by itself to free a single object. Use `delete []` with square brackets to free a heap array. Don't do something like this:

```cpp
char* one = new char;
delete [] one; // Wrong
char* many = new char [30];
delete many; // Wrong!

```

---

_**Keep Learining, Keep Practicing. :) :)**_

---

That’s All. 😅

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned with CS111.
