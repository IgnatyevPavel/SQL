# SQL_HW_1
> .sql файл выгружайте на гит и скидывайте ссылки на проверку.
> Создать .sql файл в котором под каждой командой напишите sql запрос который выполнит команду.

### 1. Вывести все поля и все строки.
```
SELECT * FROM students;
```
___
### 2. Вывести всех студентов в таблице
```
SELECT * FROM students;
```
### 3. Вывести только Id пользователей
```
select id from students;
```
### 4. Вывести только имя пользователей
```
select name from students;
```
### 5. Вывести только email пользователей
```
select email from students;
```
### 6. Вывести имя и email пользователей
```
select name, email from students;
```
### 7. Вывести id, имя, email и дату создания пользователей
```
select id, name, email, created_on from students;
```
### 8. Вывести пользователей где password 12333
```
SELECT * FROM students
where password = '12333';
```
### 9. Вывести пользователей которые были созданы 2021-03-26 00:00:00
```
SELECT * FROM students
where created_on  = '2021-03-26 00:00:00';
```
### 10. Вывести пользователей где в имени есть слово Анна
```
SELECT * FROM students
where name like '%Anna%';
```
### 11. Вывести пользователей где в имени в конце есть 8
```
SELECT * FROM students
where name like '%8%';
```
### 12. Вывести пользователей где в имени в есть буква а
```
SELECT * FROM students
where name like '%A%';
```
### 13. Вывести пользователей которые были созданы 2021-07-12 00:00:00
```
SELECT * FROM students
where created_on  = '2021-07-12 00:00:00';
```
### 14. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и имеют пароль 1m313
```
SELECT * FROM students
where created_on  = '2021-07-12 00:00:00' AND password = '1m313';
```
### 15. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть слово Andrey
```
SELECT * FROM students
where created_on  = '2021-07-12 00:00:00' AND name like '%Andrey%';
```
### 16. Вывести пользователей которые были созданы 2021-07-12 00:00:00 и у которых в имени есть цифра 8
```
SELECT * FROM students
where created_on  = '2021-07-12 00:00:00' AND name like '%8%';
```
### 17. Вывести пользователя у которых id равен 110
```
SELECT * FROM students
where id = 110;
```
### 18. Вывести пользователя у которых id равен 153
```
SELECT * FROM students
where id = 153;
```
### 19. Вывести пользователя у которых id больше 140
```
SELECT * FROM students
where id > 140;
```
### 20. Вывести пользователя у которых id меньше 130
```
SELECT * FROM students
where id < 130;
```
### 21. Вывести пользователя у которых id меньше 127 или больше 188
```
SELECT * FROM students
where id < 127 OR id > 188;
```
### 22. Вывести пользователя у которых id меньше либо равно 137
```
SELECT * FROM students
where id <=137
order by id;
```
### 23. Вывести пользователя у которых id больше либо равно 137
```
SELECT * FROM students
where id >=137
order by id;
```
### 24. Вывести пользователя у которых id больше 180 но меньше 190
```
SELECT * FROM students
where id > 180 AND id < 190
order by id;
```
### 25. Вывести пользователя у которых id между 180 и 190
```
SELECT * FROM students
where id BETWEEN 180 AND 190
order by id;
```
### 26. Вывести пользователей где password равен 12333, 1m313, 123313
```
SELECT * FROM students
where password IN ('12333', '1m313', '123313')
order by id;
```
### 27. Вывести пользователей где created_on равен 2020-10-03 00:00:00, 2021-05-19 00:00:00, 2021-03-26 00:00:00
```
SELECT * FROM students
where created_on IN ('2020-10-03 00:00:00', '2021-05-19 00:00:00', '2021-03-26 00:00:00')
order by created_on;
```
### 28. Вывести минимальный id 
```
SELECT MIN(id) FROM students;
```
### 29. Вывести максимальный.
```
SELECT MAX(id) FROM students;
```
### 30. Вывести количество пользователей
```
SELECT COUNT(*) FROM students;
```
### 31. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку возрастания даты добавления пользоватлеля.
```
SELECT id, name, created_on FROM students
ORDER BY created_on;
```
### 32. Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку убывания даты добавления пользоватлеля.
```
SELECT id, name, created_on FROM students
ORDER BY created_on DESC;
```
