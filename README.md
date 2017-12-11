# LinuxCryptoSetup
Install linux from LUKS container with iso-image

cd ~/repack/tmp2/
find . | cpio --create --format='newc' > ../initrd
cd ~/repack/
gzip -f initrd 
cp initrd.gz ~/iso/initrd.gz 
cd ~/
sudo grub-mkrescue -o grub.iso iso
