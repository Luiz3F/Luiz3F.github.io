---
title: Creating a custom module for the Linux kernel (tutorial 03)
date: 2026-03-24 21:00:05 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, setup, qemu, vm]
---

## What even is a module anyway?

Kernel modules are programs that can be dynamically loaded or unloaded from the kernel during runtime, making it very convenient to change the code that is being ran by the kernel (since you do not have to reboot) ande the system as a whole more versitile. I was planning to follow the [tutorial](https://flusp.ime.usp.br/kernel/modules-intro/) to learn how to configure and create those modules, but when I tried to boot the VM, something wasn't right.

## Learning to be careful with a VM (the hard way)

It had been a few days since the last time I used this VM, so I wanted to see with it was working normally. I started it up, tried to connect with it using `kw ssh` and... an erorr appeared, saying it couldn\`t connect to the VM. I thought that was strange, so I tried to use it directly instead of via `ssh` and, although no error message appeared, nothing else was shown on screen, like it was failling to boot. It was time for more drastic measures, so I recompiled the kernel, fully expecting it to revert the VM to the working state it was before since none of the kernel files had been changed since then. One can only imagine the shock I felt when this did not resolve the problem. Almost half a day later, I finally found the cause of all of this: the VM's disk image was corrupted, and it was corrupted for one simple reason: I commited the great sin of accidentally turning off my computer while the VM was still running. Luckly, the fix was also relatively simple, I just had to remake the disk image and _never_ forget to properly turn off the VM.

## Actually making the module

The module codes present in the tutorial were surprisingly simple to understand, it was just C with some slightly weird macros. The hard part was actually compiling and running them while dealing with the "config bureaucracy": first, you need to update the directory's `Makefile`, then update the `Kconfig` so that they are complied as modules, then run `make` (it will complie _all_ the modules of the directory, not just the ones you want), then send the resulting `.ko` files to the VM, and finally you can run them inside the VM. Luckly, this proccess ocurred without any problem.
