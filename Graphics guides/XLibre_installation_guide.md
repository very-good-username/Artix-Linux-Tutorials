# XLibre installation guide

Installing is very straightforward.

## Step 1: Install XLibre

Run:

    sudo pacman -S xlibre-xserver xlibre-drivers

The system warns about conflicting packages with Xorg, which is expected. By default, the system suggests "N" (No) in all cases in order to preserve old Xorg packages. You may see multiple questions, but, however, keep pressing "y" (Yes) to all.

After the questions, the packages are being installed. Wait until the installation is finished.

## Step 2: Reboot

## Step 3: Verify

After the installation you can verify the results.

Run:

    sudo Xorg -version

You should see a mention of XLibre at this point.

## Troubleshooting

To revert the changes and install X11 again, run:

    sudo pacman -S xorg-server xorg-drivers

And just like earlier, accept all the changes, finish the installation, reboot the computer and verify the results.
