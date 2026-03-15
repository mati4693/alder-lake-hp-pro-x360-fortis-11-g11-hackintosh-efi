# alder-lake-hp-pro-x360-fortis-11-g11-hackintosh-efi
A functional EFI for booting hackintosh on Alder Lake N100 CPU found on HP Pro x360 Fortis 11" G11 Notebook PC

# Info
I wanted to run Hackintosh on my school laptop, which was the aforementioned HP Pro x360 Fortis 11 G11 Notebook PC.
I have successfully been able to run macOS 10.15 (Catalina), which is also the only one i have tried. I think it surely can run newer OS'es, but the CPU would have a hard time catching up.
I installed the macOS userspace onto a USB drive, so i could externally boot into macOS, without overwriting the Windows on the internal SSD. I don't know the stability of this EFI running on an SSD, because of possible missing SATA kexts.

# BIOS settings
(if setting not mentioned then leave unchanged)
Secure Boot -> OFF
TPM 2 -> ACTIVE
Advanced/Boot options/Fast Boot -> OFF
Advanced/System options/VTd -> OFF
Advanced/System options/DMA -> OFF

# Functionalities
WIFI: YES
ETHERNET: YES
VOLUME: YES
SPEAKERS: YES
MICROPHONE: NOT TESTED FOR
USB 3 PORTS: YES
THUNDERBOLT 3: YES (as far as i know)
AUDIO JACK: NOT TESTED FOR
HDMI: NOT TESTED FOR
CAMERA: NOT TESTED FOR
KEYBOARD: YES
TRACKPAD: NO (use an external mouse)
RTC: NO (resets every reboot with macOS)

# Trackpad
I have tried to make the trackpad work, but I'm at my whits end. I definitely know that it's I2C based, but the I2C controller/device (Intel 54e8) onboard the laptop isn't supported by Hackintosh as of 3/2026.
In Windows Device Manager, the trackpad has the ACPI path of: ```\_SB.PC00.I2C0.TPD0```
The touchscreen (Wacom Device) has the ACPI path of: ```\_SB.PC00.I2C0.TPL0```

I believe the trackpad is an I2C-HID device or I2C-ELAN device, since in Device Management it says I2C-HID, while its HID is: ```ELAN0799```

# Upgrading to a newer macOS
If you want to use a newer macOS, then you would have to grab a newer version of AirportItlwm.kext, which is required for Wifi, matching your macOS.

# Slow boot times
If it spends a long time at the loading bar, then you probably have conflicting kexts, especialy AirportItlwm.kext, Itlwm.kext or the IntelBluetooth kexts. If this happens then remove every of those kexts, and add one at a time.

# Conclusion
Just to state it, you're free to modify and improve this EFI (try to add trackpad functionality). You're allowed use this EFI to your own extent. I don't need to be credited, but it would be nice. I won't be maintaining this repository any further.
Cheers, Mati
