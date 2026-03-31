# Steam installation guide

## Installing from Artix repositories

First we need to enable `lib32` repository in which `steam` package is located.

Run:

    sudo nano /etc/pacman.conf

Go to the bottom of the text file and look for the following text:

    #[lib32]
    #Include = /etc/pacman.d/mirrorlist

Remove the comment symbols (#) so it looks like this:

    [lib32]
    Include = /etc/pacman.d/mirrorlist

Save the file and exit.

Update repositories by running:

    sudo pacman -Sy

Download Steam by running:

    sudo pacman -S steam

Choose the package according to your driver. For example, if I have NVIDIA 580xx driver, I choose 580xx-utils.

Please note that it takes a while to launch Steam for the first time after installation.

## Installing with Flatpak

Run:

    flatpak install flathub com.valvesoftware.Steam

To start Steam launcher, run:

    flatpak run com.valvesoftware.Steam

... or via start menu.
