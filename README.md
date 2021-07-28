## Документация
1. [План автоматизации тестирования](https://github.com/troffimovka/Trip---Diplom/blob/master/documentation/Plan.md)
2. [Отчет по итогам тестирования](https://github.com/troffimovka/Trip---Diplom/blob/master/documentation/Report.md)
3. [Отчет по итогам автоматизации тестирования](https://github.com/troffimovka/Trip---Diplom/blob/master/documentation/Summary.md)

## Процедура запуска тестов сервиса покупки путешествий для MySql
1. Клонируем репозиторий на свой компьютер.
2. Открываем его с помощью JetBrains IntelliJ IDEA Ultimate.
З. Запускаем контейнеры MySql и Node c помощью команды docker-compose up -d --force-recreate.
4. Проверяем, что контейнеры запустились командой docker-compose ps.
5. Запускаем приложение и передаем данные для подключения базы MySql командой java -Dspring.datasource.url=jdbc:mysql://localhost:3306/app -Dspring.datasource.username=user -Dspring.datasource.password=pass -jar artifacts/aqa-shop.jar
6. Запускаем тесты командой gradlew clean test -Durl="jdbc:mysql://localhost:3306/app" -Duser="user" -Dpassword="pass" --info.
7. Формируем отчет командой gradlew allureServe.
8. Оцениваем результаты тестирования.

## Процедура запуска тестов сервиса покупки путешествий для PostgreSQL
1. Клонируем репозиторий на свой компьютер.
2. Открываем его с помощью JetBrains IntelliJ IDEA Ultimate.
3. Запускаем контейнеры PostgreSQL и Node c помощью команды docker-compose up -d --force-recreate.
4. Проверяем, что контейнеры запустились командой docker-compose ps.
5. Запускаем приложение и передаем данные для подключения базы PostgreSQL командой java -Dspring.datasource.url=jdbc:postgresql://localhost:5432/appps -Dspring.datasource.username=userps -Dspring.datasource.password=passps -jar artifacts/aqa-shop.jar
6. Запускаем тесты командой gradlew clean test -Durl="jdbc:postgresql://localhost:5432/appps" -Duser="userps" -Dpassword="passps" --info.
6. Формируем отчет командой gradlew allureServe.
8. Оцениваем результаты тестирования.