# Brother MFC-L5850DW Arch Linux Driver

LPR and CUPS driver for the [Brother MFC-L5850DW printer](https://support.brother.com/g/b/producttop.aspx?c=us&lang=en&prod=mfcl5850dw_us)

## Installation

1. Build package

    ```console
    makepkg
    ```

2. Install package

   ```console
   sudo pacman -U brother-mfc-l5850dw-3.5.1-1-x86_64.pkg.tar.zst 
   ```

3. Add printer to [CUPS](http://localhost:631/) using `MFC-L5850DW series - IPP Everywhere` as the driver.

   Note: If CUPS shows an error that the printer cannot be located, enable Avahi's [.local hostname resolution](https://wiki.archlinux.org/title/Avahi#Hostname_resolution).

## Credits

This was built upon the [brother-hl-l8260cdw](https://aur.archlinux.org/packages/brother-hl-l8260cdw) package. Thanks [patstew](https://aur.archlinux.org/account/patstew)!
