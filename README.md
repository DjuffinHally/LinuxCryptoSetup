# LinuxCryptoSetup
Install linux from LUKS container with iso-image

********************
* Unpack initrd.gz *
********************
gunzip initrd.gz  
mkdir tmp2  
cd tmp2/  
cpio -id < ../initrd  
  
  
******************
* Pack initrd.gz *
******************
cd ~/repack/tmp2/  
find . | cpio --create --format='newc' > ../initrd  
cd ~/repack/  
gzip -f initrd   
cp initrd.gz ~/iso/initrd.gz   
cd ~/  
  
***************************
* Make ISO with grub-boot *
***************************
sudo grub-mkrescue -o grub.iso iso  
