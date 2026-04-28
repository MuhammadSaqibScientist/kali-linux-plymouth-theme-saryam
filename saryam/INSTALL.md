# How to Install Saryam Plymouth

> [!IMPORTANT]  
> **Full Disk Encryption (LUKS) Required** > This theme is specifically engineered for systems using **Full Disk Encryption**. The "Shake" animation and password-dot logic rely on system flags that are only active during the LUKS decryption phase. On a standard (unencrypted) installation, the theme may only show the static logo or the transition animation.

Follow these steps to install the theme on Kali Linux.
### 1. Download
If you haven't cloned the full repo, download the `saryam` folder and move it to the system directory:
```bash
# Move your downloaded folder to the themes directory
sudo cp -r saryam /usr/share/plymouth/themes/
sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/saryam/saryam.plymouth 100
sudo update-alternatives --set default.plymouth /usr/share/plymouth/themes/saryam/saryam.plymouth
sudo update-initramfs -u
