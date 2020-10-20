# gnuradio-install
安装gnuradio
>sudo apt install gnuradio  

安装UHD
>sudo add-apt-repository ppa:ettusresearch/uhd  
>sudo apt-get update  
>sudo apt-get install libuhd-dev libuhd003 uhd-host  

B210需要配置USB
>sudo wget -P /etc/udev/rules.d/ https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/uhd-usrp.rules  
>sudo udevadm control --reload-rules  
>sudo udevadm trigger  

运行uhd_find_devices以检查是否安装正确

固件下载
>uhd_images_downloader

如果提示连接错误，则需要科学上网
或进行离线安装，手动下载所需镜像并解压至/usr/share/uhd/images目录  
例如B210需下载[b2xx_common_fw_default-g2bdad498.zip](https://files.ettus.com/binaries/cache/usrp1/fpga-6bea23d/usrp1_b100_fw_default-g6bea23d.zip)和[b2xx_b210_fpga_default-gfde2a94e.zip](https://files.ettus.com/binaries/cache/b2xx/fpga-fde2a94eb/b2xx_b210_fpga_default-gfde2a94e.zip)  
>wget https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/b2xx_common_fw_default-g2bdad498.zip  
>wget https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/b2xx_b210_fpga_default-gfde2a94e.zip  
>sudo unzip b2xx_b210_fpga_default-gfde2a94e.zip -d /usr/share/uhd/images  

那么/usr/share/uhd/images目录应该存在三个文件
>/usr/share/uhd/images/usrp_b200_fw.hex  
>/usr/share/uhd/images/usrp_b200_bl.img  
>/usr/share/uhd/images/usrp_b210_fpga.bin

固件下载完后再运行uhd_find_devices应当可以显示设备详细信息。
