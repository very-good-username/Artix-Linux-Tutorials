# Unable to find NetworkManager GUI

## What happens

With some desktop environments such as LXQt, NetworkManager GUI is missing from the toolbar and main menu. Running `nm-applet` or `network-manager-applet` doesn't help, because the applet doesn't appear in the toolbar.

This is a major problem especially for the people who are not tech-savvy and can't find a way to make internet connection.

## Why it happens

(Unknown)

## Solutions

### A) Running it via command line

Run `nm-connection-editor` to open NetworkManager GUI.

### B) Using NetworkManager command line interface

Run `nmtui-connect` in order to see available network connections.

### C) Using `nmcli` to connect WiFi

Turn on your WiFi:

    nmcli radio wifi on

Check available WiFi networks:

    nmcli dev wifi list

To connect:

    sudo nmcli dev wifi connect network-ssid password network-password

Example:

    sudo nmcli dev wifi connect MY_WIFI password MY_SECRET_PASSWORD

## Sources

* Manpages - nmcli: https://manpages.org/nmcli
* Manpages - nmcli-examples: https://manpages.org/nmcli-examples/7
