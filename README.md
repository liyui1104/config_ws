# **config\_ws**


### **Introduction**
This repository is used to store scripts for installing and configuring the development environment.







### **Tutorial for installing**
Download the codes of this repository in your home directory.





### **Tutorial for using**
**Firstly, you are expected to come in config\_ws directory in advance.**

#### **1 install\_ros\_by\_fishros.sh**
* Effect

Install ROS in your Ubuntu.



* Usage

```bash
sudo chmod +x install_ros_by_fishros.sh
./install_ros_by_fishros.sh
```


#### **2 backup\_raspberryPi.sh**
* Effect

Backup raspberryPi OS as an image file.



* Usage for internal storage (Not recommended)
   1. You should set the password for root in advance. Or run  **`sudo passwd root`** to set it.

```bash
su
chmod +x backup_raspberryPi.sh
./backup_raspberryPi.sh raspi.img
```
   2. After tens of minutes, you will get your backup .img file named raspi.img



* **Usage for external storage (Recommended)**
   1. mount your U disk
      1. Run **`fdisk -l`** to get your the device name for your U disk (Such as **/dev/sda4**)
      2. If the filesystem of U disk is FAT32 (**Its file size can't over 4G, and the .img will over**), you should exchange one or change the filesystem.
      3. If the filesystem of U disk is NTFS, you can run **`mount -t ntfs /dev/sdb1 /media`** (must be **/media** )
      4. Check up the content of U disk, you can run **`cd /media && ls`**
   2. start to backup

```bash
su
chmod +x backup_raspberryPi.sh
./backup_raspberryPi.sh /media/raspi.img
```
   3. Check up the content of U disk, you can run **`cd /media && ls`**
   4. Run **`umount /media/`**
   5. Run **`shutdown now `** then take out U disk



**If you want to recover your raspberryPi OS (ubuntu), you should run next .sh file or use software DiskGenius(recommended).**

* **Usage for using DiskGenius to recover OS**
   1. Burn .img into SD card in advance.
   2. Open DiskGenius
   3. Extend the boot partition
   4. Wait for success



#### **3 resize\_raspberryPi.sh**
* Effect

Resize raspberryPi OS when you have burned system in your SD card.



* Usage

```bash
su
chmod +x install_ros_fishros.sh
./install_ros_fishros.sh
```


#### **4 update\_rosdep\_tsinghua.sh**
* Effect

Implement rosdep update



* Usage

```bash
sudo chmod +x update_rosdep_tsinghua.sh
./update_rosdep_tsinghua.sh
```

#### **5 install_cartographer(TODO)**


### **References**
1. install\_ros\_by\_fishros.sh from [https://github.com/fishros/install](https://github.com/fishros/install)
2. backup\_raspberryPi.sh from [https://github.com/nanhantianyi/rpi-backup](https://github.com/nanhantianyi/rpi-backup)
3. resize\_raspberryPi.sh from [https://github.com/nanhantianyi/rpi-backup](https://github.com/nanhantianyi/rpi-backup)
4. update\_rosdep\_tsinghua.sh from [https://gitee.com/ncnynl/rosdep](https://gitee.com/ncnynl/rosdep)