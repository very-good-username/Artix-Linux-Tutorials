# GRUB tweaks

These changes are being made into grub config file. To access the file, run:

    sudo nano /etc/default/grub

After the changes, save the file and exit, and update grub:

    sudo update-grub
    
Changes will take effect after the next boot.
    
## Disable grub timeout for faster boot time

Change the timeout value to zero:

    GRUB_TIMEOUT=”0”

## Enable performance mode

Look for `GRUB_CMDLINE_LINUX_DEFAULT` and insert the following text:

    GRUB_CMDLINE_LINUX_DEFAULT=’cpufreq.default_governor=performance’

Verify the changes by running:

    cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor 

## Set GRUB screen resolution

Look for `GRUB_GFXMODE` and insert your preferred screen resolution. For example:

    GRUB_GFXMODE=”1920x1080,auto”
    GRUB_GFXPAYLOAD_LINUX=”keep”

