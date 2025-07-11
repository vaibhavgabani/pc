# PC System Information Commands

A collection of PowerShell commands to gather information about your Windows PC hardware and performance.

## 1. 💻 Processor Information
```powershell
Get-CimInstance Win32_Processor | Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed
```

## 2. 🖥️ GPU and Display Resolution
```powershell
Get-CimInstance Win32_VideoController | Select-Object Name, AdapterRAM, CurrentHorizontalResolution, CurrentVerticalResolution
```

## 3. 🔋 Battery Health (Optional)
```powershell
powercfg /batteryreport
```

## 4. ⚡ Performance Benchmark
### Step 1: Run the benchmark
```powershell
winsat formal
```

### Step 2: Run the benchmark
```powershell
$xmlPath = Get-ChildItem "C:\Windows\Performance\WinSAT\DataStore" -Filter "*Formal.Assessment*.WinSAT.xml" |
Sort-Object LastWriteTime -Descending | Select-Object -First 1

[xml]$xml = Get-Content $xmlPath.FullName

$winSPR = $xml.WinSAT.WinSPR

"CPU Score     : $($winSPR.CpuScore)"
"Memory Score  : $($winSPR.MemoryScore)"
"Disk Score    : $($winSPR.DiskScore)"
"Graphics Score: $($winSPR.GraphicsScore)"
"Gaming Score  : $($winSPR.GamingScore)"
"System Score  : $($winSPR.SystemScore)"
```


### Step 3: View scores
```powershell
Get-CimInstance Win32_WinSAT
```

## 5. 📆 BIOS Version and Install Date
```powershell
systeminfo | findstr /C:"BIOS Version" /C:"Original Install Date"
```

