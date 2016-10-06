# Vagrantまとめ
起動する仮想マシンやネットワーク・共有フォルダの設定はVagrantfileから行います(Rubyで書かれています)

[ドキュメント](http://docs.vagrantup.com/v2/vagrantfile/index.html)

## 最低限おさえるべきところ
起動するBox
```
config.vm_box = "box-name"
```
boxのURLを設定
```
config.vm.box_url = "box-url"
```
boxのipアドレス設定
```
config.vm.network "privatenetwork", ip:"192.168.33.10"
```
boxの共有フォルダの設定
```
config.vm.synced_folder
```

## よく使うコマンド
Vagrantディレクトリ設定
```
vagrant init [box name]
```
仮想マシン起動
```
vagrant up
```
仮想マシンにssh接続
```
vagrant ssh
```
仮想マシン一時停止
```
vagrant suspend
```
仮想マシン停止
```
vagrant halt
```
仮想マシン再開
```
vagrant resume
```
仮想マシン破棄
```
vagrant destroy
```
仮想マシン再起動
```
vagrant reload
```
仮想マシンの状態確認
```
vagrant status
```
仮想マシンのSSH設定確認
```
vagrant ssh-config
```
box 追加
```
vagrant box add [box_name] [box url]
```
box 削除
```
vagrant box remove [box_name]
```
box リスト表示
```
vagrant box list
```

## 人からもらったvagrant fileを使えるようにするまで
