Setup local development environment for [Dotinstall.com](http://dotinstall.com/) lessons. 

#### how to install

```
mkdir mycentos
cd mycentos
vagrant init bento/centos-6.8
# Edit Vagrantfile
vagrant up
vagrant ssh
sudo yum -y install git
sudo yum -y update
git clone https://github.com/dotinstallres/centos6.git
cd centos6
./run.sh
exec $SHELL -l
```

#### how to update

If you need to update the environment, please follow instructions below.

```
cd
cd mycentos # Vagrantfileがあるフォルダに移動
vagrant up
vagrant ssh
cd centos6
sudo yum -y update
git pull --rebase
./run.sh
exec $SHELL -l
```

#### installed softwares

see main.yml for details.


