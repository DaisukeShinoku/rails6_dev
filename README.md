# Rails6開発環境構築

## 動作環境

### macOS Catalina 10.15.7
<br>
<br>

## 前提条件(下記インストール済)

### Virtual Box 6.0.22
### Vagrant 2.2.9
<br>
<br>

## 使用用途

「これからRailsを学びたい」というプログラミング初心者の方に向けて作成した「Rails6の開発環境をサクッと構築できるVagrantfile」です！
<br>
<br>

## 注意事項

※ これから先の説明は全てmacOS Catalina 10.15.7で確認済です。別OS・別バージョンをお使いの方は一部読み替えが必要な箇所がある場合があることをご了承ください。
<br>
<br>

## 使用方法

### 1. VirtualBox及びVagrantのインストールは事前に済ませておく<br>
<br>

### 2. 任意の場所にフォルダを作成
<br>

```
$ mkdir rails6_dev
$ cd rails6_dev
```
<br>

### 3. Vagrantfile作成

<br>

`vagrant init`コマンドでデフォルトの`Vagrantfile`が作成されます。<br>
デフォルト状態の`Vagrantfile`の中身をこのリポジトリに入ってるものにコピペで置き換えてください。
<br>
<br>


### 4. 仮想環境構築

<br>

`vagrant up`コマンドで仮想環境を構築します(PCのスペックにもよるが15〜30分ほどかかります)。
<br>
<br>

### 5. 仮想環境へSSH接続

<br>

`vagrant ssh`コマンドで出来上がった仮想環境にSSH接続します。
<br>
<br>

### 6. Railsアプリケーション作成

<br>

```
vagrant@vagrant:~$ cd work
vagrant@vagrant:~/work$ rails new sample-app
vagrant@vagrant:~/work$ cd sample-app
vagrant@vagrant:~/work/sample-app$ rails s -b 0.0.0.0
```


この状態で`http://localhost:3000/`にアクセスすると、`Yay! You’re on Rails!`のデフォルト画面が表示されます。
<br>
<br>


### 7. ssh接続から抜ける

<br>

`exit`コマンドで抜けることができます。

<br>
<br>


### 8. 仮想環境のマシンをシャットダウンする

<br>

`vagrant halt`コマンドでシャットダウンすることができます。<br>
<br>
再度立ち上げたい時は、`vagrant up`で立ち上げて`vagrant ssh`で接続します（2回目以降は数分で立ち上がります）。
<br>
<br>

### 9. 作成したRailsのコードを編集したい時は

<br>
「2. 任意の場所にフォルダを作成」で作成したディレクトリ内に「6. Railsアプリケーション作成」で作成したRailsアプリと同名のファイルが作成されているはずなので、それを編集します。
<br>
<br>
<br>

### 10. 仮想環境とうまく同期していない場合

<br>

`
vagrant plugin install vagrant-vbguest
`で　プラグインを入れてから再度`vagrant up`するとうまくいくことが多いです。
<br>
<br>
<br>

## 全然うまくいかねーよって人は

<br>
https://twitter.com/oniki_dwc_sjk
<br>
↑ツイッターのDMで質問してください！
