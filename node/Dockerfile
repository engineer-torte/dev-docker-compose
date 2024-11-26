# node.jsとnpmのバージョンをビルド変数から取得する
ARG NODE_VERSION
ARG NPM_VERSION

FROM node:${NODE_VERSION}-slim

RUN apt update && \
    apt upgrade -y && \
    apt install -y git

# npm installを通すためにソースをコピーしてくる
WORKDIR /var/www/app
COPY ./app /var/www/app

# npmを最新バージョンに更新
RUN npm install -g npm@${NPM_VERSION}

# npmキャッシュをクリア
RUN npm cache clean --force

# Firebase CLIをインストール
RUN npm install -g firebase-tools

# # パッケージをインストールする
# RUN npm install

# # Next.jsのビルド
# RUN npm run build

# # 本番用のコマンドを実行
# CMD ["npm", "start"]