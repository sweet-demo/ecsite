FROM nginx:alpine

# Nginxの設定ファイルをコピー
COPY infra/web/default.conf /etc/nginx/conf.d/default.conf

RUN apk add --no-cache openssl

# SSL証明書用のディレクトリを作成
RUN mkdir -p /etc/nginx/ssl

# 自己署名証明書を生成
# RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
#     -keyout /etc/nginx/ssl/nginx.key \
#     -out /etc/nginx/ssl/nginx.crt \
#     -subj "/C=JP/ST=Tokyo/L=Tokyo/O=Local/CN=localhost"

# 証明書の権限を設定
RUN chmod 644 /etc/nginx/ssl/nginx.crt && \
    chmod 600 /etc/nginx/ssl/nginx.key

# ポート80と443を公開
EXPOSE 80 443

# Nginxを起動
CMD ["nginx", "-g", "daemon off;"] 
