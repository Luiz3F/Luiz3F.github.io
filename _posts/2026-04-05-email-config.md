---
title: Sending patches to the Linux kernel with email (tutorial 05 & 06)
date: 2026-04-05 20:40:09 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, setup, qemu, vm]
---

## Patches via... email?

So, apparently, it is very common in kernel development to send patches in email instead of using something like GitHub, so much so that git has the `git send-email` command specially for this situation. Unfortunately, this command cannot be easily used with `@usp.br` emails since 2-step verification can't be done with them.

## The workaround

The solution proposed in the tutorial is to setup a Docker container that acts like an email proxy that uses the OAuth protocol, so that the verification required for `git send-email` to work is met and, fortunately, I followed the instructions and everything worked first try.
