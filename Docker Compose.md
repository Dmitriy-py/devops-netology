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



























