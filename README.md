# gcc-v14-installation
GCC 14 Installation Guide for Windows A comprehensive step-by-step guide to install GCC 14 on Windows using MinGW-w64 via MSYS2 or the Windows Subsystem for Linux (WSL).

# Installing GCC 14 on Windows

This repository provides a comprehensive guide to installing **GCC 14** on Windows using two different methods:
1. **MinGW-w64** via **MSYS2**
2. **Windows Subsystem for Linux (WSL)**

Choose the method that best fits your development environment and preferences.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Method 1: Using MinGW-w64 via MSYS2](#method-1-using-mingw-w64-via-msys2)
  - [Step 1: Download and Install MSYS2](#step-1-download-and-install-msys2)
  - [Step 2: Update MSYS2](#step-2-update-msys2)
  - [Step 3: Install GCC 14](#step-3-install-gcc-14)
  - [Step 4: Set Path Environment Variable](#step-4-set-path-environment-variable)
  - [Step 5: Verify Installation](#step-5-verify-installation)
- [Method 2: Using Windows Subsystem for Linux (WSL)](#method-2-using-windows-subsystem-for-linux-wsl)
  - [Step 1: Enable WSL](#step-1-enable-wsl)
  - [Step 2: Install a Linux Distribution](#step-2-install-a-linux-distribution)
  - [Step 3: Update Linux Distribution](#step-3-update-linux-distribution)
  - [Step 4: Add GCC 14 Repository](#step-4-add-gcc-14-repository)
  - [Step 5: Install GCC 14](#step-5-install-gcc-14)
  - [Step 6: Verify Installation](#step-6-verify-installation)
- [Troubleshooting](#troubleshooting)
- [License](#license)

## Prerequisites

- **Windows 10** or later.
- Administrative privileges for installing software and modifying environment variables.

## Method 1: Using MinGW-w64 via MSYS2

MinGW-w64 provides a complete Open Source programming toolset for developing native Windows applications.

### Step 1: Download and Install MSYS2

1. Navigate to the [MSYS2 Official Website](https://www.msys2.org/).
2. Download the installer suitable for your system.
3. Run the installer and follow the on-screen instructions to complete the installation.

### Step 2: Update MSYS2

1. Launch the MSYS2 terminal (`MSYS2 MSYS` or `MSYS2 MinGW 64-bit`).
2. Update the package database and core system packages by executing:
    ```bash
    pacman -Syu
    ```
3. If prompted, close and reopen the terminal.
4. Run the update command again to ensure all packages are up to date:
    ```bash
    pacman -Syu
    ```

### Step 3: Install GCC 14

1. In the MSYS2 terminal, install GCC 14 by running:
    ```bash
    pacman -S mingw-w64-x86_64-gcc
    ```
   *Replace `x86_64` with `i686` if you need the 32-bit version.*

### Step 4: Set Path Environment Variable

1. Add the path to the GCC binaries to your system's `PATH` environment variable. Typically, this path is:
    ```
    C:\msys64\mingw64\bin
    ```
   *Adjust the path if you installed MSYS2 in a different location or are using a 32-bit setup.*
   
2. To modify the `PATH`:
   - Press `Win + R`, type `sysdm.cpl`, and press Enter.
   - Navigate to the **Advanced** tab and click on **Environment Variables**.
   - Under **System variables**, find and select `Path`, then click **Edit**.
   - Click **New** and add `C:\msys64\mingw64\bin`.
   - Click **OK** to save changes.

### Step 5: Verify Installation

1. Open **Command Prompt** or **PowerShell**.
2. Run the following command to check the GCC version:
    ```bash
    gcc --version
    ```
3. You should see output indicating that GCC version 14 is installed.

## Method 2: Using Windows Subsystem for Linux (WSL)

WSL allows you to run a Linux environment directly on Windows without the overhead of a virtual machine.

### Step 1: Enable WSL

1. Open **PowerShell** as an Administrator.
2. Execute the following command to enable WSL:
    ```powershell
    wsl --install
    ```
3. Restart your computer if prompted.

### Step 2: Install a Linux Distribution

1. After enabling WSL, open the **Microsoft Store**.
2. Search for your preferred Linux distribution (e.g., **Ubuntu**) and install it.

### Step 3: Update Linux Distribution

1. Launch the installed Linux distribution from the Start menu.
2. Update the package lists and upgrade existing packages:
    ```bash
    sudo apt update
    sudo apt upgrade -y
    ```

### Step 4: Add GCC 14 Repository

1. Add the GCC toolchain PPA to get the latest GCC version:
    ```bash
    sudo add-apt-repository ppa:ubuntu-toolchain-r/test
    sudo apt update
    ```

### Step 5: Install GCC 14

1. Install GCC 14 and its C++ counterpart:
    ```bash
    sudo apt install gcc-14 g++-14
    ```

### Step 6: Verify Installation

1. Check the installed GCC version:
    ```bash
    gcc-14 --version
    ```
2. You should see output indicating that GCC version 14 is installed.

## Troubleshooting

- **MSYS2 Update Issues**: If you encounter issues while updating MSYS2, ensure that you have a stable internet connection and that no antivirus software is blocking the update process.
- **Environment Variable Not Set**: After setting the `PATH`, ensure that you open a new terminal window for changes to take effect.
- **GCC 14 Not Found in Repositories**: If GCC 14 is not available in the default repositories, check the MSYS2 or your Linux distribution's community resources for alternative installation methods.

## License

This project is licensed under the [MIT License](LICENSE).

