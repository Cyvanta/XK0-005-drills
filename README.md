## 🗂️ Day 4: Archives & Filesystems (Linux+ XK0-005)

---

### 📦 ARCHIVE COMMANDS (tar, gzip, zip)

🔹 `tar -cvf archive.tar folder/`  
→ Create a .tar archive from a folder  
- `c`: create  
- `v`: verbose (shows progress)  
- `f`: filename for output

🔹 `tar -xvf archive.tar`  
→ Extracts the `.tar` archive

🔹 `tar -czvf archive.tar.gz folder/`  
→ Compress tar with gzip at once (`z` = gzip)

🔹 `gzip filename.txt`  
→ Compresses the file into `filename.txt.gz`

🔹 `gunzip filename.txt.gz`  
→ Decompress `.gz` file

🔹 `zip archive.zip file1.txt file2.txt`  
→ Zip multiple files into one

🔹 `unzip archive.zip`  
→ Extract `.zip` archive

🧠 **Secret Tip:**  
Use `.tar.gz` or `.tgz` for backups or log rotation in scripts.

---

### 🧱 FILESYSTEM COMMANDS

🔹 `df -h`  
→ Show disk space (human-readable)

🔹 `du -sh folder/`  
→ Show size of a specific folder

🔹 `mount /dev/sdb1 /mnt/usb`  
→ Temporarily mount a disk/USB

🔹 `umount /mnt/usb`  
→ Unmount disk safely

🔹 `lsblk -f`  
→ List block devices with filesystem info (UUID, type)

🔹 `mkfs.ext4 /dev/sdb1`  
→ Format a device with ext4 filesystem  
⚠️ This will erase all data on the disk.

🔹 `blkid`  
→ Show filesystem labels and UUIDs

🔹 `tune2fs -l /dev/sda1`  
→ Show detailed info about ext2/3/4 partitions

🧠 **Secret Tip:**  
Always use `mount` + `df -h` to test if drives are properly mounted before copying large files.

---

### 🔧 PRACTICE LAB

```bash
# Create dummy folder & files
mkdir backup
touch backup/config.txt backup/data.db

# Archive using tar
tar -cvf backup.tar backup/

# Compress with gzip
gzip backup.tar  # becomes backup.tar.gz

# Extract it
gunzip backup.tar.gz
tar -xvf backup.tar

# Check space used
du -sh backup/

# Mount test drive (replace /dev/sdb1 with your USB)
sudo mkdir /mnt/usb
sudo mount /dev/sdb1 /mnt/usb

# Format drive to ext4 (DANGER: wipes data)
sudo mkfs.ext4 /dev/sdb1

# Unmount
sudo umount /mnt/usb

Command
What It Does
tar
Archive (no compression by default)
gzip
Compress individual files
zip
Archive + compress multiple files
mount
Temporarily attach filesystem
df
Show usage of mounted filesystems
mkfs
Format partition (create filesystem)
