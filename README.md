【参考サイト：laravel\_環境構築】
https://zenn.dev/404_notfound/articles/38e296b353c02e
【参考サイト：php_Myadmin 追加の記述】
https://zenn.dev/peishim/articles/f7a76ae6c253e4

【client 側の起動方法】

1. client ディレクトリへ
   cd client

2. npm run dev で起動する

【server 側の起動方法】

1. docker-compose up -d で起動する
   ※docker ファイルや docker-compose.yml ファイルを変更した際は、docker-compose up -d --build で起動する

2. docker の起動が完了したら、docker ps でコンテナを確認して lara_base_web のコンテナに docker-compose exec lara_base_web bash で接続する

3. コンテナ直下にて php artisan serve コマンドを実行して laravel を起動する（migrate の際もコンテナ内で実行すること）
   ※注意：コンテナ内で laravel を起動する際は、以下のコマンドのようにホストとポート番号を指定する
   php artisan serve --host=0.0.0.0 --port=8000
