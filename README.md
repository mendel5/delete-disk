# delete-disk
How to delete/ erase a HDD or SSD and similar topics

## SATA HDDs and SSDs
### Quote 1
>The only NIST approved method to securely erase a hard drive is by utilizing the `secure erase` internal command and that is what everyone should be doing. It is an ATA command, and covers (S)ATA interfaces.

Source: https://security.stackexchange.com/questions/5749/how-can-i-reliably-erase-all-information-on-a-hard-drive

### Quote 2
> Secure erase overwrites all user data areas with binary zeroes. Enhanced secure erase writes predetermined data patterns (set by the manufacturer) to all user data areas.

Source: https://www.skrilnetz.net/the-truth-about-how-to-securely-erase-a-solid-state-drive-ssd/

### Quote 3
> An overwrite command in the ATA standard (as ‘Security Erase Unit’) that leverages a firmware-based process to overwrite the media. This command typically executes substantially faster than attempting to rewrite through the native read and write interface. There are up to two options, ‘`normal erase`’ and ‘`enhanced erase`’.
> 
> The `normal erase`, as defined in the standard, is only required to address data in the contents of LBA 0 through the greater of READ NATIVE MAX or READ NATIVE MAX EXT, and replaces the contents with 0s or 1s.
>
> The `enhanced erase` command specifies that, “…all previously written user data shall be overwritten, including sectors that are no longer in use due to reallocation” and the contents of the media following Sanitization are vendor unique. The actual action performed by an enhanced erase varies by vendor and model, and could include a variety of actions that have varying levels of effectiveness.
>
> The secure erase command is not defined in the SCSI standard, so it does not apply to media with a SCSI interface.

Source: https://csrc.nist.gov/glossary/term/secure_erase_command

### Quote 4
> A standard `Secure Erase` overwrites all the data on the disk with zeros. On SSDs, the process is different, and often much faster, but the end result is the same. This is the standard option provided with most drives.
>
> `Enhanced Secure Erase` is provided on some newer or more specialist drives. It writes predetermined patterns on to the disk, usually multiple times. As a result of this, it takes a lot longer to perform. It is much harder to verify the disk has been erased in this case, because the patterns are manufacturer-specific.

Source: https://www.hamishmb.com/files/support/diskverifier/ch02s11.html

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

## Links 1
- https://github.com/PartialVolume/shredos.x86_64 Alternative to DBAN

## Links 2
- https://kb.iu.edu/d/aiut
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
- https://superuser.com/questions/1518253/ssd-what-is-the-difference-between-sanitize-secure-erase
- https://support-de.wd.com/app/answers/detailweb/a_id/43893/~/was-ist-der-unterschied-zwischen-secure-erase-und-sanitize%3F
- https://tinyapps.org/docs/ata_sanitize_hdparm.html
- https://security.stackexchange.com/questions/62253/what-is-the-difference-between-ata-secure-erase-and-security-erase-how-can-i-en
