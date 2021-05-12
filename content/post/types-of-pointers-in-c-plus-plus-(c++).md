---
title: Types of Pointers in C/C++
date: 2021-05-12T16:16:41+05:30
draft: false
author: Vikash Patel
tags: ["C", "C++", "Programming"]
categories: ["Tutorial"]
featuredImage: >-
  https://images.unsplash.com/photo-1509116453669-0baa67ef9073?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8aHlhY2ludGglMjBtYWNhd3xlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60
---

![Photo of Hyacinth macaw on Unsplash - Village Programmer](https://images.unsplash.com/photo-1509116453669-0baa67ef9073?ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8aHlhY2ludGglMjBtYWNhd3xlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60)  
Photo of _Hyacinth macaw by_ Roi Dimor on [Unsplash](https://unsplash.com/photos/AEQ-166CWY8)

---

# Types of Pointers in C / C++

## 1. Null Pointer

It is a pointer pointing to nothing. **NULL** pointer points to the base address of the segment.

`-EXAMPLE-`

```c
int * ptr = (int) * 0;
float * fptr = (float) * 0;
double * dptr = (double) * 0;
char * chptr = (char) * 0;
```

##### Other ways of initializing NULL pointer

```c
int * ptr = NULL;
char * chptr = '\0';
```

> #### NULL also means 0 in macro
>
> ```c
> #define NULL 0
> ```

---

## 2. Dangling Pointer

A pointer pointing to the memory address of any variable (or object) which has been deleted from memory.  
When a pointer points to a deleted memory address, the pointer is called as a _dangling pointer_.

`-EXAMPLE-`

```cpp
Person p = new Person();
Person * pptr = &p;
delete p;
/* here pointer pptr (* pptr) is still pointing to
the Person object which has been deleted.
*/
```

---

## 3. Generic Pointer

_void_ pointer is known as generic pointer. It can point to **_any type_** of data.

`-EXAMPLE-`

```cpp
void * ptr;
```

#### Points to remember

- We can't de-reference a generic pointer.
- We can find the size of pointer using `sizeof()` operator.
- These pointers can hold any type of pointer such as char, int, float, structure, array, object etc without any typecasting.
- Any type of pointer can hold generic pointer without typecasting.
- Generic pointer can be used to implement dynamic datatype.

---

## 4. Wild Pointer

A pointer which has not been initialized is called as _wild pointer_.

`-EXAMPLE-`

```cpp
int * ptr;
```

---

## 5. Complex Pointers

These are pointers pointing to derived data-types.

- Pointer to array
- Pointer to function
- Pointer to structure / union
- Pointer to object
- Multilevel pointers

---

## 6. near / far / huge Pointers

These pointer modifiers were used in 1980's-90's before 32 bit architecture.  
**_near_** : a 16 bit pointer that can address any byte in a 64k segment.  
**_far_** : a 32 bit pointer that contains a segment and an offset.  
**_huge_** : a 32 bit pointer in which the segment is "normalized" so that no two far pointers point to the same address unless they have the same value.

You can read <a href="https://stackoverflow.com/questions/3575592/what-are-near-far-and-huge-pointers" target="_BLANK">this</a> stack overflow answer for more information.

---

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned.

---
