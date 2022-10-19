
![](https://raw.githubusercontent.com/frainzy1477/_xPanel/master/xpanel.png)


## Feature
- [Install Ioncube Loader](https://www.howtoforge.com/tutorial/how-to-install-ioncube-loader/#-configure-ioncube-loader-on-centos)
- [Google Analytic](https://analytics.google.com/analytics/web/) 
- [Google Console](https://console.developers.google.com/) 
- [Twilio](https://www.twilio.com/console/project/api-keys) 
- [AmazonSNS](https://aws.amazon.com/sns/)
- [Alphadvantage (Exchange rate key)](https://www.alphavantage.co/support/#api-key)
- [Paypal](https://developer.paypal.com/classic-home) 
- [Tawk](https://www.tawk.to/)
- [TelegramBot](https://telegram.org/)
- [Mailgun](https://www.mailgun.com/)
- [Twilio-Sendgrid](https://sendgrid.com/)
- [Hcaptcha](https://dashboard.hcaptcha.com/overview)


## PANEL INSTALL NGINX

```
Install Ioncube Loader 
Install CentOS 7x64 / Ubuntu 18.04+
Install Ngnix Server
Install PHP 7.3+
Install Database(mysql or mariab)
Install Cron
	
	
Download program code:
git clone https://github.com/philve/_xPanel.git tmp -b master && mv tmp/.git . && rm -rf tmp && git reset --hard

xpanel Configuration:
config/config.php

Import sql/xpanel.sql in the sql directory:


php composer.phar install

cp smarty_internal_resource_file.php /home/xxxx/xxx/vendor/smarty/smarty/libs/sysplugins

chmod -R 777 /home/xxxx/xxx

Create an administrator:
php cronjob createAdmin

Offline application:
php cronjob downloadApps

Open nginx Config:

Change the root line to:
root /home/xxxx/xxx/public;

Then add the following paragraph to the server:
location / {
    try_files $uri $uri/ /index.php$is_args$args;
}

Restart nginx:
service nginx restart

systemctl restart nginx 


crontab -e ，添加以下四段 (Add the following four paragraphs)
0 */1 * * * php /home/xxxx/xxxx/cronjob backup
0 */1 * * * php /home/xxxx/xxxx/cronjob rate
*/1 * * * * php /home/xxxx/xxxx/cronjob checkjob
59 23 * * * php /home/xxxx/xxxx/cronjob dailyjob


Management backend, system settings -> notification settings -> notification method -> Telegram information:
php cronjob setTelegram

```

## DOCKER BACKEND INSTALL

```
CENTOS 7
-------------------------------
cd /root && \
rm -rf install.sh && \
yum -y install epel-release wget bash zip unzip update && \
wget https://raw.githubusercontent.com/frainzy1477/_xPanel/master/backend/install.sh -O /root/install.sh && \
chmod +x  install.sh && \
bash install.sh
```

```
UBUNTU 18/20
-------------------------------
cd /root && \
rm -rf install.sh && \
apt install wget bash zip unzip && \
wget https://raw.githubusercontent.com/frainzy1477/_xPanel/master/backend/install.sh -O /root/install.sh && \
chmod +x  install.sh && \
bash install.sh
```
#Credits
- [XrayR-project](https://github.com/XrayR-project/XrayR) 后端
