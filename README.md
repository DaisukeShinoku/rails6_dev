# Rails6開発環境構築

## 動作環境

### macOS Catalina 10.15.7
<br>
<br>

## 前提条件(下記インストール済)

### Virtual Box 6.1.16
### Vagrant 2.2.14
<br>
<br>

## 使用用途

<br>

「これからRailsを学びたい」というプログラミング初心者の方に向けて作成した「Rails6の開発環境を１時間以内で構築できるVagrantfile」です！
<br>
<br>

## 注意事項

<br>

※ これから先の説明は全てmacOS Catalina 10.15.7で確認済です。別OS・別バージョンをお使いの方は一部読み替えが必要な箇所がある場合があることをご了承ください。
<br>
<br>

## 使用方法

### 0. VirtualBox及びVagrantのインストールは事前に済ませておく<br>
<br>

### 1. vagrant-vbguestプラグインのインストール

<br>

```
$ vagrant plugin install vagrant-vbguest
```
<br>
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

```
$ vagrant init
```

上記コマンドでデフォルトの`Vagrantfile`が作成されます。<br>
<br>

デフォルト状態の`Vagrantfile`の中身をこのリポジトリに入ってるものにコピペで置き換えてください。
<br>
<br>


### 4. 仮想環境構築

<br>

```
$ vagrant up
```

上記コマンドで仮想環境を構築します(PCのスペックにもよりますが、15〜30分ほどかかります)。
<br>
<br>

### 5. 仮想環境へSSH接続

<br>

```
$ vagrant ssh
```
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


### 7. ssh接続の終了

<br>

```
$ exit
```

上記コマンドでSSH接続を終了することができます。

<br>
<br>


### 8. 仮想環境のマシンをシャットダウンする

<br>

```
vagrant halt
```
上記コマンドで仮想環境上のゲストOSをシャットダウンすることができます。<br>
<br>
再度立ち上げたい時は、`vagrant up`で立ち上げ`vagrant ssh`で接続します（2回目以降は数分で完了します）。
<br>
<br>

### 9. Railsアプリケーションの開発を進める方法

<br>

「2. 任意の場所にフォルダを作成」で作成したディレクトリ内に「6. Railsアプリケーション作成」で作成したRailsアプリと同名のファイルが作成されているはずなので、そこのコードを書き換えることで開発を進めます。<br>

`rails g controller Users` や `bundle install` 等のコマンドはSSH接続をした状態で、作成したRailsアプリケーションのディレクトリ上で叩くことになります。
<br>
<br>
<br>
