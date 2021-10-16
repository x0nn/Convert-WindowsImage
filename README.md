# Convert-WindowsImage
Creates a Windows VM for Hyper-V from a Windows-ISO

# Release 21H2
Currently **supported and tested**:
- Windows 7, 8, 8.1
- Windows 10 / all versions up to 21H2
- **new** Windows 11 / all versions up to 21H2 in UEFI **and** BIOS
- **experimental** ARM64 support / all versions up to 21H2 in UEFI
  - I don't have the hardware to test this on ARM64 &#128576;

BIOS-DiskLayout
- Windows Server 2016 / 2019 / **new** 2022
- It should work for all versions from Windows 7 up to 11. Please file a bug report, if a version does not work.

VM's run on Hyper-V (DiskLayout: BIOS uses Gen1-VM, UEFI uses Gen2-VM)

## Examples

1. Dotsource the script to load the functions
   
`. .\Convert-WindowsImage.ps1`

2. Create a Windows Server 2019 VM

`Convert-WindowsImage -SourcePath "C:\Temp\windowsServer2019.iso" -VHDFormat "VHDX" -Edition "Windows Server 2019 Standard" -SizeBytes 50GB -DiskLayout "UEFI" -VHDPath "C:\Temp\windowsServer2019.vhdx"`
					
If you don't know the Edition, use -Edition "LIST" and the function will fail, but *list all editions in the ISO/WIM-file*.

## Bugs

If you change the script for debugging remember to reload the functions
   
`. .\Convert-WindowsImage.ps1`

Please open an issue on github, when you found a bug. Run the script with "-Debug" and "-Verbose" options and a Transcript, like:

```
Start-Transcript
Convert-WindowsImage -.... -Debug -Verbose
Stop-Transcript
```

Please attach/post the transcript to the issue.

You've guessed it, PR's are welcome.

## Requirements

The script needs
- **exact** Powershell 5.1 on a 
- Windows Host (lowest is Windows 8, but Windows 10 is recommended) with 
- **administrator rights**
	
Powershell ISE is currently supported, but will be deprecated in further releases, according microsofts policy. Consider using Visual Studio Code.

## License

The code is licensed under the GPLv3-License since version 21H2.
The code **was** licensed under the MIT licencse (X11) before version 21H1 as per the original source this implementation is based upon. See `LICENSE` for details.
