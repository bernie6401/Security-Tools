# Security Tools

個人安全工具集，依用途分類整理。

---

## 目錄總覽

| 分類 | 說明 | 大小 |
|------|------|------|
| [Android](#android) | Android 平台除錯與分析工具 | 257 MB |
| [Information Gathering](#information-gathering) | 資訊蒐集 | 35 MB |
| [Misc](#misc) | 編解碼、封包分析、鑑識、隱寫術、安裝檔 | 1.5 GB |
| [Penetration](#penetration) | 滲透測試工具 | 946 MB |
| [Reverse](#reverse) | 逆向工程工具 | 2.8 GB |
| [Script](#script) | 自用腳本與設定 | 10 KB |
| [Web](#web) | Web 安全測試工具 | 661 MB |
| [Windows](#windows) | Windows PE 分析與系統監控 | 227 MB |

---

## Android

Android 開發與安全測試所需的平台工具。

```
Android/
├── ADB-Tools/              # ADB Toolkit（含 Magisk、recovery.img、Toolkit.bat）
│   ├── adb.exe / adb34.exe
│   ├── fastboot.exe
│   ├── Magisk-v27.0.apk
│   ├── bundletool-all-1.17.2.jar
│   └── recovery.img
└── SDK-Platform-Tools/     # 官方 Android SDK Platform Tools
    ├── adb.exe
    ├── fastboot.exe
    ├── aapt / aapt2
    ├── zipalign
    └── apksigner.bat
```

> **⚠ 重複注意**: `ADB-Tools/` 與 `SDK-Platform-Tools/` 皆含 adb.exe、fastboot.exe 等工具（版本不同）。ADB-Tools 是第三方 Toolkit 封裝，SDK-Platform-Tools 是 Google 官方版本。

---

## Information Gathering

資訊蒐集與 metadata 提取。

```
Information Gathering/
└── exiftool-13.59_64/      # ExifTool — 圖片/檔案 metadata 讀寫
```

---

## Misc

雜項工具，含編解碼、封包分析、數位鑑識、隱寫術。

### EnDecode — 編碼/解碼

```
Misc/EnDecode/
├── crc32-reverse/          # CRC32 逆向計算
└── decodeObfuscator/       # JavaScript 反混淆
```

### Flow — 流量分析

```
Misc/Flow/
├── Fiddler2/               # HTTP(S) 抓包代理
└── TcpLogView/             # TCP 連線監控
```

### Forensics — 數位鑑識

```
Misc/Forensics/
├── Eric Zimmerman Tools/   # EZ Tools 合集（含 EvtxECmd、PECmd、RegistryExplorer、MFTECmd 等）
├── EvtxECmd/               # ⚠ 重複 — 已含於 Eric Zimmerman Tools
├── PECmd/                  # ⚠ 重複 — 已含於 Eric Zimmerman Tools
├── RegistryExplorer/       # ⚠ 重複 — 已含於 Eric Zimmerman Tools
├── LogonTracer/            # Windows 登入事件視覺化
├── Regshot/                # Registry 快照比對
├── mac_apt/                # macOS Artifact Parsing Tool
├── volatility/             # 記憶體鑑識（Python 2）
├── volatility3/            # 記憶體鑑識（Python 3）
├── volatility_2.6_win64_standalone.exe
├── oledump.py              # OLE 文件分析
├── sleuthkit-4.12.0.tar.gz # The Sleuth Kit（磁碟鑑識）
└── vmss2core-sb-8456865.exe # VMware snapshot → core dump
```

> **⚠ 重複注意**: `EvtxECmd/`、`PECmd/`、`RegistryExplorer/` 已包含在 `Eric Zimmerman Tools/` 資料夾中，為重複存在。

### Stego — 隱寫術

```
Misc/Stego/
├── Stegsolve.jar           # 圖片隱寫分析
├── MP3Stego_1_1_19/        # MP3 隱寫工具（已解壓）
├── MP3Stego_1_1_19.zip     # ⚠ 重複 — 同檔也在 Install file/ 中
├── Find flag script/       # 隱寫 flag 搜尋腳本
└── height_width_script.py  # 圖片寬高修復腳本
```

### Install file — 安裝檔

```
Misc/Install file/
├── AccessData_FTK_Imager_4.7.1.exe   # FTK Imager（鑑識映像）
├── ImageMagick-7.1.0-62-*.exe        # ImageMagick（圖片處理）
├── audacity-win-3.2.4-x64.exe        # Audacity（音訊分析）
├── deepsound-2-0-en-win.msi          # DeepSound（音訊隱寫）
├── silenteye-0.4.1-win32.exe         # SilentEye（圖片/音訊隱寫）
├── QCSetup.exe                        # QuickCrypto
├── jre-8u361-windows-i586-iftw.exe   # Java Runtime（Stegsolve 依賴）
└── MP3Stego_1_1_19.zip               # ⚠ 重複 — 同檔也在 Stego/ 中
```

---

## Penetration

滲透測試工具集。

### Password Brute Force — 密碼破解

```
Penetration/Password Brute Force/
├── hashcat-7.1.2/          # GPU 密碼破解
└── john-1.9.0-jumbo-1-win64/ # John the Ripper（CPU 密碼破解）
```

### Active Directory / Kerberos

```
Penetration/
├── Kerbrute/               # Kerberos 使用者列舉與密碼噴灑
│   ├── kerbrute_windows_amd64.exe
│   ├── kerbrute_linux_amd64
│   └── users.txt           # 使用者名稱字典（89 MB）
├── Krbrelayx/              # Kerberos 中繼攻擊（krbrelayx, dnstool, addspn, printerbug）
├── Responder/              # LLMNR/NBT-NS/mDNS 投毒 & NTLM 中繼
└── enum4linux/             # SMB/NetBIOS 列舉（Perl）
```

### Network / Proxy

```
Penetration/
└── proxychains_0.6.8_win32_x64/ # Windows ProxyChains
```

### Reconnaissance

```
Penetration/
└── Infoga/                 # Email OSINT 蒐集
```

### Exploit

```
Penetration/
└── Windows Exploit Suggester - New Generator/ # Windows 提權漏洞建議（wes.py）
```

### Android Pentest

```
Penetration/Android/
└── Mobile-Security-Framework-MobSF/ # MobSF — 行動 App 自動化安全分析
```

---

## Reverse

逆向工程工具集。

### Disassembler — 反組譯

```
Reverse/Disassembler/
├── Ghidra/                 # NSA Ghidra
├── IDA 7.0/                # IDA Free 7.0
└── IDA Pro 7.7/            # IDA Pro 7.7
```

### Debugger — 除錯器

```
Reverse/Debugger/
├── x96dbg/                 # x64dbg / x32dbg
├── odbg110/                # OllyDbg 1.10
└── scdbg/                  # Shellcode 除錯模擬器
```

### .NET Reverse

```
Reverse/.Net/
├── dnSpy-net-win32/        # dnSpy（32-bit）
└── dnSpy-net-win64/        # dnSpy（64-bit）
```

### Android Reverse

```
Reverse/Android/
├── jadx-1.4.7/             # JADX — DEX/APK 反編譯
├── ApkScan-PKID.jar        # APK 加殼偵測
└── uber-apk-signer-1.1.0.jar # APK 簽章工具
```

### Malware Analysis

```
Reverse/Malware Reverse/
├── Noriben/                # Sandbox 行為記錄（基於 Procmon）
└── ProcDOT/                # Procmon + PCAP 視覺化分析
```

### PE Tools

```
Reverse/
├── Patch Import Table/     # IAT 修復
│   ├── Imports Fixer/
│   └── UIF/
├── Scylla/                 # IAT 重建（配合 x64dbg）
└── upx-4.0.2-amd64_linux/  # UPX 脫殼（Linux 版）
```

> **⚠ 重複注意**: `Windows/Various on REM VM/` 中也有 `upx.exe`（Windows 版）。

### Other

```
Reverse/
└── PHP-Deobfuscator/       # PHP 反混淆
```

---

## Script

自用腳本與系統設定。

```
Script/
├── AddNewContextMenu.reg   # 右鍵選單自訂
├── get_chrome_password.py  # Chrome 密碼提取
├── shell env init.sh       # Shell 環境初始化
└── README.md
```

---

## Web

Web 滲透測試工具。

### Proxy

```
Web/Burp Suite/
├── burpsuite_pro_v2022.2.2.jar  # Burp Suite Pro
├── BurpLoaderKeygen.jar
└── jython-standalone-2.7.3.jar  # Jython（Burp 擴充用）
```

### Injection — 注入

```
Web/Injection/
├── sqlmap-dev/             # SQLMap（SQL Injection）
├── tplmap/                 # Server-Side Template Injection
└── xsssniper/              # XSS 掃描
```

### Deserialization — 反序列化

```
Web/Deserialization/
├── Demo/                   # 反序列化 Demo
├── PHP/                    # PHP 反序列化利用
├── pickle/                 # Python Pickle 反序列化
└── xxe/                    # XXE 注入
```

### Information Leak — 資訊洩漏

```
Web/Information Leak/
├── ds_store_exp/           # .DS_Store 洩漏利用
└── scrabble/               # .git 洩漏利用
```

### Upload — 檔案上傳

```
Web/Upload/
├── webshell.php / .png.php / .php.jpg  # 各種繞過格式的 Webshell
└── chtsecpt.*              # 上傳測試 payload
```

### Language — 語言環境

```
Web/Language/
├── PHP/                    # PHP 執行環境
├── d8/                     # V8 JavaScript Engine（d8）
└── wabt/                   # WebAssembly Binary Toolkit
```

---

## Windows

Windows 平台 PE 分析與系統監控工具。

### PE Analysis — PE 檔分析

```
Windows/
├── Detect It Easy/         # DIE — 檔案類型/加殼偵測
├── ExeinfoPe/              # PE 檔資訊 & 加殼偵測
├── PEiD-0.95-20081103/     # PEiD — 經典加殼偵測
├── PEBear/                 # PE 結構瀏覽
├── PEStudio/               # PE 靜態分析（含惡意指標）
└── PEview/                 # PE Header 檢視
```

### System Monitoring — 系統監控

```
Windows/
├── API Monitor/            # Windows API 呼叫監控
├── Process Hacker 2/       # 進階工作管理員
└── SysinternalsSuite/      # Sysinternals 全家桶（Procmon, Process Explorer 等）
```

### Various on REM VM — 逆向分析 VM 工具

```
Windows/Various on REM VM/
├── bintext.exe             # 字串提取
├── strings2.exe            # 進階字串提取
├── bytehist.exe            # Byte 分布直方圖
├── WinDump.exe             # Windows tcpdump
├── pe_unmapper.exe         # PE 記憶體映射還原
├── jmp2it.exe              # Shellcode 跳轉執行
├── shellcode_launcher.exe  # Shellcode 載入器
├── upx.exe                 # ⚠ 重複 — UPX（Reverse/ 下有 Linux 版）
├── setdllcharacteristics.exe # PE DLL 特性修改
├── rapid_env.exe           # 環境變數快速編輯
├── reg_export.exe          # Registry 匯出
└── sdelete64.exe           # Sysinternals 安全刪除
```

---

## 重複工具整理建議

| # | 重複項目 | 位置 A | 位置 B | 建議 |
|---|---------|--------|--------|------|
| 1 | `adb.exe` / `fastboot.exe` | `Android/ADB-Tools/` | `Android/SDK-Platform-Tools/` | 保留兩者（用途不同：Toolkit vs 官方 SDK） |
| 2 | `MP3Stego_1_1_19.zip` | `Misc/Stego/` | `Misc/Install file/` | 刪除 `Install file/` 中的副本 |
| 3 | `EvtxECmd/` | `Misc/Forensics/EvtxECmd/` | `Misc/Forensics/Eric Zimmerman Tools/EvtxECmd` | 刪除獨立的 `EvtxECmd/` |
| 4 | `PECmd/` | `Misc/Forensics/PECmd/` | `Misc/Forensics/Eric Zimmerman Tools/PECmd.exe` | 刪除獨立的 `PECmd/` |
| 5 | `RegistryExplorer/` | `Misc/Forensics/RegistryExplorer/` | `Misc/Forensics/Eric Zimmerman Tools/RegistryExplorer` | 刪除獨立的 `RegistryExplorer/` |
| 6 | `upx` | `Windows/Various on REM VM/upx.exe` | `Reverse/upx-4.0.2-amd64_linux/` | 保留兩者（平台不同：Win vs Linux） |

---

## Cheat Sheets

### CTF
- [Crypto Cheat Sheet](https://bernie6401.github.io/Crypto-Cheat-Sheet/)
- [Forensics Cheat Sheet](https://bernie6401.github.io/Forensics-Cheat-Sheet/)
- [Misc Cheat Sheet](https://bernie6401.github.io/Misc-Cheat-Sheet/)
- [PWN Cheat Sheet](https://bernie6401.github.io/PWN-Cheat-Sheet/)
- [Reverse Cheat Sheet](https://bernie6401.github.io/Reverse-Cheat-Sheet)
- [Web Cheat Sheet](https://bernie6401.github.io/Web-Cheat-Sheet)

### Others
- [Command Cheat Sheet](https://bernie6401.github.io/Command-Cheat-Sheet/)
- [Real World Tools](https://bernie6401.github.io/Real-World-Tools)
- [Docker Cheat Sheet](https://bernie6401.github.io/Docker-Cheat-Sheet/)
- [Useful Toolkit](https://bernie6401.github.io/Useful-Toolkit/)
