# SQL_DDL. Первая часть.

### Таблица employees

+ Создать таблицу employees
```
- id. serial,  primary key,
- employee_name. Varchar(50), not null
```
+ Наполнить таблицу employee 70 строками.

```
CREATE TABLE employees(
    id SERIAL PRIMARY KEY,
    employee_name VARCHAR(50) NOT NULL
);

select * from employees ;

INSERT INTO employees(employee_name)
VALUES  
        ('Ana Trujillo'),
        ('Antonio Moreno'),
        ('Thomas Hardy'),
        ('Christina Berglund'),
        ('Hanna Moos'),
        ('Frédérique Citeaux'),
        ('Martín Sommer'),
        ('Laurence Lebihans'),
        ('Elizabeth Lincoln'),
        ('Victoria Ashworth'),
        ('Patricio Simpson'),
        ('Francisco Chang'),
        ('Yang Wang'),
        ('Pedro Afonso'),
        ('Elizabeth Brown'),
        ('Sven Ottlieb'),
        ('Janine Labrune'),
        ('Ann Devon'),
        ('Roland Mendel'),
        ('Aria Cruz'),
        ('Diego Roel'),
        ('Martine Rancé'),
        ('Maria Larsson'),
        ('Peter Franken'),
        ('Carine Schmitt'),
        ('Paolo Accorti'),
        ('Lino Rodriguez'),
        ('Eduardo Saavedra'),
        ('José Pedro Freyre'),
        ('André Fonseca'),
        ('Howard Snyder'),
        ('Manuel Pereira'),
        ('Mario Pontes'),
        ('Carlos Hernández'),
        ('Yoshi Latimer'),
        ('Patricia McKenna'),
        ('Helen Bennett'),
        ('Philip Cramer'),
        ('Daniel Tonini'),
        ('Annette Roulet'),
        ('Yoshi Tannamuri'),
        ('John Steel'),
        ('Renate Messner'),
        ('Jaime Yorres'),
        ('Carlos González'),
        ('Felipe Izquierdo'),
        ('Fran Wilson'),
        ('Giovanni Rovelli'),
        ('Catherine Dewey'),
        ('Jean Fresnière'),
        ('Alexander Feuer'),
        ('Simon Crowther'),
        ('Yvonne Moncada'),
        ('Rene Phillips'),
        ('Henriette Pfalzheim'),
        ('Marie Bertrand'),
        ('Guillermo Fernández'),
        ('Georg Pipps'),
        ('Isabel de Castro'),
        ('Bernardo Batista'),
        ('Lúcia Carvalho'),
        ('Horst Kloss'),
        ('Sergio Gutiérrez'),
        ('Paula Wilson'),
        ('Maurizio Moroni'),
        ('Janete Limeira'),
        ('Michael Holz'),
        ('Alejandra Camino'),
        ('Jonas Bergulfsen'),
        ('Hari Kumar');
```

### Таблица salary
+ Создать таблицу salary
```
- id. Serial  primary key,
- monthly_salary. Int, not null
```
+ Наполнить таблицу salary 15 строками:
```
- 1000
- 1100
- 1200
- 1300
- 1400
- 1500
- 1600
- 1700
- 1800
- 1900
- 2000
- 2100
- 2200
- 2300
- 2400
- 2500
```
+ Решение:
```
CREATE TABLE salary(
    id SERIAL PRIMARY KEY,
    mounthly_salary INT NOT NULL
);

select * from salary;

INSERT INTO salary(mounthly_salary)
VALUES  (1000),
        (1100),
        (1200),
        (1300),
        (1400),
        (1500),
        (1600),
        (1700),
        (1800),
        (1900),
        (2000),
        (2100),
        (2200),
        (2300),
        (2400),
        (2500);
```
__
### Таблица employee_salary

+ Создать таблицу employee_salary
```
- id. Serial  primary key,
- employee_id. Int, not null, unique
- salary_id. Int, not null
```
+ Наполнить таблицу employee_salary 40 строками:
+ в 10 строк из 40 вставить несуществующие employee_id

