## Настраиваем gitlab-runner сервис

Нужно скачать gitlab-runner и зарегистрировать его в нашем GitLab:

sudo -E apt-get install gitlab-runner

Установим runner в Docker контейнере и зарегистрируем как докеровский сервис в docker-compose.yml. Таким образом он очутится в одной сети с GitLab.

В секции RUN лежит установка раннера и TypeScript, а уже регистрация и запуск пошли в CMD секцию. Немного уродливо, но работать будет. По крайней мере один раз.

Запустить:

docker-compose up -d runner-ts
