# Convert-WindowsImage
Creates a Windows VM for Hyper-V from a Windows-ISO

## Examples

1. Dotsource the script to load the functions
`. .\Convert-WindowsImage.ps1`

2. Create a Windows Server 2019 VM

`Convert-WindowsImage -SourcePath "C:\Temp\windowsServer2019.iso" -VHDFormat "VHDX"
                     -Edition "Windows Server 2019 Standard" -SizeBytes 50GB
                     -DiskLayout "UEFI"
                     -VHDPath "C:\Temp\windowsServer2019.vhdx"`

## Requirements

The script needs Powershell 5.1 on a Windows System with administrator rights. Powershell ISE is currently supported, but will be deprecated in further releases, according microsofts policy. Consider using Visual Studio Code.

## License

The code is licensed under the MIT licencse (X11) as per the original source this implementation is based upon. See `LICENSE` for details.
