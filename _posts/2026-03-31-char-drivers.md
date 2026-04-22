---
title: Introduction to character device drivers in the Linux kernel (tutorial 04)
date: 2026-03-31 20:14:25 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, setup, qemu, vm]
---

## A breather

Unlike the previous ones, this [tutorial](flusp.ime.usp.br/kernel/char-drivers-intro/) is much more expository, leaving less room to make day-consuming mistakes.

## Character device driver? I hardly know'er!

The main topic of this tutorial are character device drivers, but, to talk about them, it is necessary to first understand character devices. Character devices are files that serve as abstractions of hardware components for the kernel, meaning that communication between the kernel and a hardware device (like a monitor or a mouse) is done through this special kind of file. These files also have what are called Major numbers, which identify the type of device, and Minor numbers, which differentiate multiple devices of the same type or switch operation modes. With that in mind, the definition of character device drivers is pretty simple: they are the programs responsible for accessing and manipulating these character devices and their major/minor numbers.

## A character device driver in action

Although much more complex than the programs shown in the previous tutorial, the code present here is compiled and executed the same way as a module is, so there wasn't any problems in that regard, and the reading and writing programs also worked perfectly.
