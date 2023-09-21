# mini-blog-app-on-docker

## 前準備
* http://mini-blog.localhost でアクセスするので、hostsを書き換える必要あり

```
echo "127.0.0.1 mini-blog.localhost" | sudo tee -a /etc/hosts
```

## 起動

* 起動
```
docker-compose up -d --build
```

## 補足
* ドキュメントルート
  * /var/www/mini-blog.localhost/web
* 自作フレームワーク場所
  * applifcationディレクトリ  
