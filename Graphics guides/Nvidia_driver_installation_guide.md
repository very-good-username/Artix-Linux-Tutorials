# Nvidia driver installation guide

This is a simple copy-paste guide.

## Step 1: Disable Secure Boot in BIOS/UEFI settings

Check your BIOS/UEFI settings to disable secure boot.
To enter BIOS/UEFI settings, press rapidly Delete or Esc keys during the initial boot process. These keys might vary depending on the device.

## Step 2: Check if there's already Nvidia driver installed on your device

Run:

    sudo pacman -Q | grep nvidia

## Step 3: Install necessary packages for Nvidia driver installation

Run:

    sudo pacman -S base-devel linux-headers cmake make gcc dkms

## Step 4: Install Nvidia driver

There are alternative drivers to be downloaded. In this example, we are installings dkms drivers. Please note that driver versions and filenames will evolve during the time.

Run:

    sudo pacman -S nvidia-580xx-dkms

## Step 5: Block nouveau driver

Create an empty file:

    sudo nano /etc/modprobe.d/blacklist-nouveau.conf

Insert the following text into the file:

    blacklist nouveau
    options nouveau modeset=0

Save the file and exit.

## Step 6: Update initramfs

Run:

    sudo mkinitcpio -p linux

## Step 7: Reboot your computer

## Step 8: Verify the current driver

Run:

    nvidia-smi

or:

    sudo lshw | grep nvidia

If the installation was successful, you should see mentions of Nvidia driver.

## Step 9: Install Nvidia driver settings

Run:

    sudo pacman -S nvidia-settings

## Step 10: Edit Nvidia driver settings

Run:

    nvidia-settings 

Feel free to edit the settings as you wish.
