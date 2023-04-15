# delete-disk
How to delete/ erase a HDD or SSD and similar topics

## SATA HDDs and SSDs
>The only NIST approved method to securely erase a hard drive is by utilizing the `secure erase` internal command and that is what everyone should be doing. It is an ATA command, and covers (S)ATA interfaces.

Source: https://security.stackexchange.com/questions/5749/how-can-i-reliably-erase-all-information-on-a-hard-drive

### Tools
Tools that can be used to execute the "ATA Enhanced Secure Erase" command on SATA HDDs and SATA SSDs:
- Parted Magic: https://partedmagic.com/
- hdparm: https://wiki.archlinux.org/title/Solid_state_drive/Memory_cell_clearing (`SATA drive` section)
- SeaTools: https://www.seagate.com/support/downloads/seatools/

### GUI
```
# Open Gnome Disks program
sudo gnome-disks

# Get parameters for hard drive. !! Make sure to select the correct drive !!
sudo hdparm -I /dev/sda

sudo systemctl suspend
--> Press power button afterwards to resume

# In Gnome Disks do:
ATA Enhanced Secure Erase
```

Source: https://wiki.ubuntuusers.de/SSD/Secure-Erase/

## NVMe SSDs

### Terminal
- `Format` or `Sanitize` available
- https://wiki.archlinux.org/title/Solid_state_drive/Memory_cell_clearing (`NVMe drive` section)
- https://superuser.com/questions/1730791/can-someone-help-me-understand-the-differences-between-the-possible-actions-in-n
- https://tinyapps.org/docs/nvme-sanitize.html
- https://superuser.com/questions/1530363/how-to-securely-erase-an-nvme-ssd

### Parted Magic
- Parted Magic: https://partedmagic.com/

### Manufacturer tools
- Samsung Magician for Samsung SSDs (Windows)
- Crucial Storage Executive for Crucial SSDs (Windows)

## Links
- https://kb.iu.edu/d/aiut
- https://github.com/PartialVolume/shredos.x86_64
- https://wiki.ubuntuusers.de/SSD/Secure-Erase/
- https://partedmagic.com/secure-erase/
- https://www.ssdblog.de/2015/01/17/ssd-secure-erase-mit-parted-magic/
- https://www.youtube.com/watch?v=bjBJ2Vl7j_s Samsung Specific: How to Securely Erase an SSD, Samsung EVO PRO Plus NVMe M 2 SSD Secure Erase Windows 10
- https://partedmagic.com/nvme-secure-erase/
- https://superuser.com/questions/1530363/how-to-securely-erase-an-nvme-ssd
- http://blog.pythonaro.com/2018/05/how-to-securely-wipe-nvme-drive.html
- https://www.mankier.com/1/nvme-format
- https://wiki.archlinux.org/title/Solid_state_drive/Memory_cell_clearing
- https://archive.kernel.org/oldwiki/ata.wiki.kernel.org/index.php/ATA_Secure_Erase.html
- https://www.thomas-krenn.com/de/wiki/SSD_Secure_Erase
- https://www.thomas-krenn.com/en/wiki/Perform_a_SSD_Secure_Erase
- https://askubuntu.com/questions/17640/how-can-i-securely-erase-a-hard-drive
- https://security.stackexchange.com/questions/5749/how-can-i-reliably-erase-all-information-on-a-hard-drive
