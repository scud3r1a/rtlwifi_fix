## rtlwifi_fix

#### The problem
On certain Wi-Fi modules (mostly included in notebooks and laptops), 
the Wi-Fi does not work, the connection gets lost after some time or the connection rate drops from time to time.
Those Wi-Fi drivers are made from Realtek and they make some problems under Linux distributions.

#### The Wi-Fi device
To find your Wi-Fi device, under Linux, just execute the following:
```
lspci | grep Wireless
```

#### The solution
Thanks to GitHub and friendly developers, there are updated drivers. Personally, I recommend this driver:
```
https://github.com/lwfinger/rtlwifi_new
```
According to the developer, the ```kernel_version``` branch is newer.

#### The dependencies
- latest or at least modern Linux kernel, e.g. version 4.13, 4.14 or later
- linux-headers-generic, build-essential (make) and git

#### The kernel update
For Linux kernel updates, you may use the shell and pull the latest kernel packages (pre-compiled). Furthermore, there is the option to use a GUI to install the kernel. I recommend Ukuu:
```
sudo apt-add-repository ppa:teejee2008/ppa --yes
sudo apt-get update
sudo apt-get install ukuu --yes
```

#### The driver update
For my purpose, I use a Ubuntu Linux system or Linux Mint system with ```apt``` and ```sudo```.
```rtlXXXXxx``` is your Realtek Wi-Fi adapter model to install with the correct name and without ```"```.
```
sudo apt-get install linux-headers-generic build-essential git --yes

git clone https://github.com/lwfinger/rtlwifi_new.git 
--branch kernel_version \
&& pushd rtlwifi_new \
&& make clean
&& sudo make install \
&& sudo modprobe -r "rtlXXXXxx" \
&& sudo modprobe "rtlXXXXxx" \
&& popd
```

#### The example
I show you the installation instructions for one device, Realtek RTL8821ae:
```
pushd ~/ \
&& sudo apt-get install linux-headers-generic build-essential git --yes \
&& git clone https://github.com/lwfinger/rtlwifi_new.git --branch kernel_version \
&& pushd rtlwifi_new \
&& make clean && sudo make install \
&& sudo modprobe -r "rtlXXXXxx" && sudo modprobe "rtlXXXXxx" \
&& popd && popd
```
