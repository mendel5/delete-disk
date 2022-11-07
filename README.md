# delete-disk
How to delete/ erase a HDD or SSD and similar topics

## Commands
Linux Terminal on Ubuntu / Linux Mint

```
sudo gnome-disks

!! Make sure to select the correct drive !!
sudo hdparm -I /dev/sda

sudo systemctl suspend
--> Press power button afterwards to resume

ATA Enhanced Secure Erase
```

Source:
- https://wiki.ubuntuusers.de/SSD/Secure-Erase/

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
