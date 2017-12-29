## rtlwifi_fix

#### The problem
On certain Wi-Fi modules (mostly included in notebooks and laptops), 
the Wi-Fi does not work, the connection gets lost after some time or the connection rate drops from time to time.
Those Wi-Fi drivers are made from Realtek and they make some problems under Linux distributions.

#### The solution
Thanks to GitHub and friendly developers, there are updated drivers. Personally, I recommend this driver:
```
https://github.com/lwfinger/rtlwifi_new/blob/master/README.md
```

#### The dependencies
- latest or at least modern Linux kernel, e.g. version 4.13, 4.14 or later
- linux-headers-generic, build-essential (make) and git


#### The update
For my purpose, I use a Ubuntu Linux system or Linux Mint system with ```apt``` and ```sudo```.
```
sudo apt-get install linux-headers-generic build-essential git --yes
```
