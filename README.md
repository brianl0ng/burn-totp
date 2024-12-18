# Tool to configure OTPC-P2-i Token from https://token2.com/

**Disclaimer: This program comes without any warranty.**

**Note: This project is not affiliated with token2.com in any way.**

**Danger: Random commands to Token can brick it.**

SySS wrote a [report](https://blog.syss.com/posts/security-of-totp-tokens/).

## Requirements:
*   PN533 NFC Writer. Tested with "StickID Writer" from token2.
*   OTPC-P2-i Token.
*   python: 3.11 or later
*   pypi packages: [nfcpy](https://pypi.org/project/nfcpy/), [sm4](https://pypi.org/project/sm4/)  (use a venv!)

**Don't run as root. Add udev rule:**
```
ACTION=="add", SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device", ATTRS{idVendor}=="04cc", ATTRS{idProduct}=="2533", OWNER="root", GROUP="plugdev", MODE="0660"
```

## Usage

```
# Read current config:
burn_totp

# Reconfigure and write seed
burn_totp -c -s JBSWY3DPK5XXE3DE
```
