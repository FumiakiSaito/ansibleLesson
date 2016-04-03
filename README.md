# ansibleLesson

## 環境設定

```
vagrant init bento/centos-6.7
```

Vagrantfile  
(host=ansibleをインストールするホスト)  
(web=Apacheをインストールするホスト)  
(db=mysqlをインストールするホスト)


```
 #  config.vm.box = "bento/centos-6.7"

  config.vm.define "host" do |node|
    node.vm.box = "bento/centos-6.7"
    node.vm.hostname = "host"
    node.vm.network :private_network, ip: "192.168.43.51"
  end

  config.vm.define "web" do |node|
    node.vm.box = "bento/centos-6.7"
    node.vm.hostname = "web"
    node.vm.network :private_network, ip: "192.168.43.52"
  end

  config.vm.define "db" do |node|
    node.vm.box = "bento/centos-6.7"
    node.vm.hostname = "db"
    node.vm.network :private_network, ip: "192.168.43.53"
  end
```

サーバ起動
```
vagrant up
```

##hostでの操作

Ansibleインストール
```
wget https://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
sudo rpm -Uvh epel-release-6-8.noarch.rpm
sudo yum -y install ansible
```



