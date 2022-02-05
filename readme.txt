

project
├ docker-compose.yml
│- nginx
│ 　└ nginx.conf
│- php
│ 　└ Dockerfile
│　 ├ php.ini
│　 

①プロジェクトフォルダを作りその中に docker-compose.ymlを配置
②①で作ったフォルダにnginxフォルダを作りそこにnginx.confを配置
③①で作ったフォルダにphpフォルダを作りそこにdockerfileとphp.iniを配置
④下記コマンドを実行
　docker-compose build
　docker-compose up -d
起動成功したらOK
⑤下記コマンドを実行
　docker-compose exec php bash
　composer create-project --prefer-dist laravel/laravel laravel "8.*"
  docker-compose down
⑥上記でインストールしたlaravelフォルダの中の.envファイルを開き該当箇所を書き換える
DB_CONNECTION=mysql
DB_HOST=db-host
DB_PORT=3306
DB_DATABASE=mydatabase
DB_USERNAME=root
DB_PASSWORD=password

⑦下記コマンド実行
　docker-compose up -d
　docker-compose exec php bash
　chmod -R 777 laravel/storage
　cd laravel/
　php artisan migrate
　下にアクセス
　http://localhost:8080/
　http://localhost:8888
  http://localhost:9001/
　laravelの画面が表示される＆phpmyadmin&minioが開くようになっている・・・・ハズ。
　おわり。