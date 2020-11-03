# gnuradio-install 
仅适用于Ubuntu16.04或Ubuntu18.04
以下方法只安装ubuntu源自带的gnuradio3.7与uhd3.10以下的版本，兼容性比较好。  
安装gnuradio
>sudo apt install gnuradio  

安装UHD（for Ubuntu 16.04）
>sudo apt-get install libuhd-dev libuhd003.010.003 uhd-host  

安装UHD（for Ubuntu 16.04）
>sudo apt-get install libuhd-dev libuhd003 uhd-host  


其中，B210需要配置USB
>sudo wget -P /etc/udev/rules.d/ https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/uhd-usrp.rules  
>sudo udevadm control --reload-rules  
>sudo udevadm trigger  

运行uhd_find_devices以检查安装是否成功  


固件下载  
>uhd_images_downloader  

如果提示连接错误，则需要科学上网  
或进行离线安装  
18.04请使用  
>wget https://mirrors.zju.edu.cn/gentoo/distfiles/d4/uhd-images_003.010.003.000-release.zip  
>unzip uhd-images_003.010.003.000-release.zip  
>sudo cp -r ./uhd-images_003.010.003.000-release/* /usr  

16.04请使用  
>wget https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/uhd-images_003.009.002-release.zip 
>unzip uhd-images_003.009.002-release.zip
>sudo cp -r ./uhd-images_003.010.003.000-release/* /usr  

固件下载完后再运行uhd_find_devices应当可以显示设备详细信息。  

最后运行uhd_usrp_probe进行配置  


如果你用的源安装或者其他方法安装，uhd版本不是3.10以下，可能需要按下述方法下载镜像  
例如B210需下载[b2xx_common_fw_default-g2bdad498.zip](https://files.ettus.com/binaries/cache/usrp1/fpga-6bea23d/usrp1_b100_fw_default-g6bea23d.zip)  
>wget https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/b2xx_common_fw_default-g2bdad498.zip  
>sudo unzip b2xx_common_fw_default-g2bdad498.zip -d /usr/share/uhd/images