# alder-lake-hp-pro-x360-fortis-11-g11-hackintosh-efi
A functional EFI for booting hackintosh on Alder Lake N100 CPU found on HP Pro x360 Fortis 11" G11 Notebook PC

# Info
I wanted to run Hackintosh on my school laptop, which was the aforementioned HP Pro x360 Fortis 11 G11 Notebook PC.</br>
I have successfully been able to run macOS 10.15 (Catalina), which is also the only one i have tried. I think it surely can run newer OS'es, but the CPU would have a hard time catching up.</br>
I installed the macOS userspace onto a USB drive, so i could externally boot into macOS, without overwriting the Windows on the internal SSD. I don't know the stability of this EFI running on an SSD, because of possible missing SATA kexts.

# Files
In the EFI folder, i have the raw EFI with macOS 10.15 recovery environment.</br>
In the "hackintosh" folder, i have included all the tools and files i used to create the EFI, but it's quite messy.

# BIOS settings
(if setting not mentioned then leave unchanged)</br>
Secure Boot -> OFF</br>
TPM 2 -> ACTIVE</br>
Advanced/Boot options/Fast Boot -> OFF</br>
Advanced/System options/VTd -> OFF</br>
Advanced/System options/DMA -> OFF</br>

# Functionalities
BATTERY STATUS: YES</br>
WIFI: YES</br>
ETHERNET: YES</br>
BLUETOOTH: YES</br>
VOLUME: YES (even with the volume keys F4, F5, F6)</br>
SPEAKERS: YES</br>
MICROPHONE: YES</br>
USB 3 PORTS: YES</br>
THUNDERBOLT 3: YES (as far as i know)</br>
AUDIO JACK: NOT TESTED FOR</br>
HDMI: NOT TESTED FOR</br>
DRM: NOT TESTED</br>
APPLE ID SERVICES (imessage, facetime): NOT TESTED</br>
CAMERA: YES</br>
KEYBOARD: YES</br>
TRACKPAD: NO (use an external mouse)</br>
RTC: NO (resets every reboot with macOS)</br>
LAPTOP CLOSED: NO (only turns screen off, but doesnt logs out and go to sleep, when closing laptop)

# Trackpad
I have tried to make the trackpad work, but I'm at my whits end. I definitely know that it's I2C based, but the I2C controller/device (Intel 54e8) onboard the laptop isn't supported by Hackintosh as of 3/2026.</br>
In Windows Device Manager, the trackpad has the ACPI path of: ```\_SB.PC00.I2C0.TPD0```</br>
The touchscreen (Wacom Device) has the ACPI path of: ```\_SB.PC00.I2C0.TPL0```</br>

I believe the trackpad is an I2C-HID device or I2C-ELAN device, since in Device Management it says I2C-HID, while its HID is: ```ELAN0799```
If you would like to contribute, then you could give it a shot at fixing the trackpad.

# Keyboard
The Windows key is the equivalent of the Command key. </br>
The Alt key is the equivalent of the Option key

# Upgrading to a newer macOS
If you want to use a newer macOS, then you would have to grab a newer version of AirportItlwm.kext, which is required for Wifi, matching your macOS.

# Slow boot times
If it spends a long time (10-15 minutes) at the loading bar, then you probably have conflicting kexts, especialy AirportItlwm.kext, Itlwm.kext or the IntelBluetooth kexts. If this happens then remove every of those kexts, and add one at a time.

# Conclusion
Just to state it, you're free to modify and improve this EFI (try to add trackpad functionality). You're allowed use this EFI to your own extent. I don't need to be credited, but it would be nice. I won't be maintaining this repository any further.</br>
Cheers, Mati
