- Сборка контейнера

`$ docker build -t task-one-image .`

- Запуск контейнера

`$ docker run --rm --name task-one-cont task-one-image  # Запуск контейнера с захватом консоли`

`$ docker run --rm -d --name task-one-cont task-one-image  # Запуск контейнера в daemon режиме`

- Запуск с возможностью доступа по tcp-порту на хост-машине

`$ docker run -p 5000:5000 --rm --name task-one-cont task-one-image`

- Присоединение папки с приложением

`$ docker run --rm -d -p 5000:5000 -v ~/projects/docker_less/task-two/:/app --name task-two-cont task-two-image`

