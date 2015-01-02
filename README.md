## InfiniPy
Raspberry Pi Kiosk HTML Framework


## Prerequisite

A "Raspbian wheezy" configured as you want with "raspi-config"

## Localization setting

Looking for your setting :
<pre><code>locale</pre></code>
And configure "LANGUAGE, LANG, LC_ALL" if their empty :

like
<pre><code>export LANGUAGE=en_GB.UTF-8
export LANG=en_GB.UTF-8
export LC_ALL=en_GB.UTF-8</code></pre>

## Package : Re-synchronize And Install the newest versions
Re-synchronize the package index files from their sources
And 
Install the newest versions of all packages currently installed on the system from the sources enumerated in /etc/apt/sources.list(5)

<pre><code>sudo apt-get update && sudo apt-get upgrade -y</pre></code>

## PHP
<pre><code>sudo apt-get -y install php5-cli</pre></code>

## BROWSER 
<pre><code>sudo apt-get -y install libwebkitgtk-3.0-dev
git clone https://github.com/martya/kiosk-browser/

cd kiosk-browser
make
cd
sudo ln -s /home/pi/kiosk-browser/browser /usr/bin/browser
</pre></code>

## PHP & X's BROWSER & Startup Movie


### PHP & X's BROWSER 
<pre><code>git clone https://github.com/martya/infinipy/</pre></code>

Link files
<pre><code>sudo ln -s /home/pi/infinipy/init.d/infinipy /etc/init.d/infinipy</pre></code>

Modify the owner and properties
<pre><code>sudo chown root:root /etc/init.d/infinipy
sudo chmod 755 /etc/init.d/infinipy
sudo update-rc.d infinipy defaults 4
</pre></code>

### Startup Movie
Edit /boot/cmdline.txt
<pre><code>sudo nano /boot/cmdline.txt</pre></code>

Add 'quiet' to the end of the line
<pre><code>... rootwait quiet</pre></code>

Link files
<pre><code>sudo ln -s /home/pi/infinipy/init.d/asplashscreen /etc/init.d/asplashscreen
</pre></code>

Modify the owner and properties
<pre><code>sudo chown root:root /etc/init.d/asplashscreen
sudo chmod 755 /etc/init.d/asplashscreen
sudo update-rc.d asplashscreen defaults 0
</pre></code>