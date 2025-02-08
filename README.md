# Docker＿基本コマンド

## １．コンテナの一覧表示
### docker ps

このコマンドは、現在実行中のDockerコンテナを表示します。

## ２．全てのコンテナの表示
### docker ps -a

このコマンドは、実行中および停止中のすべてのDockerコンテナを表示します。

### ※コンテナの削除
### docker rm [CONTAINER ID]or[NAMES]

## ３．イメージの一覧表示
### docker images

このコマンドは、ローカルマシンに保存されているすべてのDockerイメージを表示します。

### ※イメージの削除
### docker rmi [IMAGE ID]

## ４．コンテナのログ表示
### docker logs [CONTAINER ID]or[NAMES]

指定したDockerコンテナのログを表示します。[CONTAINER ID]または[NAMES]には対象のコンテナのIDまたは名前を入力します。

## ５．コンテナの停止
### docker stop [CONTAINER ID]

指定したDockerコンテナを停止します。[CONTAINER ID]には対象のコンテナのIDを入力します。

## ６．コンテナの再起動
### docker restart [CONTAINER ID]

指定したDockerコンテナを再起動します。このコマンドは、コンテナの環境変数などを変更した後に使用されることがあります。

## ７．コンテナへの接続
### docker exec -it [CONTAINER ID]or[NAMES] bash (or sh)

指定したDockerコンテナに対してインタラクティブなシェルセッションを開きます。[CONTAINER ID]または[NAMES]には対象のコンテナのIDまたは名前を入力します。



# ImageとContainerについて



# Dockerfileの使い方



# docker-composeの使い方



