# Docker＿基本コマンド

## １．コンテナの一覧表示
```
docker ps
```
このコマンドは、現在実行中のDockerコンテナを表示します。

## ２．全てのコンテナの表示
```
docker ps -a
```
このコマンドは、実行中および停止中のすべてのDockerコンテナを表示します。

### ※コンテナの削除
```
docker rm [CONTAINER ID]or[NAMES]
```
## ３．イメージの一覧表示
```
docker images
```
このコマンドは、ローカルマシンに保存されているすべてのDockerイメージを表示します。

### ※イメージの削除
```
docker rmi [IMAGE ID]
```
## ４．コンテナのログ表示
```
docker logs [CONTAINER ID]or[NAMES]
```
指定したDockerコンテナのログを表示します。[CONTAINER ID]または[NAMES]には対象のコンテナのIDまたは名前を入力します。

## ５．コンテナの停止
```
docker stop [CONTAINER ID]
```
指定したDockerコンテナを停止します。[CONTAINER ID]には対象のコンテナのIDを入力します。

## ６．コンテナの再起動
```
docker restart [CONTAINER ID]
```
指定したDockerコンテナを再起動します。このコマンドは、コンテナの環境変数などを変更した後に使用されることがあります。

## ７．コンテナへの接続
```
docker exec -it [CONTAINER ID]or[NAMES] bash (or sh)
```
指定したDockerコンテナに対してインタラクティブなシェルセッションを開きます。[CONTAINER ID]または[NAMES]には対象のコンテナのIDまたは名前を入力します。

# ImageとContainerについて
Image = テンプレート（Dockerが用意してくれるもの）  
Container = インスタンス（分身）

Docker Hub から Docker Official Image である「postgres」を入手する。  
「postgres」は、コマンドを入力するだけで Image がダウンロードできる。  
tag でバージョンを確認してインストールする。

VSCode のターミナル（ ～/Desktop～ main± ）上で、「 docker pull postgres:14.10 」等とコマンドを叩く（実行する）

# Dockerfileの使い方
Dockerfile とは、image を元にコンテナを作成するファイル（専門的に言えば、ビルドするためのファイル）である。役割は（１）ライブラリなどのパッケージを入れる、（２）ファイルのコピーなどのコマンドを叩く、である。  

<< 以下、Dockerfile の導入の例 >>
```
FROM php:8.1-fpm
```
Docker の Image を選ぶ（FROM は一つだけ）
```
WORKDIR /var/www
```
ワーキングディレクトリ >>> どこで作業を行うか
```
ADD . /var/www
```
ADD はファイルやディレクトリをコンテナ内にコピーする命令で、/var/www はコンテナ内のコピー先のディレクトリを指定している。

<< ADD と COPY の違い >>  
ADD はファイルをコピーするだけでなく、（１）圧縮ファイルの展開 ... tar 形式のアーカイブを自動解凍、（２）URL からのダウンロード ... 外部の URL を指定可能、である。  
COPY は単純なコピーのみを行う。  


> [!NOTE]
> 特別な理由がない限り、通常は COPY の使用が推奨される  
> 圧縮ファイルの解凍や URL からの取得が必要な場合にのみ、ADD を使用すべき


# docker-composeの使い方


# 構築手順
postgresからImageをダウンロードし、「 docker run 」でコンテナを作成  

Dockerイメージからコンテナを作成する場合はdocker run -it **イメージID** bashコマンドでコンテナを作成しないと起動ができない


[参考＿YouTube](https://www.youtube.com/watch?v=dbIdWVFWF5Q&list=PLQ0-GXIIQG6cSXEnv2ZoJ5LDxhAaoDv_e&index=11&ab_channel=%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0%E5%AD%A6%E7%BF%92%E3%82%B5%E3%83%9D%E3%83%BC%E3%82%BF%E3%83%BC%E3%82%82%E3%82%93%E3%81%97%E3%82%87%E3%83%BC%E3%80%90IT%E3%83%A9%E3%83%9C%E3%80%91)


