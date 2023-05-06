# WSL-DESKTOP-ENVIROMENT

## How to have a desktop enviroment on your WSL.

<ol>
<li>
Install xfce4 enviroment

```
sudo apt install -y xfce4 
```
</li>

<li>

```
sudo apt install xfce4-goodies
```
</li>

<li>
Then, run the following:

```
    sudo cp /etc/xrdp/xrdp.ini /etc/xrdp/xrdp.ini.bak
    sudo sed -i 's/3389/3390/g' /etc/xrdp/xrdp.ini
    sudo sed -i 's/max_bpp=32/#max_bpp=32\nmax_bpp=128/g' /etc/xrdp/xrdp.ini
    sudo sed -i 's/xserverbpp=24/#xserverbpp=24\nxserverbpp=128/g' /etc/xrdp/xrdp.ini
    echo xfce4-session > ~/.xsession
```
</li>

<li>

run ``` 
sudo nano /etc/xrdp/startwm.sh
``` , then comment out the following lines by placing a ``` # ``` before them ``` test -x /etc/x11...``` and the next line; ``` echo /bin/sh /etc/x11... ```
</li>

<li>

Now, add the following on a new line at the very end  ``` startxfce4 ```  .

</li>

<li>
Save using CTRL+S and exit using CTRL+X.
</li>

<li>

Now, open Remote Desktop on your Windows host machine, and connect to  ``` localhost:3390 ```  .

</li>

</ol>
