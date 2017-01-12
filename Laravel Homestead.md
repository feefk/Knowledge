Laravel Homestead Install
=====

### 1. Install Virtualbox
* ubuntu:
```javascript 
sudo sh -c "echo 'deb http://download.virtualbox.org/virtualbox/debian '$(lsb_release -cs)' contrib non-free' > /etc/apt/sources.list.d/virtualbox.list" 
wget -q http://download.virtualbox.org/virtualbox/debian/oracle_vbox.asc -O- | sudo apt-key add - 
sudo apt-get update
sudo apt-get install virtualbox dkms
```
* mac:
download virtual box: [download](https://www.virtualbox.org/wiki/Downloads)

### 2. Install vagrant
download vagrant: [download](https://www.vagrantup.com/)

### 3. Download project vagrant package box
* package profile:
```
os: linux 14.04
php: 5.6 (http://devdocs.magento.com/guides/v2.0/install-gde/prereq/php-ubuntu.html#instgde-prereq-php5.66-install-ubuntu)
nginx: 1.8
...
...
```
* download lastest package:
http://192.168.1.29/files/packages to ~/vbox/

* edit metadata.json(in ~/vbox)
```
{
    "name": "laravel/homestead",
    "versions": [{
        "version": "0.3.3",
        "providers": [{
            "name": "virtualbox",
            "url": "homestead-virtualbox-0.3.3.box" //注意替换成你的box的文件名
        }]
    }]
}
```
* run command below(注意版本问题)
```
cd ~
git clone http://120.26.236.33:8089/gitlab/root/homestead.git Homestead 
cd Homestead
bash init.sh
```

* 这会自动创建一个Homestead.yaml配置文件。
```
vim ~/.homestead/Homestead.yml
```

* start vagrant
```
vagrant up
```

* 参考
https://solarhell.com/post/2016/04/homestead
