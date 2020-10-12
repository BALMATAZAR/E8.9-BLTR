# Задание E8.9

   Сервис подсчёта с очередями (flask framework с celery и redis)

   ТехЗадание:
Необходимо реализовать сервис, который считает, сколько раз встречается слово "python" на странице.
Этот сервис должен состоять из следующих частей:
1) Веб-форма для внесения сайтов в спискок задач;
2) Очередь, которая эти задания запускает;
3) Часть, которая обрабатывает результаты;
4) Табличка со статистикой с результатами.

Итак, задание считается выполненным, если:
   - прислана ссылка на github с репозиторием.
   - в репозитории есть README.md, в котором сказано, как работать с приложением.
   - в приложении реализована вебформа, куда можно добавлять адреса веб-сайтов.
   - после добавления адреса создается задача для подсчета количества слов Python по этому адресу в Celery в форме модели.
   - после завершения запроса результат (независимо успешный или нет) обрабатывается и сохраняется в форме модели Results. Запрос, который длится дольше 10 секунд считается неуспешным.
   - по запросу к эндпоинту отрисовывается табличка с результатами: на каком сайте сколько раз встретилось слово Python. Либо, если запрос был неуспешен, с кодом ошибки.
   - приложение должно быть упаковано в Docker, можно воспользоваться Docker-compose.
   - Бонусный балл: реализовать обновление результатов с помощью nsq, то есть, когда приходит результат, клиент публикует об этом сообщение, и слушающий клиент, подписанный на соответствующий топик, об этом узнает и обновляет информацию в табличке результатов.

Для того, чтобы запустить сервис необходимо:
1) Распакуйте архив с проектом в папку и через командную строку зайдите в директорию проекта.
2) Создайте виртуальную машину, если она еще не создана:
   - docker-machine create default
3) Запустите виртуальную машину:
   - docker-machine start default
4) Определите рабочий IP-адрес виртуальной машины:
   - docker-machine ip default
5) Запустите сборку docker-проекта:
   - docker-compose up --build
Сервис откроется по IP-адресу виртуальной машины с 5000 портом.
