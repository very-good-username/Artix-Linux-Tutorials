# ufw firewall installation guide

## Step 1: Install 

Depending on your init system, you must choose the right package from repos:

    OpenRC => ufw-openrc
    s6     => ufw-s6
    dinit  => ufw-dinit
    runit  => ufw-runit
    
For example:

    sudo pacman -S ufw-openrc

## Step 2: Starting a service (OpenRC)
    
After the installation has finished, you must start the service:

    sudo rc-service ufw start

Then, add the service to default runlevel:

    sudo rc-update add ufw default

## Step 3: Verification (OpenRC)
    
Once done, you can verify that `ufw` is succesfully added as a service:

    rc-update | grep ufw

This should bring you a mention of ufw.

## Sources

* ufw Manpages: https://manpages.org/ufw/8
