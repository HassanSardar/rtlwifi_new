rtlwifi_new
===========

A repo for the newest Realtek rtlwifi codes.

This code will build on any kernel 3.0 and newer as long as the distro has not modified
any of the kernel APIs. It includes the following drivers:

rtl8192ce, rtl8192se, rtl8192de, rtl8188ee, rtl8192ee, rtl8723ae, rtl8723be, and rtl8821ae.

Added March 16, 2016: All branches of this repo now support the ant_sel module option
for rtl8723be. In addition, patches to implement this feature have been submitted
to the linux-wireless repo. If accepted, they should appear in kernel 4.7; however,
they will be backported to kernels 4.0 and newer when they reach mainline.

The New Way To Build Working Module.
===========

Download the source code in a zip and extract it to your desktop.   
In terminal type: `cd Desktop`   
Then type: `cd rtlwifi_new-rock.new_btcoex`    
Then: `make`  
Then: `sudo make install`   
Then: `sudo modprobe -rv rtl8723be`   
Then: `sudo modprobe -v rtl8723be ant_sel=2`  
Then: `sudo ip link set wlp13s0 up`   
Then: `sudo iw dev wlp13s0 scan`   
Then: `echo "options rtl8723be ant_sel=2" | sudo tee /etc/modprobe.d/50-rtl8723be.conf`   

Note: After your OS (Kernel) update, you need to apply these settings again to get strong signal.   
Noet 2: This is for rtl8723be, replace it in respect to the module you've.   
I'll update this properly in a while, this is just the initial setup.   
