# raspberry-ansible

AnsibleでRaspberry Pi 3 Model BにWordPress環境を構築するサンプルPlaybookです。

## Requirements
- ansible 2.2 or later

## Usage

### Raspberry Pi

以下URLのRaspbianをインストールしたRaspberry Pi 3 Model Bを準備し、
SSH接続可能な環境を構築しておいてください。

- Raspbian STRETCH WITH DESKTOP(Release date:2017-09-07)
https://www.raspberrypi.org/downloads/raspbian/


### Download
適当なディレクトリにPlaybookをダウンロードしてください。

```
$ git clone https://github.com/rednes/raspberry-ansible.git
$ cd raspberry-ansible
```

### Edit hosts

hosts.sampleファイルがあるので、hostsにコピーしてください。
```
$ cp hosts.sample hosts
```

hostsにRaspberry PiのIPアドレスを記載してください。

```
[raspberry-pi]
XX.XX.XX.XX # set your environment
```

### Execute ansible

ansibleを実行してsshのパスワードを入力してください。
対象としたRaspberry PiにWordPress環境が構築できます。

```
$ ansible-playbook site.yml -v --ask-pass -u pi
```

### Setup WordPress

構築したWordPressにアクセスしてWordPressのセットアップを行ってください。
MySQLのDB名、ユーザー名、パスワードは以下をデフォルト値にしています。

* データベース名：wordpress
* ユーザー名：wordpress-user
* パスワード：wordpress

```
http://(Raspberry PiのIPアドレス)/wordpress/wp-admin/setup-config.php
```
