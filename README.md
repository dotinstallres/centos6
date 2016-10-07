Setup local development environment for Dotinstall.com lessons. 
See main.yml for more details.

```
mkdir mycentos
cd mycentos
vagrant init bento/centos-6.8
# Vagrantfileの編集
vagrant up
vagrant ssh
sudo yum -y install git
sudo yum -y update
git clone https://github.com/dotinstallres/centos6.git
cd centos6
./run.sh
exec $SHELL -l
```

If you need to update the environment, please follow instructions below.

```
cd
cd mycentos # Vagrantfileがあるフォルダに移動
vagrant up
vagrant ssh
cd centos6
git pull --rebase
./run.sh
exec $SHELL -l
```

