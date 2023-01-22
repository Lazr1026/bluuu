You should really only follow this if you were redirected here due to unable to use the browser for some reason.

Notes:  
- BluuBomb requires Linux. It's easiest in an Ubuntu VM.  
- You will need a compatible Bluetooth adapter so keep that in mind (In my experience Realtek adapters do not work, although they should be supported.)  

### What you need:
1. BluuBomb
1. [Tiramisu](https://tiramisu.foryour.cafe)

### SD Prep:
1. Copy the **contents** of the Tiramisu zip to the root of the SD Card.
1. Copy the `root.rpx` file from the `sd:/wiiu/environments` folder to root of the SD Card, and rename to `launch.rpx`.
1. Insert the SD Card into the Wii U.

### Setting up and using BluuBomb:
- Follow [this](bluubomb setup.md) to set up BluuBomb.

### Installing the PayloadLoader into Health and Safety:
1. Navigate to `installer` and then press A to Check.
1. Press A on `Install / Update`.
1. You’ll be asked if you are sure you want to install the PayloadLoader. Use the D-Pad to select `Install` and press A.
1. Press A to shut down the console.

### NAND Backup:  
1. Load the the Health and Safety application while holding B.
1. Navigate to `nanddumper` and press A.  
1. Make the settings look like this and then press A. MLC is optional as it is the biggest part of the NAND Backup (8gb or 32gb depending on your model).  
	-SLC: Yes  
	-SLCCMPT: Yes  
	-MLC: Optional  
	-OTP: Yes  
	-SEEPROM: Yes  
1. Wait for it to finish. It may take a few hours if you opted to dump MLC.  
1. To make sure you don’t lose the files, copy the `slc.bin`, `slccmpt.bin`, `seeprom.bin`, `otp.bin` and if you chose to go with a full backup, every `mlc.bin.part` file to your computer.
1. Delete the files to free up space on the SD Card.

### Autobooting Tiramisu
1. Start the console to boot into the Wii U Menu, launch the Health and Safety Information app and hold the X button to open the Environment Loader menu.
1. Navigate the list using the D-Pad and navigate to the `installer` environment, press A to launch it.
1. Press A to select `Check`.
1. Select `Boot Options`.
1. You will be asked if you want to switch the boot title. Press A to select `Switch to PayloadLoader`
1. When the process finished, press A to shutdown the console.
1. The PayloadLoader will now be launched automatically on every boot.

### Finalize:
- It is now a good idea to finalize your Tiramisu installation. You can find a guide on this [here](https://wiiu.hacks.guide/#/tiramisu/finalizing-setup).
