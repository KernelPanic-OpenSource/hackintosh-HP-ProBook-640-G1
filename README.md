# hackintosh-HP-ProBook-640-G1
HP ProBook 640 G1 - Core i5 4200M - VGA Intel HD Graphics 4600 - VGA Radeon 8750M

## What Work
```bash
ALL
I can FakeID VGA HD8750M to HD8770M but i can't test it ( i see system info show: Support Devices )
```

```bash
HP Probook 640 G1
CPU: Core i5 4200M
GPU: Intel HD Graphics 4600
VGA: AMD Radeon 8750M 1Gb DDRL5
RAM: 8Gb DDRL3 Bus 1600
Disk: SSD-256Gb
      HDD-500Gb -- Carddy Bay
Wifi: Intel Centrino N1000
Bluetooth: Not include
```

## Install VoodooHDA macOS Big Sur 11.3 -> 12.X
```bash
reboot to recovery mode
```
Open Terminal on recovery mode
Type
```bash
csrutil authenticated-root disable
```
```bash
csrutil disable
```
reboot
Download VoodooHDA.kext
Open Terminal
```bash
sudo cp -R /path_to_kext/VoodooHDA.kext  /Library/Extensions
```
Example:
```bash
sudo cp -R ~/Download/VoodooHDA.kext  /Library/Extensions
```
LoadKext:
```bash
sudo kmutil load -p /Library/Extensions/voodooHDA.kext
```
Afte Loadkext Open System Preferences -> Security and enable here VoodooHDA
And Reboot --> Complete

# Multiboot Windows - macOS
```bash
Create Partition
Boot Windows
Afte Boot Windows Copy Folder Microsoft to /EFI/Microsoft
Copy you Folder BOOT to /EFI/BOOT
Copy you OC foler to /EFI/OC
Copy /EFI/BOOT/BOOTx64.efi to /EFI/OC/BOOTx64.efi
Copy my Folder BOOT to /EFI/BOOT
Open PowerShell ( Run On Admin )
```
```bash
bcdedit /set "{bootmgr}" path \EFI\BOOT\BOOTx64.efi
```
Done
