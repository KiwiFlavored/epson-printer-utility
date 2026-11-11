# Epson Printer Utility 1.2.3 Arch Linux Package

This is my attempt at packaging **Epson Printer Utility for Linux** for Arch Linux. It works with the `amd64` Deb release, version 1.2.3-1. It is available at the [Epson Download Center](https://download-center.epson.com). I have not been able to find a direct download link that will work in `PKGBUILD`, so you will have to download this yourself.

## Installation

1. Clone the GitHub repository:
    ```bash
    git clone https://github.com/KiwiFlavored/epson-printer-utility.git
    ```
    
2. Enter the repository directory:
   ```bash
   cd epson-printer-utility
   ```
   
4. Place the Epson Printer Utility `.deb` package inside the repository directory
   ```bash
   mv /path/to/deb/epson-printer-utility-1.2.3-1_amd64.deb .
   ```
   
6. Create and install the package:
   ```bash
   makepkg -si
   ```
   
8. Start and enable the `ecbd.service`:
    ```bash
    systemctl enable --now ecbd.service
    ```
    
## Usage

1. Ensure the `ecbd.service` is running.
   
2. Use the desktop application (installed to `/usr/share/applications/`) or run `epson-printer-utility` from the command line
