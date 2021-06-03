
DOCKER INSTALL

```
CENTOS 7
-------------------------------
cd /root && \
rm -rf install.sh && \
yum -y install epel-release wget bash zip unzip update && \
wget https://raw.githubusercontent.com/frainzy1477/Xray-Backend/master/install.sh -O /root/install.sh && \
chmod +x  install.sh && \
bash install.sh
```

```
UBUNTU 18/20
-------------------------------
cd /root && \
rm -rf install.sh && \
apt install wget bash zip unzip && \
wget https://raw.githubusercontent.com/frainzy1477/Xray-Backend/master/install.sh -O /root/install.sh && \
chmod +x  install.sh && \
bash install.sh
```
