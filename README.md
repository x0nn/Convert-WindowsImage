# Convert-WindowsImage
Creates a Windows VM for Hyper-V from a Windows-ISO

## Examples

Create a Windows Server 2019 VM

```Convert-WindowsImage -SourcePath "C:\Temp\windowsServer2019.iso" -VHDFormat "VHDX" `
                     -Edition "VHDX" -SizeBytes "50GB" `
                     -DiskLayout "UEFI" `
                     -VHDPath "C:\Temp\windowsServer2019.vhdx"```

## Requirements

The script needs Powershell 5.1 on a Windows System.

## License

The code is licensed under the MIT licencse (X11) as per the original source this implementation is based upon. See `LICENSE` for details.
