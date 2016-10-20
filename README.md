Setup local development environment for [Dotinstall.com](http://dotinstall.com/) lessons. 

#### how to install

```
# ホームディレクトリに移動
cd
# 仮想マシンをまとめるフォルダ（MyVagrant）を作る
mkdir MyVagrant
# MyVagrantに移動する
cd MyVagrant
# 仮想マシンを作るフォルダを作る（MyCentOS）
mkdir MyCentOS
# MyCentOSに移動する
cd MyCentOS
# 仮想マシン設定用のVagrantfileを作る
vagrant init bento/centos-6.8
# Vagrantfileを編集して仮想マシンのIPアドレスを192.168.33.10にする
sed -i '' -e 's/# config.vm.network "private_network", ip: "192.168.33.10"/config.vm.network "private_network", ip: "192.168.33.10"/' Vagrantfile
# 仮想マシンを起動する（少し時間かかります）
vagrant up
# OSを最新状態にアップデート（時間かかります）
sudo yum -y update
# スクリプトを入手するためのgitをインストール
sudo yum -y install git
# gitを使ってアプリケーション設定用のスクリプトをダウンロード
git clone https://github.com/dotinstallres/centos6.git
# centos6フォルダができるのでそちらに移動
cd centos6
# スクリプトを実行（時間かかります）
./run.sh
# もろもろの設定を反映
exec $SHELL -l
```

#### how to update

If you need to update the environment, please follow instructions below.

```
# ホームディレクトリに移動
cd
# 仮想マシンをまとめるフォルダ（MyVagrant）に移動する
cd MyVagrant
# 仮想マシンを作ったフォルダ（MyCentOS）に移動する
cd MyCentOS
# 仮想マシンを起動する（少し時間かかります）
vagrant up
# OSを最新状態にアップデート（時間かかります）
sudo yum -y update
# gitを使ってアプリケーション設定用のスクリプトを更新
git pull --rebase
# スクリプトを実行（時間かかります）
./run.sh
# もろもろの設定を反映
exec $SHELL -l
```

#### installed softwares

see main.yml for details.


