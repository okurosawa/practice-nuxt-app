# ベースイメージを指定
# alpine は 軽量の linux OS
FROM node:14.16.1-alpine

# node.js の環境変数を定義する
# 本番環境では production
ENV NODE_ENV=development

# 雛形を生成するのに必要なパッケージのインストール
RUN npm install -g @vue/cli @vue/cli-init create-nuxt-app@2.15.0

# ディレクトリを移動する
WORKDIR /usr/src/app

# ポート3000番を開放する
EXPOSE 3000
