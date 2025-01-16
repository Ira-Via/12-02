# 12-02
12-02 «Работа с данными (DDL/DML)» Васяева Ирина
# Задание 1
### 1.1 Поднимаем чистый инстанс MySQL
```
docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=root -d mysql:8.0
```
### 1.2 Создаём учётную запись sys_temp
```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '12345';
```
### 1.3 Выполняем запрос на получение списка пользователей
```
SELECT User, Host FROM mysql.user;
```
### 1.4 Даем все права для пользователя sys_temp
```
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
```
### 1.5 Выполняем запрос на получение списка прав для пользователя sys_temp
```
SHOW GRANTS FOR 'sys_temp'@'localhost';
```
### 1.6 Переподключитемся к базе данных от имени sys_temp
```
mysql -u sys_temp -p
```
### 1.7 Сменим тип аутентификации
```
ALTER USER 'sys_temp'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password';
```
### 1.8 Скачиваем и восстановим дамп базы данных  
1. Скачиваем базу данных Sakila.  
2. Обычно распаковать дамп можно так:  
```
unzip sakila-db.zip
```
3. Восстановите дамп с помощью команды:
```
mysql -u root -p < sakila-db.sql
```
### 1.9 Получаем все таблицы базы данных
```
SHOW TABLES;
```
### 1.10  ER-диаграмма 
# Задание 2
Вот пример таблицы, которую можно создать в текстовом редакторе или Excel. Я представила данные в виде таблицы с названиями таблиц и первичными ключами:
![image](https://github.com/user-attachments/assets/9f03f5e7-1422-4396-b17d-92126d23c464)
