# Hackintosh
人生第一台黑蘋果

## EFI輔助工具
| 軟體                                                 | 作者                                     | 簡述              |
| :--------------------------------------------------- |:----------------------------------------| :-----------------|
| [ProperTree](https://github.com/corpnewt/ProperTree) | [corpnewt](https://github.com/corpnewt) | PLIST檔案編輯器    |
| [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)   | [corpnewt](https://github.com/corpnewt) | 生成為啟用的SMBIOS |
| [SSDTTime](https://github.com/corpnewt/SSDTTime)     | [corpnewt](https://github.com/corpnewt) | 自動生成ACPI文件   |
| [USBMap](https://github.com/corpnewt/USBMap)         | [corpnewt](https://github.com/corpnewt) | 配置USB孔的裝置路徑 |

## 硬體配置
| EFI名稱| YFHD ✔️        |    EFI名稱| Tin ✔️                |     EFI名稱| Amelia ❌             |
| :----- |:---------------|    :----- |:----------------------|     :----- |:----------------------|
| 主機板 | ASUS-B85M-PLUS |    主機板 | GA-H81M-DS2 (rev. 2.1) |     主機板 | Z690 AORUS ELITE DDR4  |
| 處理器 | i7-4790        |    處理器 | i3-4160                |     處理器 | i5-12600k              |
| 記憶體 | DDR3-28GB      |    記憶體 | DDR3-10GB              |     記憶體 | DDR4 32G               |
| 顯示卡 | RX-470 GDDR5 4G|    顯示卡 | GTX-650                |     顯示卡 | RX-570 GDDR5 4G        |
| 網路卡 | Intel® 217-V   |    網路卡 | Realtek RTL8125        |     網路卡 | Realtek® 2.5GbE網路晶片 |

## 驅動程式
| 名稱            | 連結                                                                       | 簡述                        |
| :-----          |:---------------                                                            |    :-----                  |
| HP印表機驅動程式 | [Apple](https://support.apple.com/kb/DL1888?viewlocale=zh_TW&locale=en_US) | HP印表機、掃描器通用驅動程式 |

## 安裝時出現 pkgDownload Error 8 錯誤
依據 [csdn](https://blog.csdn.net/qq_38017558/article/details/123171466) 的教學，首先打開終端機

- Step 1 到磁碟的跟目錄``cd /Volumes/Macintosh HD``
- Step 2 建立放置安裝包的資料夾``mkdir private/tmp``
- Step 3 將安裝報複製過來``cp -R /Install/macOS monterey.app private/tmp``
- Step 4 進入剛剛建立的目錄``cd private/tmp``
- Step 5 在安裝包中新增資料夾``mkdir Contents/SharedSupport``
- Step 6 下載Ventura安裝套件``curl -L -o Contents/SharedSupport/SharedSupport.dmg https://swcdn.apple.com/content/downloads/26/15/032-48342-A_OG2YEE7OSX/8sd3qpy79cimb7cjiy47cytps0gm7m0z5l/InstallAssistant.pkg``
- Step 7 再次回到安裝目錄``cd /Volumes/Macintosh HD/private/tmp``
- Step 8 執行安裝程式``./Contents/MacOS/InstallAssistant_springboard``
