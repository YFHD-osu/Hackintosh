# Hackintosh
My first hackintosh

## Hardware Info
| Name        | Model              |
| :---------- |:------------------ |
| MotherBoard | ASUS-B85M-PLUS     |
| CPU         | i7-4790            |
| RAM         | DDR3-24GB          |
| GPU         | RX-470 GDDR5 4G    |
| Ethernet    | Intel® 1217-V      |
| Disk        | WD Blue SA510 250G |

## Setup
### Choose correct plist verison 
| Filename             | Tested on   | OC Version   |
| :------------------- | :---------- | :----------: |
| ``config-v11.plist`` | 11 BigSur   | 0.8.0        |
| ``config-v12.plist`` | 12 Monterey | 0.8.0        |
| ``config-v13.plist`` | 13 Ventura  | 0.9.3        |
| ``config-v14.plist`` | 14 Sonoma   | 1.0.1        |

Download correct [Opencore](https://github.com/acidanthera/OpenCorePkg/) version

> [!IMPORTANT]  
> It's required to diable iGPU in BIOS if you are using macOS 13 or above

> [!IMPORTANT]  
> Those config havn't filled in correct serial number, please use ``PlatformInfo\Generic\SystemProductName`` to generate unique SMBIOS 

> [!IMPORTANT]  
> My ``UTBMap.kext`` might not work with every hardware, if you are experiencing USB not detected issue, you'll need to map USB yourself
<img width="500" alt="file-001" src="https://github.com/user-attachments/assets/ca41ec97-299e-4bbe-a280-19f8b46c73e1">

### ACPI Folder

Download ACPI folder in this repository and move them to ``\OC\ACPI``

### Drivers Folder
Copy these .efi files below from opencore package
- AudioDxe.efi
- HfsPlus.efi
- OpenCanopy.efi
- OpenRuntime.efi
- ResetNvramEntry.efi

### Kexts Folder
Download these .kext file below
- [AppleALC.kext](https://github.com/acidanthera/AppleALC)
- [IntelMausi.kext](https://github.com/acidanthera/IntelMausi) or [WOL Version](https://github.com/fischerscode/IntelMausi-WOL?tab=readme-ov-file)
- [Lilu.kext](https://github.com/acidanthera/Lilu)
- [USBToolBox.kext](https://github.com/USBToolBox/kext)
- UTBMap.kext
- [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC)
- [WhateverGreen.kext](https://github.com/acidanthera/WhateverGreen)

### Resources Folder
Download [OcBinaryData](https://github.com/acidanthera/OcBinaryData) and exetact them into folder

### Tools
Copy these .efi files below from opencore package
- OpenShell.efi
- ResetSystem.efi

## Driver
| 名稱            | 連結                                                                       | 簡述                        |
| :-----          |:---------------                                                            |    :-----                  |
| HP印表機驅動程式 | [Apple](https://support.apple.com/kb/DL1888?viewlocale=zh_TW&locale=en_US) | HP印表機、掃描器通用驅動程式 |

## macOS Recovery Downloader
```
# Big Sur (11)
py macrecovery.py -b Mac-42FD25EABCABB274 -m 00000000000000000 download

# Monterey (12)
py macrecovery.py -b Mac-FFE5EF870D7BA81A -m 00000000000000000 download

# Ventura (13)
py macrecovery.py -b Mac-4B682C642B45593E -m 00000000000000000 download

# Sonoma (14)
py macrecovery.py -b Mac-937A206F2EE63C01 -m 00000000000000000 download
```

## In order to skip boot select menu
Set ``Misc/Boot/ShowPicker`` to False in ``config.plist``
