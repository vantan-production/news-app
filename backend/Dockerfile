FROM python:3.12
# デバックをしやすくするための設定
ENV PYTHONUNBUFFERED=1
WORKDIR /backend
# pythonとmysqlを繋ぐためのライブラリ
RUN apt-get update && apt-get install -y --no-install-recommends \
    gcc \
    default-libmysqlclient-dev \
    pkg-config \
    && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
# pythonのパッケージをインストール
RUN pip install --no-cache-dir -r requirements.txt
RUN pip install mysqlclient

COPY . .
    
EXPOSE 8001
# コンテナ起動時に実行されるコマンド
CMD ["python", "manage.py", "runserver", "0.0.0.0:8001"]
