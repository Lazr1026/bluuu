# Bluubomb Setup

How to set up and use Bluubomb:

1. Run `sudo apt install build-essential libbluetooth-dev libglib2.0-dev libdbus-1-dev git` to install the required dependencies.
1. Run `git clone https://github.com/rnconrad/WiimoteEmulator && cd WiimoteEmulator`.
1. Run `source ./build-custom.sh` to build BlueZ. Don't worry if building the emulator itself fails due to missing SDL headers. Just continue with the next steps.
1. Stop the already running bluetooth service `sudo systemctl disable --now bluetooth`.
1. Run the custom built bluetoothd `sudo ./bluez-4.101/dist/sbin/bluetoothd -d -n`.
1. Download the bluubomb binary and the sd_kernels.zip from the [releases](https://github.com/GaryOderNichts/Bluubomb/releases) page. 
1. Copy `loadrpx.bin` from `sd_kernels.zip` to the root of your SD Card and rename it to `bluu_kern.bin`. 
1. Power on the Wii U, insert your SD Card and press the sync button. Make sure there are no other controllers connected.
1. Open a new terminal and make the bluubomb file executable by running `chmod +x bluubomb`.
1. Run `sudo ./bluubomb` and wait for the pairing process to complete.  
	- This might take a minute.  
	- If you get a warning about Simple Pairing mode read the Simple Pairing mode section below.  
1. After it has finished sending the data, go to Step 1 on the main page in section `Installing the PayloadLoader into Health and Safety`.

### Simple Pairing Mode
On some devices the simple pairing mode can't be disabled by bluubomb.  
You can check the current Simple Pairing mode by running hciconfig hci0 sspmode.  
Make sure it says `Simple Pairing mode: Disabled`.  
If not run `sudo hciconfig hci0 sspmode disabled` and `sudo hciconfig hci0 reset`.  
Then check the mode again.  
