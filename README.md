# python-app

# メモ

## 手順

- 環境構築
  https://qiita.com/a-im12/items/7f3c8d1212dac3685e77
- index を繋ぐ
  https://rightcode.co.jp/blog/become-engineer/django-diary-app-make-top-screen

## 手こずったところ

- VScode で実行しているコンテナへアクセス

  1.  TERMINAL で新しくタブを生成
  1.  docker-compose ps
      → コンテナ名を確認する
  1.  docker container exec -it {コンテナ名} bash
      docker container exec -it django bash
      → コンテナに入る
  1.  django-admin startproject python_django_app
      →django プロジェクト生成コマンド

- サーバーの起動

> python3 manage.py runserver 0.0.0.0:8000

コンテナに入って`manage.py`があるところで実行しないとできません

- マイグレーションの実施
  > python3 manage.py makemigrations

これ実施前に、下記設定を追加しないといけない
setting.py

```
INSTALLED_APPS = [
    〜省略〜
    'django.contrib.staticfiles',
    'diary', # 追加
]
```
