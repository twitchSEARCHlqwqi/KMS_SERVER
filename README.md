
#VMware Workstation Pro 16永久激活碼激活秘訣
官網: https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html
下載link: https://download3.vmware.com/software/wkst/file/VMware-workstation-full-16.1.2-17966106.exe
------ZF3R0-FHED2-M80TY-8QYGC-NPKYF------
------YF390-0HF8P-M81RQ-2DXQE-M2UT6------
------ZF71R-DMX85-08DQY-8YMNC-PPHV8------

#Ubuntu 20.04.2.0 LTS
https://ubuntu.com/download/desktop/thank-you?version=20.04.2.0&architecture=amd64

# KMS_SERVER
sudo -i
apt update && apt upgrade
apt install git -y
sudo apt-get install -y net-tools
wget --no-check-certificate https://github.com/teddysun/across/raw/master/kms.sh && chmod +x kms.sh && ./kms.sh

-------查看端口號1688的監聽情況-------
netstat -nxtlp | grep 1688

-------如下表示OK了-------
tcp        0      0 0.0.0.0:1688                0.0.0.0:*                   LISTEN      3200/vlmcsd         
tcp        0      0 :::1688                     :::*                        LISTEN      3200/vlmcsd

-------腳本安裝完成後，將KMS服務加入啟動自啟動-------
啟動：/etc/init.d/kms start
停止：/etc/init.d/kms stop
重啟：/etc/init.d/kms restart
狀態：/etc/init.d/kms status

卸載方法  以root權限運行以下命令
./kms.sh uninstall

#如何使用 KMS 服務？

-------使用管理員權限運行cmd 查看系統版本-------
wmic os get caption

-------使用管理員權限運行cmd 安裝從上面列表得到的鍵-------
slmgr /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX   | Windows 10 專業版 Key
https://docs.microsoft.com/zh-cn/windows-server/get-started/kmsclientkeys

-------使用管理員權限運行cmd將KMS Server 地址設置為你自己的IP或域名，最好還有上端口號（:1688）-------
slmgr /skms 192.168.88.135

-------使用管理員權限運行cmd手動激活系統-------
slmgr /ato

-------KMS 方式激活只有 180 天-------
所以每隔一段時間系統會自動向KMS服務請求續期，請確保你自己的KMS服務正常運行^^


