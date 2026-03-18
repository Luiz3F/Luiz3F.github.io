---
title: Setting up the testing environment for Linux kernel development (tutorial 01)
date: 2026-03-16 14:53:00 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, setup, qemu, vm]
---

## Wait, how do you do Linux kernel development again?

As much as I love Linux and the idea of open source software, I never actually contributed to an open source project before, much less to a project as large and important as the Linux kernel, so I didn't even know how to start. With the intention to change that, I enrolled in the course MAC0470 at IME-USP and will be following the four-part guide provided in that course to learn about kernel development. In that guide, the Industrial I/O subsystem is used, so that is the system I will be working with, and this post is about my experience following the first of the tutorials, available [here](https://flusp.ime.usp.br/kernel/qemu-libvirt-setup/).

## The Setup

Before even thinking about messing with the Linux kernel, I first had to properly set up a test environment so that editing, compiling and installing custom kernels could be done as efficient and safe as possible. To achieve that, I installed `qemu` and `libvirt` so that the custom kernels would be run inside a VM, and created an `activate.sh` that launched a terminal with the environment variables set up correctly, as per the tutorial. I proceeded to create and configure the VM, and the only issue I had was that there were no `ssh` config files in the VM, but this was easily solvable by simply installing `ssh`. Other than that, it was smooth sailing, and soon enough the development environment was ready.

