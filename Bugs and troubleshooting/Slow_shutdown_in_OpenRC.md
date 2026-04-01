# Slow shutdown in OpenRC

## What happens

When shutting down the computer, this message will appear:

    The system will power off now
    nm-dispatcher: req:2 'down' [wlan0], "/etc/NetworkManager/dispatcher.d/10-openrc-status": complete: proccess failed with Script '/etc/NetworkManager/dispatcher.d/10-openrc-status' exited with status 1
    ModemManager[2286]: <wrn> could not acquire the 'org.freedesktop.ModemManager1' service name

    ModemManager[2286]: <msg> ModemManager is shutdown
    
    nm-dispatcher: Caught signal 15, shutting down...

Computer will succesfully shut down, but it takes longer than usual.

## Why it happens

See the explanation: https://forum.artixlinux.org/index.php/topic,7711.0.html

## Solution

I deleted `modemmanager`, because I didn't need it anyway:

    sudo pacman -R modemmanager

The ModemManager messages are not visible anymore during the shutdown and the shutdown process is now a little bit faster.

There may (or may not) be better solutions available.

Note: This solution doesn't affect the `nm-dispatcher` messages. They are still visible.
