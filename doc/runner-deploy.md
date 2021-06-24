## Настраиваем стадию развёртывания

### Раннер для развёртывания

Можно сделать два nginx контейнера, у которых папки с html будут подключены к третьему контейнеру — раннеру развёртывания. Это будет просто ещё один gitlab-runner, на которыйне надо устанавливать компилятор.

Запустить:

docker-compose up -d runner-deploy

docker-compose up -d staging

docker-compose up -d production

Коммитим изменённый .gitlab-ci.yml ещё раз, делаем git push origin master.
