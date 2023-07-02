# Hackintosh
人生第一台黑蘋果

## EFI說明
| 資料夾名稱         | OpenCore版本 |
| :---------------- | :---------: |
| macOS 11 BigSur   | 0.8.0       |
| macOS 12 Monterey | 0.8.0       |
| macOS 13 Ventura  | 0.8.8       |


## 硬體配置
| 名稱   | 型號               |
| :----- |:------------------|
| 主機板 | ASUS-B85M-PLUS     |
| 處理器 | i7-4790            |
| 記憶體 | DDR3-24GB          |
| 顯示卡 | RX-470 GDDR5 4G    |
| 網路卡 | Intel® 1217-V      |
| 硬碟   | WD Blue SA510 250G |

## EFI輔助工具
| 軟體                                                 | 作者                                     | 簡述              |
| :--------------------------------------------------- |:----------------------------------------| :-----------------|
| [ProperTree](https://github.com/corpnewt/ProperTree) | [corpnewt](https://github.com/corpnewt) | PLIST檔案編輯器    |
| [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)   | [corpnewt](https://github.com/corpnewt) | 生成為啟用的SMBIOS |
| [SSDTTime](https://github.com/corpnewt/SSDTTime)     | [corpnewt](https://github.com/corpnewt) | 自動生成ACPI文件   |
| [USBMap](https://github.com/corpnewt/USBMap)         | [corpnewt](https://github.com/corpnewt) | 配置USB孔的裝置路徑 |
| [Opencore Configurator](https://mackie100projects.altervista.org/download-opencore-configurator/) | [notiflux](https://github.com/notiflux) | 圖形化介面的EFI編輯工具 |

## 驅動程式
| 名稱            | 連結                                                                       | 簡述                        |
| :-----          |:---------------                                                            |    :-----                  |
| HP印表機驅動程式 | [Apple](https://support.apple.com/kb/DL1888?viewlocale=zh_TW&locale=en_US) | HP印表機、掃描器通用驅動程式 |


## 硬體採坑
避免的SSD: (待驗證) 
- WD 藍標 Blue 250G 250GB SSD

## 安裝時出現 pkgDownload Error 8 錯誤
- 方案1 使用終端機下載``InstallAssistant.pkg``
  > 依據 [csdn](https://blog.csdn.net/qq_38017558/article/details/123171466) 的教學，首先打開終端機 \
  > Step 1 到磁碟的跟目錄``cd /Volumes/Macintosh HD`` \
  > Step 2 建立放置安裝包的資料夾``mkdir private/tmp`` \
  > Step 3 將安裝報複製過來``cp -R /Install/macOS monterey.app private/tmp`` \
  > Step 4 進入剛剛建立的目錄``cd private/tmp`` \
  > Step 5 在安裝包中新增資料夾``mkdir Contents/SharedSupport`` \
  > Step 6 下載Ventura安裝套件``curl -L -o Contents/SharedSupport/SharedSupport.dmg https://swcdn.apple.com/content/downloads/26/15/032-48342-A_OG2YEE7OSX/8sd3qpy79cimb7cjiy47cytps0gm7m0z5l/InstallAssistant.pkg`` \
  > Step 7 再次回到安裝目錄``cd /Volumes/Macintosh HD/private/tmp`` \
  > Step 8 執行安裝程式``./Contents/MacOS/InstallAssistant_springboard`` 

- 方案2 使用``date``指令設定正確時間
  > 在終端機輸入指令:
  > ``date [月月][日日][時時][分分][年年]`` (每個欄位只填兩位數) 

- 方案3 檢查記憶體是否損毀
  > 使用 [memtest86+](https://www.memtest86.com/) 測試記憶體狀態
