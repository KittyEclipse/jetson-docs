# Booting the Latest Kernel

[As outlined in the overview](../index.md#storage--boot), the Jetson Nano boots the system stored on the microSD card using the kernel stored on the internal eMMC.

## The Problem

Linux has these things called [Kernel Modules](https://en.wikipedia.org/wiki/Loadable_kernel_module#Linux) which provide functionally akin to drivers on Windows, such as having modules for Wi-Fi or graphics. If the corresponding modules for the booted kernel do not exist in the filesystem, these things will break. Furthermore, while the Jetson Nano loads the kernel stored on the internal eMMC, it loads the kernel modules stored on the *microSD card* instead, creating potential incompatibilities if the kernel modules on the microSD card do not correspond to the kernel booted from the internal eMMC.

Such a situation can arise if the system on the microSD card is upgraded. In this case, there is a newer version of the kernel and its modules. However, when the system upgrades, it removes the old version of the kernel and its modules since there is no need for them in theory. However, since the kernel on the internal storage is still the old kernel, the system will attempt to load the modules for the old kernel, which will fail because those modules no longer exist.

## The Solution

To fix this problem, the `/boot` folder on the internal eMMC was moved to `/boot.bak`, and the `/boot` folder on the *microSD card* was copied to `/boot` on the *internal eMMC*. This causes the system to load the updated kernel on the internal eMMC with the existing kernel modules on the microSD card.

However, this workaround means that if the microSD card is reflashed, the device will fail to load the kernel modules again. To fix this, move the `/boot.bak` folder back to `/boot`.
