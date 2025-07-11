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

### Step 2: View scores
```powershell
Get-CimInstance Win32_WinSAT
```

## 5. 📆 BIOS Version and Install Date
```powershell
systeminfo | findstr /C:"BIOS Version" /C:"Original Install Date"
```

