# Overview

Welcome! For the Kitty Eclipse project, we are using the Jetson Nano 2GB Developer Kit.

## Operating System

This device is currently running [Jetpack 4.6.2](https://developer.nvidia.com/embedded/jetpack-sdk-462). It uses [Jetson Linux R32.7.?](https://developer.nvidia.com/embedded/linux-tegra-r3272), which is based on [Ubuntu 18.04 (Bionic Beaver)](https://ubuntu.com/18-04). This version has reached the end of support, but unfortunately, NVIDIA has not released any further updates for this device, so we need to use an operating system that hasn't been updated for the past two years.

## Storage & Boot

The Jetson Nano has two onboard ways to store data: the internal eMMC and a microSD card. Upon being powered on, the device will initially load the kernel stored on its internal storage. It'll then boot the system stored on the device it is set up to boot from. In our case, it'll load into the system stored on the microSD card using the kernel stored on the internal eMMC.

## Pinout

TODO: UPLOAD PINOUT CURRENTLY SAVED ON JETSON NANO
