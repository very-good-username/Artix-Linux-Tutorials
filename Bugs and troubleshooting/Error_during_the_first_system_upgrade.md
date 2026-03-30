# Error during the first system upgrade

## What happens 
When doing the first system upgrade with `sudo pacman -Syu`, you'll see the following error message:

    linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad103 exists in filesystem
    linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad104 exists in filesystem
    linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad106 exists in filesystem
    linux-firmware-nvidia: /usr/lib/firmware/nvidia/ad107 exists in filesystem

## Why it happens

With 20250613.12fe085f-5, firmware was split into several vendor-focused packages. `linux-firmware` is now an empty package depending on the default set of firmware. Unfortunately, this coincided with upstream reorganizing the symlink layout of the NVIDIA firmware, resulting in a situation that Pacman cannot handle.

## Solution

Reinstall `linux-firmware`:

    sudo pacman -Rdd linux-firmware
    sudo pacman -Syu linux-firmware

## Sources

* Arch Linux: linux-firmware >= 20250613.12fe085f-5 upgrade requires manual intervention  https://archlinux.org/news/linux-firmware-2025061312fe085f-5-upgrade-requires-manual-intervention/ 