```
CREATE TABLE employee_salary(
    id SERIAL PRIMARY KEY,
    employee_id INT UNIQUE NOT NULL,
    salary_id INT NOT NULL
);       

CREATE TABLE employee_salary(
    id SERIAL PRIMARY KEY,
    employee_id INT UNIQUE NOT NULL,
    salary_id INT NOT NULL
);

select * from employee_salary;

INSERT INTO employee_salary(employee_id, salary_id)
VALUES (1,1),
       (2,2),
       (3,3),
       (4,4),
       (5,5),
       (6,6),
       (7,7),
       (8,8),
       (9,9),
       (10,10),
       (11,11),
       (12,12),
       (13,13),
       (14,14),
       (15,15),
       (16,1),
       (17,2),
       (18,3),
       (19,4),
       (20,5),
       (21,6),
       (22,7),
       (23,8),
       (24,9),
       (25,10),
       (26,11),
       (27,12),
       (28,13),
       (29,14),
       (30,15),
       (131,1),
       (132,2),
       (133,3),
       (134,4),
       (135,5),
       (136,6),
       (137,7),
       (138,8),
       (139,9),
       (140,10);
```
__
### Таблица roles

+ Создать таблицу roles
```
- id. Serial  primary key,
- role_name. int, not null, unique
```
+ Поменять тип столба role_name с int на varchar(30)
+ Наполнить таблицу roles 20 строками:
```
+ Решение: 
CREATE TABLE roles(
    id SERIAL PRIMARY KEY,
    role_name INT UNIQUE NOT NULL
);

select * from roles;

ALTER TABLE roles 
ALTER COLUMN role_name TYPE VARCHAR(30);

INSERT INTO roles(role_name)
VALUES  ('Junior Python developer'),
        ('Middle Python developer'),
        ('Senior Python developer'),
        ('Junior Java developer'),
        ('Middle Java developer'),
        ('Senior Java developer'),
        ('Junior JavaScript developer'),
        ('Middle JavaScript developer'),
        ('Senior JavaScript developer'),
        ('Junior Manual QA engineer'),
        ('Middle Manual QA engineer'),
        ('Senior Manual QA engineer'),
        ('Project Manager'),
        ('Designer'),
        ('HR'),
        ('CEO'),
        ('Sales manager'),
        ('Junior Automation QA engineer'),
        ('Middle Automation QA engineer'),
        ('Senior Automation QA engineer');
```
__
### Таблица roles_employee

+ Создать таблицу roles_employee
```
- id. Serial  primary key,
- employee_id. Int, not null, unique (внешний ключ для таблицы employees, поле id)
- role_id. Int, not null (внешний ключ для таблицы roles, поле id)
```
+ Наполнить таблицу roles_employee 40 строками:

+ Решение 
```
CREATE TABLE roles_employee(
    id SERIAL PRIMARY KEY,
    employee_id INT UNIQUE NOT null,
    role_id INT NOT null,
    FOREIGN KEY (employee_id)
        REFERENCES employees(id),
    FOREIGN KEY (role_id)
        REFERENCES roles(id)
);

select * from roles_employee;

INSERT INTO roles_employee(employee_id, role_id)
VALUES (1,1),
       (2,2),
       (3,3),
       (4,4),
       (5,5),
       (6,6),
       (7,7),
       (8,8),
       (9,9),
       (10,10),
       (11,11),
       (12,12),
       (13,13),
       (14,14),
       (15,15),
       (16,16),
       (17,17),
       (18,18),
       (19,19),
       (20,20),
       (21,1),
       (22,2),
       (23,3),
       (24,4),
       (25,5),
       (26,6),
       (27,7),
       (28,8),
       (29,9),
       (30,10),
       (31,11),
       (32,12),
       (33,13),
       (34,14),
       (35,15),
       (36,16),
       (37,17),
       (38,18),
       (39,19),
       (40,20);
```





