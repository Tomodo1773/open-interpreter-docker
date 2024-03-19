# open-interpreter-dockerプロジェクト詳細

## プロジェクトの概要

open-interpreter-dockerは、[Open Interpreter](https://github.com/KillianLucas/open-interpreter)をDockerコンテナ環境で利用するためのプロジェクトです。Open Interpreterは、対話型の自然言語プログラミング環境で、自然言語での対話を通じてプログラミングを行うことができます。

## ディレクトリ構成

プロジェクトのディレクトリ構成は以下の通りです。

- open-interpreter-docker/
- container-gui/
  - Dockerfile
- container-simple/
  - .devcontainer/
    - devcontainer.json
  - Dockerfile
- docker-compose.yml
- LICENSE
- README.md
- .env.sample

## 主要なファイルの説明

### container-gui/Dockerfile

このDockerfileでは、GUIを含むUbuntu 22.04ベースのDockerイメージを構築します。必要なパッケージやPythonライブラリ（numpy、matplotlib、pandas）をインストールし、日本語環境も設定しています。

### container-simple/.devcontainer/devcontainer.json

Visual Studio CodeのDevContainerの設定ファイルです。container-simple/Dockerfileを使用してコンテナを構築するための設定が記述されています。

### container-simple/Dockerfile

このDockerfileでは、シンプルなUbuntu 22.04ベースのDockerイメージを構築します。必要なパッケージやPythonライブラリ（numpy、matplotlib、pandas）をインストールし、最新バージョンのOpen Interpreterをインストールします。

### docker-compose.yml

Docker Composeの設定ファイルです。container-simple/Dockerfileを使用してopen-interpreterサービスを定義しています。ホストマシンのカレントディレクトリをコンテナ内の/appディレクトリにマウントし、.envファイルから環境変数を読み込むように設定されています。

### LICENSE

MITライセンスが適用されています。このライセンスの下で、ソフトウェアの使用、修正、配布などが許可されています。

### README.md

プロジェクトの概要を説明するREADMEファイルです。Open Interpreterのdocker環境について簡単に説明しています。

### .env.sample

環境変数のサンプルファイルです。OpenAIのAPIキーを設定するための例が記述されています。

```properties
OPENAI_API_KEY="your openai key"
```

実際に使用する際は、このファイルを`.env`にリネームし、実際のAPIキーを設定します。

## 使用方法

1. リポジトリをクローンまたはダウンロードします。
2. `.env.sample`ファイルを`.env`にリネームし、OpenAIのAPIキーを設定します。
3. docker-compose.ymlファイルがあるディレクトリで`docker-compose up -d`コマンドを実行し、コンテナを起動します。
4. `docker-compose exec open-interpreter /bin/bash`コマンドでコンテナ内にアクセスし、Open Interpreterを使用します。

以上が、open-interpreter-dockerプロジェクトの詳細です。このプロジェクトを使用することで、Open Interpreterを簡単にDocker環境で利用できます。
