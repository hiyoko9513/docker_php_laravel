# laravel docker template

## 動作確確認環境
mac os

## laravelプロジェクトの作成
### 1. docker起動
```shell
$ cp -f ./build/docker/.env.example ./build/docker/.env
$ docker compose --env-file ./build/docker/.env up -d --build
$ docker compose --env-file ./build/docker/.env exec workspace bash
```
### 2. laravel作成
```shell
$ composer create-project laravel/laravel
```

### 3. laravel起動
```shell
# laravel用(環境依存有)
$ composer install
$ cp .env.docker.example .env
$ php artisan key:generate
$ php artisan jwt:secret
$ php artisan storage:link
$ sudo chmod -R 775 bootstrap/cache && sudo chmod -R 775 storage
$ sudo chown -R www-data:admin storage && sudo chown -R www-data:admin bootstrap/cache
$ php artisan migrate:fresh --seed
```
### 4. laravel起動確認

## コマンドリスト


## ドキュメント
- [git commit rule](./docs/markdown/git/commit.md)
- [git branch rule](./docs/markdown/git/branch.md)
- [git release-drafter document](./docs/markdown/git/release-drafter.md)
