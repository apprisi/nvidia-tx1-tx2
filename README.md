# NVIDIA - TX1 
Repository of all NVIDIA TX-1 related code and usage instructions. 

## Initial Set-up
STEP 1: When you boot up the Jetson TX1 for the first time a terminal window will appear. To use the Ubuntu via the GUI, install the Nvidia Linux drive <br/>
From the home directory (use username: **ubuntu** and password: **ubuntu**)<br/>

>$ cd NVIDIA-INSTALLER <br/>

>$ sudo ./installer.sh <br/>

STEP 2: After the installation completes reboot the device,<br/>
>$ sudo reboot <br/>

STEP 3: You should now be able to log into the Ubuntu GUI

***

## Installing JetPack 
Link - https://developer.nvidia.com/embedded/jetpack<br/>
STEP 1: Download **JetPack** on the Host Machine by joining *Embedded System Developer* programme on NVIDIA page<br/>
The latest versopm at the time of writing was *JetPack-L4T-2.3.1-linux-x64.run*<br/>
STEP 2: Connect HOST (*Ubuntu 14.04*) machine to router (switch)<br/>
STEP 3: Connect Jetson (TX1) to router (switch)<br/>
STEP 4: Navigate to download folder of JetPack file and give executability rights to the installer file:<br/>

> $ chmod +x JetPack-L4T-2.3.1-linux-x64.run

STEP 5: Run the installer file:<br/>

> $ ./JetPack-L4T-2.3.1-linux-x64.run

STEP 6: Select Jetson platform when prompted (here: Jetson TX1 with Ubuntu Host)<br/>
STEP 7: Enter administrator password<br/>
STEP 8: Select Standard or Full in Component Manager and accept all Terms and Conditions<br/>
STEP 9: Once the installation completes on th
e Host machine, you will see a message "Completed Host installation, Installer will continue with Device/Post installation." <br/>
STEP 10: In the *networking layout* option, select the first option as mentioned in the above instructions (Device accesses Internet via router/switch.)<br/>
STEP 11: Put the Jetson TX1 in *Force USB Recovery Mode* by following the instructions on the screen<br/>
STEP 12: The device will proceed to get flashed. Wait until you see the message "Finished Flashing OS". Then hit the reset button on the device and wait till it enters the Ubuntu GUI.<br/>
STEP 13: Hit enter to continue on the host machine and set the IP address using ifconfig of prompted.<br/>
STEP 14: Remove all packages from the host (y/n) - decide accordingly<br/>

***

## Verifying CUDA 8.0 installation
By installing JetPack, you should now be able to run CUDA and all the samples that come with it<br/>
STEP 1: To check if you have successfully intalled cuda - version should say CUDA 8.0<br/>
> $ nvcc -V

STEP 2: To run a sample, from the home directory<br/>
> $ cd ~/NVIDIA_CUDA-8.0_Samples/bin/aarch64/linux/release/

STEP 3: You should see a list of executable scripts for all the CUDA samples<br/>
> $ ./smokeParticles

You should see the example running! I noticed a frame rate of ~38fps for this example<br/>

***

## Verifying VisionWorks installation
In a similar manner you can test the Vision Works install<br/>
> $ cd ~/VisionWorks-SFM-0.88-Samples/bin/aarch64/linux/release/

> $./nvx_sample_sfm

You should see a running example of Structure From Motion in what appears to be a parking lot<br/>

***


