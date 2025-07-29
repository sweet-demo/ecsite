FROM nginx:alpine

# Nginxの設定ファイルをコピー
COPY infra/web/default.conf /etc/nginx/conf.d/default.conf

RUN apk add --no-cache openssl

# SSL証明書用のディレクトリを作成
RUN mkdir -p /etc/nginx/ssl

# SSL証明書ファイルをコピー
COPY infra/web/ssl/nginx.crt /etc/nginx/ssl/nginx.crt
COPY infra/web/ssl/nginx.key /etc/nginx/ssl/nginx.key

# 証明書の権限を設定
RUN chmod 644 /etc/nginx/ssl/nginx.crt && \
    chmod 600 /etc/nginx/ssl/nginx.key

# ポート80と443を公開
EXPOSE 80 443

# Nginxを起動
CMD ["nginx", "-g", "daemon off;"] 
