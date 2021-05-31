# odoo12-saas-on-GCP

1.  GPC申請VM

![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/1.png)
![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/2.png)
![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/3.png)
![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/4.png)
![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/5.png)

2.  GCP/XSHELL 使用SSH連線
    + XSHELL上使用工具/新使用者金鑰精靈(2048/RSA/空白)產生金鑰
    + 上傳到GOOGLE指令
      + cd ~/.ssh
      + vi authorized_keys
      + 貼上XSHELL產生的金鑰
    + 設定XSHELL連線(PORT:22/IP/PUBLIC KEY連線)
    + 到GCP 使用sudo passwd username 修改使用者密碼，並新增sudo權限 sudo adduser username sudo(需重新連線才啟用)

3.  安裝ODOO
  > 
    sudo wget https://raw.githubusercontent.com/Yenthe666/InstallScript/12.0/odoo_install.sh
    sudo chmod +x odoo_install.sh
    sudo ./odoo_install.sh
    sudo service-odoo server start
    http://35.201.191.91:8069/web/database/selector
    
![Alt text](https://github.com/ksharry/odoo12-saas-on-GCP/blob/main/png/6.png)

3.  安裝相關依賴
  > 
    sudo apt-get install xvfb libfontconfig wkhtmltopdf  #python套件
    sudo service odoo-server stop    #ngix開始
    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install nginx
    http://35.201.191.91/

4. 申請DNS
  > 
    https://www.noip.com/
    進行註冊
    填寫三組網域(實際需要四組)
    下載NO IP DCU
