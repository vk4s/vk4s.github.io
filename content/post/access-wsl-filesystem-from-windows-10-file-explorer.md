---
title: "Access Wsl Filesystem From Windows 10 File Explorer"
date: 2021-05-04T00:52:26+05:30
draft: false
tags: ["Windows 10", "WSL"]
categories: ["Tutorial"]
---

![](https://images.unsplash.com/photo-1442120108414-42e7ea50d0b5?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw=&ixlib=rb-1.2.1&auto=format&fit=crop&w=818&q=80)

If you want to get Linux environment in your Windows system there are some solutions that provide the oportunity.  
For example MYSYS, CYGWIN and a Virtual Machine (If you want complete linux machine) or Multiple Boot.  
But some of them aren't much powerful and some are resources hungry like Virtual Machine.  
So, the solution is **WSL (Windows Subsystem for Linux)**.  
You can learn how to setup WSL from [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10#manual-installation-steps).

In this article I'll be sharing how to access WSL file system from Windows 10 file explorer.  
I am assuming you have completely setup WSL and is able to access it through command prompt/powershell.

### Step 1

Open Windows Explorer  
Then type `\\wsl$` in the path location as shown in the below picture and hut enter. ![](https://i.imgur.com/sHbW2MZ.png)

### Step 2

Now a new window will open having your WSL linux machine name.  
![](https://i.imgur.com/9czE5vN.png)

### Step 3

Now right click on the icon shown in the above image (Name may not be the same)  
![](https://i.imgur.com/qAexGU9.png)

### Step 4

Now Select `Map Network Drive` option.  
A new diaglog box will open, As shown in the below picture.  
![](https://i.imgur.com/PXs7nwn.png)

Now choose a drive letter and click **Finish**.

### Step 5

You will have the Linux machine file system listed under Network Storage.  
![](https://i.imgur.com/ASl6mIy.png)

### Conclusion

You can view, rename, delete, copy/paste the files as you do with normal windows files.  
But do not delete any of the files you don't know. If you do that it may break the WSL System.

That’s all from my side.

Thanks for reading. 🙏  
If you liked it feel free to share with your dear ones.💗  
And tell me what do you think in the comment box.💬

Stay tuned with CS111.

This post was originally posted on [Village Programmer](https://villageprogrammer.blogspot.com)
