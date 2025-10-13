# Домашнее задание к занятию 4 «Оркестрация группой Docker контейнеров на примере Docker Compose»

## Задача 1

## Сценарий выполнения задачи:

Установите docker и docker compose plugin на свою linux рабочую станцию или ВМ.
Если dockerhub недоступен создайте файл /etc/docker/daemon.json с содержимым: {"registry-mirrors": ["https://mirror.gcr.io", "https://daocloud.io", "https://c.163.com/", "https://registry.docker-cn.com"]}
Зарегистрируйтесь и создайте публичный репозиторий с именем "custom-nginx" на https://hub.docker.com (ТОЛЬКО ЕСЛИ У ВАС ЕСТЬ ДОСТУП);
скачайте образ nginx:1.21.1;
Создайте Dockerfile и реализуйте в нем замену дефолтной индекс-страницы(/usr/share/nginx/html/index.html), на файл index.html с содержимым:
```html
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I will be DevOps Engineer!</h1>
</body>
</html>
Соберите и отправьте созданный образ в свой dockerhub-репозитории c tag 1.0.0 (ТОЛЬКО ЕСЛИ ЕСТЬ ДОСТУП).
Предоставьте ответ в виде ссылки на https://hub.docker.com/<username_repo>/custom-nginx/general .
```
## Ответ:  https://hub.docker.com/repository/docker/dikdemon/custom-nginx/general 

## Задача 2

Запустите ваш образ custom-nginx:1.0.0 командой docker run в соответвии с требованиями:
имя контейнера "ФИО-custom-nginx-t2"
контейнер работает в фоне
контейнер опубликован на порту хост системы 127.0.0.1:8080
Не удаляя, переименуйте контейнер в "custom-nginx-t2"
Выполните команду date +"%d-%m-%Y %T.%N %Z" ; sleep 0.150 ; docker ps ; ss -tlpn | grep 127.0.0.1:8080  ; docker logs custom-nginx-t2 -n1 ; docker exec -it custom-nginx-t2 base64 /usr/share/nginx/html/index.html
Убедитесь с помощью curl или веб браузера, что индекс-страница доступна.
В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

## Ответ:

<img width="1920" height="1080" alt="Снимок экрана (1599)" src="https://github.com/user-attachments/assets/5e93bf5b-177c-4347-80df-581e8324d08c" />

<img width="1920" height="1080" alt="Снимок экрана (1598)" src="https://github.com/user-attachments/assets/d5bc51a2-6683-4f3d-ade5-57bf24aa9806" />

## Задача 3

Воспользуйтесь docker help или google, чтобы узнать как подключиться к стандартному потоку ввода/вывода/ошибок контейнера "custom-nginx-t2".
Подключитесь к контейнеру и нажмите комбинацию Ctrl-C.
Выполните docker ps -a и объясните своими словами почему контейнер остановился.
Перезапустите контейнер
Зайдите в интерактивный терминал контейнера "custom-nginx-t2" с оболочкой bash.
Установите любимый текстовый редактор(vim, nano итд) с помощью apt-get.
Отредактируйте файл "/etc/nginx/conf.d/default.conf", заменив порт "listen 80" на "listen 81".
Запомните(!) и выполните команду nginx -s reload, а затем внутри контейнера curl http://127.0.0.1:80 ; curl http://127.0.0.1:81.
Выйдите из контейнера, набрав в консоли exit или Ctrl-D.
Проверьте вывод команд: ss -tlpn | grep 127.0.0.1:8080 , docker port custom-nginx-t2, curl http://127.0.0.1:8080. Кратко объясните суть возникшей проблемы.
Это дополнительное, необязательное задание. Попробуйте самостоятельно исправить конфигурацию контейнера, используя доступные источники в интернете. Не изменяйте конфигурацию nginx и не удаляйте контейнер. Останавливать контейнер можно. пример источника
Удалите запущенный контейнер "custom-nginx-t2", не останавливая его.(воспользуйтесь --help или google)
В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

## Ответ:

<img width="1920" height="1080" alt="Снимок экрана (1602)" src="https://github.com/user-attachments/assets/a8ccc281-50a2-4a8f-9ba5-c37a61d0d8f4" />

<img width="1920" height="1080" alt="Снимок экрана (1607)" src="https://github.com/user-attachments/assets/cdf354be-8b24-405f-91f6-8d5ce6b22322" />

<img width="1920" height="1080" alt="Снимок экрана (1608)" src="https://github.com/user-attachments/assets/2ca66043-7f41-44bf-bd27-906932b30073" />

<img width="1920" height="1080" alt="Снимок экрана (1609)" src="https://github.com/user-attachments/assets/6ce34be3-093e-4627-a3ef-9fff9e1110af" />

<img width="1920" height="1080" alt="Снимок экрана (1610)" src="https://github.com/user-attachments/assets/8cb8a755-2171-47d5-acf3-bcc70ac36d23" />

<img width="1920" height="1080" alt="Снимок экрана (1611)" src="https://github.com/user-attachments/assets/4ed2debf-f197-45f1-9c0f-ec0426aa2e49" />

## Задача 4

Запустите первый контейнер из образа centos c любым тегом в фоновом режиме, подключив папку текущий рабочий каталог $(pwd) на хостовой машине в /data контейнера, используя ключ -v.

Запустите второй контейнер из образа debian в фоновом режиме, подключив текущий рабочий каталог $(pwd) в /data контейнера.

Подключитесь к первому контейнеру с помощью docker exec и создайте текстовый файл любого содержания в /data.

Добавьте ещё один файл в текущий каталог $(pwd) на хостовой машине.

Подключитесь во второй контейнер и отобразите листинг и содержание файлов в /data контейнера.

В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод.

## Ответ:

