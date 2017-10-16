```
mkdir app
docker-machine create default -d "virtualbox" --virtualbox-share-folder="D:\dev\catine\docker:docker"

# установить переменные окружения
docker-machine env default
eval $("C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env default)

docker-compose run composer bash
rm /var/www/app/.gitkeep && composer create-project --prefer-dist laravel/laravel /var/www/app

# docker-compose run composer composer install -d /var/www/app
docker-compose up или docker-compose up -d
```

Поправить в windows файл `hosts`: взять ip из `docker-machine env default` и прописать его к домену `app.dev`.