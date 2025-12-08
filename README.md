# news-app

##初回起動の手順
1. notionの環境変数ページの設定
2. dockerの起動
   ``` bash
   docker compose up -d
3. backendのコンテナに入る
  ``` bash
  docker compose run backend bash
4. migrationの実行
  ``` bash
  python manage.py migrate
