# pc

Get-CimInstance Win32_Processor | Select-Object Name, NumberOfCores, NumberOfLogicalProcessors, MaxClockSpeed

5. 🖥️ GPU and Display Resolution
Get-CimInstance Win32_VideoController | Select-Object Name, AdapterRAM, CurrentHorizontalResolution, CurrentVerticalResolution

6. 🔋 Battery Health (Optional)
powercfg /batteryreport

Step 1: Run the benchmark
winsat formal

Step 2: View scores
Get-CimInstance Win32_WinSAT


9. 📆 BIOS Version and Install Date
systeminfo | findstr /C:"BIOS Version" /C:"Original Install Date"

