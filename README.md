# gnuradio-install
以下方法只安装ubuntu源自带的gnuradio3.7与uhd3.10版本，兼容性比较好。  
安装gnuradio
>sudo apt install gnuradio  

安装UHD
>sudo apt-get install libuhd-dev libuhd003.010.003 uhd-host  

其中，B210需要配置USB
>sudo wget -P /etc/udev/rules.d/ https://raw.githubusercontent.com/zhjc1124/gnuradio-install/main/uhd-usrp.rules  
>sudo udevadm control --reload-rules  
>sudo udevadm trigger  

运行uhd_find_devices以检查安装是否成功  


固件下载
>uhd_images_downloader  

如果提示连接错误，则需要科学上网
或进行离线安装  
>wget https://mirrors.zju.edu.cn/gentoo/distfiles/d4/uhd-images_003.010.003.000-release.zip  
>unzip uhd-images_003.010.003.000-release.zip  
>sudo cp -r ./uhd-images_003.010.003.000-release/* /usr  

固件下载完后再运行uhd_find_devices应当可以显示设备详细信息。  

最后运行uhd_usrp_probe进行配置  
