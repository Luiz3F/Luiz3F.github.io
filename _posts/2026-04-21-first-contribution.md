---
title: First contribution to the Linux kernel
date: 2026-04-21 22:32:30 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, setup, qemu, vm]
---

## My first ever contribution!

I joined Tiago Dourado to tackle two cases of code duplication in the [AMD DRM tree](https://gitlab.freedesktop.org/agd5f/linux.git), more specifically in the process interrupt handling logico of some versions of jpeg drivers. The first pair of duplicate functions was `jpeg_v5_0_0.c::jpeg_v5_0_0_process_interrupt` and `jpeg_v5_3_0.c::jpeg_v5_3_0_process_interrupt`, and the second was `jpeg_v2_0.c::jpeg_v2_0_process_interrupt` and `jpeg_v3_0.c::jpeg_v3_0_process_interrupt`.

## The fix

Both of these cases are very similar, so the solutions were also very similar. For the `v2_0` and `v3_0` duplication, we noticed that `jpeg_v2_0.h` was included in `jpeg_v3_0.c`, so we just declared `jpeg_v2_0.c::jpeg_v2_0_process_interrupt` in `jpeg_v2_0.h` and substituted `jpeg_v3_0.c::jpeg_v3_0_process_interrupt` for 
```c
#define jpeg_v3_0_process_interrupt jpeg_v2_0_process_interrupt
```
(for this to work, we had to get rid of the `static` keyword from the `jpeg_v2_0_process_interrupt` declaration). For the `v5_0_0` and `v5_3_0` duplication, the fix was basically the same, we just had to include `jpeg_v5_0_0.h` in `jpeg_v5_3_0.c` since it wasn't already there.

## Will it be accepted?

We've send the patch to the AMD DRM mailing list and are waiting for their response.