<img width="1920" height="1080" alt="Снимок экрана (1612)" src="https://github.com/user-attachments/assets/117abc58-a216-432e-ad55-e5abdf9a3612" />

<img width="1920" height="1080" alt="Снимок экрана (1613)" src="https://github.com/user-attachments/assets/e92c455d-af1c-4e54-8919-efa998ba3a45" />

<img width="1920" height="1080" alt="Снимок экрана (1614)" src="https://github.com/user-attachments/assets/2138f6b3-9542-4c6b-9489-b466dbcc1f82" />

<img width="1920" height="1080" alt="Снимок экрана (1615)" src="https://github.com/user-attachments/assets/4798dfc0-6e95-4feb-8de2-2533f6bdd648" />

<img width="1920" height="1080" alt="Снимок экрана (1616)" src="https://github.com/user-attachments/assets/8b363c83-7933-4a4f-871f-175642c81a24" />

## Задача 5

Создайте отдельную директорию(например /tmp/netology/docker/task5) и 2 файла внутри него. "compose.yaml" с содержимым:
```yaml
version: "3"
services:
  portainer:
    network_mode: host
    image: portainer/portainer-ce:latest
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
```
"docker-compose.yaml" с содержимым:
```yaml
version: "3"
services:
  registry:
    image: registry:2

    ports:
    - "5000:5000"
```
И выполните команду "docker compose up -d". Какой из файлов был запущен и почему? (подсказка: https://docs.docker.com/compose/compose-application-model/#the-compose-file )

Отредактируйте файл compose.yaml так, чтобы были запущенны оба файла. (подсказка: https://docs.docker.com/compose/compose-file/14-include/)

Выполните в консоли вашей хостовой ОС необходимые команды чтобы залить образ custom-nginx как custom-nginx:latest в запущенное вами, локальное registry. Дополнительная документация: https://distribution.github.io/distribution/about/deploying/

Откройте страницу "https://127.0.0.1:9000" и произведите начальную настройку portainer.(логин и пароль адмнистратора)

Откройте страницу "http://127.0.0.1:9000/#!/home", выберите ваше local окружение. Перейдите на вкладку "stacks" и в "web editor" задеплойте следующий компоуз:
```yaml
version: '3'

services:
  nginx:
    image: 127.0.0.1:5000/custom-nginx
    ports:
      - "9090:80"
```
Перейдите на страницу "http://127.0.0.1:9000/#!/2/docker/containers", выберите контейнер с nginx и нажмите на кнопку "inspect". В представлении <> Tree разверните поле "Config" и сделайте скриншот от поля "AppArmorProfile" до "Driver".

Удалите любой из манифестов компоуза(например compose.yaml). Выполните команду "docker compose up -d". Прочитайте warning, объясните суть предупреждения и выполните предложенное действие. Погасите compose-проект ОДНОЙ(обязательно!!) командой.

В качестве ответа приложите скриншоты консоли, где видно все введенные команды и их вывод, файл compose.yaml , скриншот portainer c задеплоенным компоузом.

## Ответ:



<img width="1920" height="1080" alt="Снимок экрана (1618)" src="https://github.com/user-attachments/assets/1a447b0f-ae05-4fdb-9344-cc9cf767efe7" />

<img width="1920" height="1080" alt="Снимок экрана (1619)" src="https://github.com/user-attachments/assets/c6229c85-4d76-4e63-87be-bb6265c324c3" />

### `compose.yaml` после редактирования:
```yaml
version: "3"
include:
  - docker-compose.yaml
services:
  portainer:
    network_mode: host
    image: portainer/portainer-ce:latest
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
```

<img width="1920" height="1080" alt="Снимок экрана (1622)" src="https://github.com/user-attachments/assets/56a33faf-6311-4713-8f6b-783f397afc78" />

<img width="1920" height="1080" alt="Снимок экрана (1623)" src="https://github.com/user-attachments/assets/9326c6b8-6c7e-4742-b515-a5a731aeb724" />

<img width="1920" height="1080" alt="Снимок экрана (1624)" src="https://github.com/user-attachments/assets/bd57a064-374c-49b0-a86d-53724fc7812b" />

<img width="1920" height="1080" alt="Снимок экрана (1625)" src="https://github.com/user-attachments/assets/e8dd746d-a35c-47af-8f80-063d6c13a886" />

<img width="1920" height="1080" alt="Снимок экрана (1626)" src="https://github.com/user-attachments/assets/b48fe937-438f-4342-b2ef-be7bbd6b9809" />

<img width="1920" height="1080" alt="Снимок экрана (1627)" src="https://github.com/user-attachments/assets/10d7a57b-9a4f-44b9-bffd-1cb272285460" />

<img width="1920" height="1080" alt="Снимок экрана (1628)" src="https://github.com/user-attachments/assets/d1cb7a58-26d2-486e-ab85-4844532ff6af" />

<img width="1920" height="1080" alt="Снимок экрана (1629)" src="https://github.com/user-attachments/assets/b157ab77-ce98-4ae4-8ea9-ed1011523d83" />

<img width="1920" height="1080" alt="Снимок экрана (1630)" src="https://github.com/user-attachments/assets/7de106b4-d866-42fc-a355-3bbec22ec737" />

<img width="1920" height="1080" alt="Снимок экрана (1631)" src="https://github.com/user-attachments/assets/7028f934-7ddb-4c06-8060-a6c92f5a9082" />

<img width="1920" height="1080" alt="Снимок экрана (1632)" src="https://github.com/user-attachments/assets/4684cc7b-adae-4849-be53-987974fc05dc" />

<img width="1920" height="1080" alt="Снимок экрана (1633)" src="https://github.com/user-attachments/assets/19eda5e4-2aa4-456f-9e79-cb7ada69413c" />


