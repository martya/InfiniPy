## InfiniPy
Raspberry Pi Kiosk HTML Framework


## Prerequisite

A "Raspbian stretch" configured as you want with "raspi-config"

Boot up the Raspberry Pi, login as user pi with password raspberry, then start <pre><code>sudo raspi-config</pre></code> to apply some initial customizations:

-Localisation Options
-Change User Password: This is important 
-Network Options
-Boot Options: Select “Desktop / CLI” and then “Console Autologin”.
-Interfacing Options: Enable SSH access if needed.

## Package : Re-synchronize And Install the newest versions
Re-synchronize the package index files from their sources
And 
Install the newest versions of all packages currently installed on the system

<pre><code>sudo apt-get update && sudo apt-get upgrade -y</pre></code>


## Minimum Environment for GUI Applications
<pre><code>sudo apt-get install --no-install-recommends xserver-xorg x11-xserver-utils xinit openbox</pre></code>

## Openbox Configuration
<pre><code>sudo nano /etc/xdg/openbox/autostart</pre></code>

And add the following:
<pre><code>
# Disable any form of screen saver / screen blanking / power management
xset s off
xset s noblank
xset -dpms

# Allow quitting the X server with CTRL-ATL-Backspace
setxkbmap -option terminate:ctrl_alt_bksp
</pre></code>

## PHP
Install PHP-CLI
<pre><code>sudo apt-get -y install php7.0-cli</pre></code>

## GIT
Install Git Client
<pre><code>sudo apt-get -y install git </pre></code>

## BROWSER 
it takes a while...
<pre><code>sudo apt-get -y install libwebkitgtk-3.0-dev
git clone https://github.com/martya/kiosk-browser/

cd kiosk-browser
make
cd
sudo ln -s /home/pi/kiosk-browser/browser /usr/bin/browser
</pre></code>

## PHP & X's BROWSER 
<pre><code>git clone https://github.com/martya/infinipy/</pre></code>

Modify the properties
<pre><code>
chmod +x infinipy/infinipy
sudo nano .profile
</pre></code>
add 
<pre><code>sudo infinipy/infinipy start</pre></code>


## Rotate the screen (Option)
<pre><code>sudo nano /boot/config.txt<pre><code>
Add one of the following lines to the bottom of the file :
<pre><code>display_rotate=1</pre></code>
