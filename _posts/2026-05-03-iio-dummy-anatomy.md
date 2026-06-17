---
title: The anatomy of iio_simple_dummy (tutorial 07)
date: 2026-05-03 20:29:59 +/- 0300
categories: [Open Source Software Development, Linux Kernel, MAC0470]
tags: [linux, kernel, kernel-linux, qemu, vm]
---

## The iio_dummy module

The `iio_dummy` module is a toy device driver already present in the IIO subsystem, and it has a lot of comments to help people like me that want to understand how device drivers work. In the [tutorial](https://flusp.ime.usp.br/iio/iio-dummy-anatomy/), the `iio_simple_dummy.c` file is explained.

## This thing is... complicated

I'm not gonna lie, I read the tutorial 5 times already together with the `iio_simple_dummy.c` source code and I still don't completely understand the `iio_dummy` module. I get what channels are, why `iio_chan_spec` is so important to configure them, and what `iio_dummy_read_raw`, `iio_dummy_write_raw`, `iio_dummy_probe` and `iio_dummy_remove` do on a conceptual level, but there are so many different structs with so many different fields that I can't even imagine what they do, that makes it clear that a lot of time has to be spent to get comfortable with it.
