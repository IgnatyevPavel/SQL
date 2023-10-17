# SQL HomeWork 2. Joins

> Подключится к 
> Host: 159.69.151.133
> Port: 5056
> DB: подключение к той таблице где делали DDL операции
> User: подключение к тем пользователем каким делали DDL операции
> Pass: 123
> Если для какого-то кейса надо сделать дополнительную таблицу, наполнить её данными, то делайте )

### 1. Вывести всех работников чьи зарплаты есть в базе, вместе с зарплатами.
```
select employees.employee_name , salary.mounthly_salary from 
employees inner join salary 
on employees.id = salary.id ;
```
___
###  2. Вывести всех работников у которых ЗП меньше 2000.
```
select employees.employee_name , salary.mounthly_salary from 
employees inner join salary 
on employees.id = salary.id 
where mounthly_salary < 2000;
```
___
### 3. Вывести все зарплатные позиции, но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```
select employees.employee_name , salary.mounthly_salary from 
employees FULL OUTER join salary 
on employees.id = salary.id 
where mounthly_salary is null;
```
___
### 4. Вывести все зарплатные позиции  меньше 2000 но работник по ним не назначен. (ЗП есть, но не понятно кто её получает.)
```
select employee_salary.employee_id , employees.employee_name , salary.mounthly_salary from employee_salary right join salary
on employee_salary.salary_id = salary.id 
FULL OUTER join employees
on employees.id = employee_salary.employee_id 
where employees.employee_name is null;
```
___
### 5. Найти всех работников кому не начислена ЗП.
```
select employee_salary.employee_id , employees.employee_name , salary.mounthly_salary from employee_salary right join salary
on employee_salary.salary_id = salary.id 
FULL OUTER join employees
on employees.id = employee_salary.employee_id
where mounthly_salary is null;
```
___
### 6. Вывести всех работников с названиями их должности.
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id;
```
___
### 7. Вывести имена и должность только Java разработчиков.
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
where roles.role_name like '%Java dev%';
```
___
### 8. Вывести имена и должность только Python разработчиков.
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
where roles.role_name like '%Python dev%';
```
___
###  9. Вывести имена и должность всех QA инженеров.
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
where roles.role_name like '%QA engineer%'; 
```
___
### 10. Вывести имена и должность ручных QA инженеров.
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
where roles.role_name like '%Manual QA engineer%';
```
___

### 11. Вывести имена и должность автоматизаторов QA
```
select employees.employee_name, roles.role_name from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
where roles.role_name like '%Automation QA engineer%'; 
```
___
### 12. Вывести имена и зарплаты Junior специалистов
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Junior%';
```
___
### 13. Вывести имена и зарплаты Middle специалистов
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Middle%';
```
___
### 14. Вывести имена и зарплаты Senior специалистов
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Senior%';
```
___
### 15. Вывести зарплаты Java разработчиков
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Java dev%';
```
___
### 16. Вывести зарплаты Python разработчиков
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Python dev%';
```
___
### 17. Вывести имена и зарплаты Junior Python разработчиков
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Junior Python dev%';
```
___
### 18. Вывести имена и зарплаты Middle JS разработчиков
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Middle JavaS%';
```
___
### 19. Вывести имена и зарплаты Senior Java разработчиков
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id;
```
___
### 20. Вывести зарплаты Junior QA инженеров
```
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%Junior%QA%';
```
___
### 21. Вывести среднюю зарплату всех Junior специалистов
```
select AVG(salary.mounthly_salary) as Middle_salary  from roles_employee inner join roles
on roles_employee.role_id = roles.id 
join employee_salary
on roles_employee.employee_id  = employee_salary.employee_id 
join salary 
on employee_salary.salary_id = salary.id 
where roles.role_name like '%Junior%';
```
___
### 22. Вывести сумму зарплат JS разработчиков
select AVG(salary.mounthly_salary) as Middle_salary  from roles_employee inner join roles
on roles_employee.role_id = roles.id 
join employee_salary
on roles_employee.employee_id  = employee_salary.employee_id 
join salary 
on employee_salary.salary_id = salary.id 
where roles.role_name like '%JavaS% dev%';

### 23. Вывести минимальную ЗП QA инженеров
--все QA инженеры и зарплаты
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%QA%';
--решение задачи
select MIN(salary.mounthly_salary) as Min_salary  from roles_employee inner join roles
on roles_employee.role_id = roles.id 
join employee_salary
on roles_employee.employee_id  = employee_salary.employee_id 
join salary 
on employee_salary.salary_id = salary.id 
where roles.role_name like '%QA%';
```
___
### 24. Вывести максимальную ЗП QA инженеров
--все QA инженеры и зарплаты
select employees.employee_name, roles.role_name, employee_salary.salary_id , salary.mounthly_salary from employees inner join roles_employee
on employees.id = roles_employee.employee_id 
full OUTER join roles 
on roles.id = roles_employee.role_id
join employee_salary
on employee_salary.employee_id = employees.id
join salary 
on employee_salary.salary_id = salary.id
where roles.role_name like '%QA%';
```
--решение задачи
select MAX(salary.mounthly_salary) as Max_salary  from roles_employee inner join roles
on roles_employee.role_id = roles.id 
join employee_salary
on roles_employee.employee_id  = employee_salary.employee_id 
join salary 
on employee_salary.salary_id = salary.id 
where roles.role_name like '%QA%';
```
___
### 25. Вывести количество QA инженеров
```
--таблицы из HW1 employees\salary\roles\employee_salary\roles_employee()
select count(roles.role_name) as Quantity_QA_engineer from roles inner join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%QA%';
--полный список qa инженеров
select roles.role_name, roles_employee.id from roles full OUTER join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%QA%';
```
___
### 26. Вывести количество Middle специалистов.
```
select roles.role_name, roles_employee.id from roles full OUTER join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%Middle%';
--полный список Middle специалистов
select count(roles.role_name) as Quantity_QA_engineer from roles inner join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%Middle%';
```
___
### 27. Вывести количество разработчиков
select count(roles.role_name) as Quantity_QA_engineer from roles inner join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%dev%';
--полный список Middle специалистов
select roles.role_name, roles_employee.id from roles full OUTER join roles_employee
on roles.id = roles_employee.role_id
where roles.role_name like '%dev%';

### 28. Вывести фонд (сумму) зарплаты разработчиков.
--зарплаты всех сотрудников
select employee_salary.employee_id, roles_employee.employee_id, salary.mounthly_salary, roles.role_name from employee_salary full outer join roles_employee
on employee_salary.employee_id = roles_employee.employee_id
join salary 
on salary.id = employee_salary.salary_id 
join roles 
on roles_employee.role_id = roles.id;
--решение (фонд на месяц)
select SUM(salary.mounthly_salary) from employee_salary full outer join roles_employee
on employee_salary.employee_id = roles_employee.employee_id
join salary 
on salary.id = employee_salary.salary_id 
join roles 
on roles_employee.role_id = roles.id
where role_name like '%dev%';

### 29. Вывести имена, должности и ЗП всех специалистов по возрастанию
--таблицы из HW1 employees\salary\roles\employee_salary\roles_employee
select employees.employee_name, roles.role_name, salary.mounthly_salary from employee_salary right join employees
on employees.id = employee_salary.employee_id
join roles_employee
on roles_employee.employee_id = employees.id
join roles 
on roles.id = roles_employee.role_id 
join salary 
on salary.id = employee_salary.salary_id 
order by salary.mounthly_salary ;

### 30. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП от 1700 до 2300
```
select employees.employee_name, roles.role_name, salary.mounthly_salary from employee_salary right join employees
on employees.id = employee_salary.employee_id
join roles_employee
on roles_employee.employee_id = employees.id
join roles 
on roles.id = roles_employee.role_id 
join salary 
on salary.id = employee_salary.salary_id 
where salary.mounthly_salary between 1700 and 2300
order by salary.mounthly_salary;
```
### 31. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП меньше 2300
```
select employees.employee_name, roles.role_name, salary.mounthly_salary from employee_salary right join employees
on employees.id = employee_salary.employee_id
join roles_employee
on roles_employee.employee_id = employees.id
join roles 
on roles.id = roles_employee.role_id 
join salary 
on salary.id = employee_salary.salary_id 
where salary.mounthly_salary < 2300
order by salary.mounthly_salary;
```

### 32. Вывести имена, должности и ЗП всех специалистов по возрастанию у специалистов у которых ЗП равна 1100, 1500, 2000
```
select employees.employee_name, roles.role_name, salary.mounthly_salary from employee_salary right join employees
on employees.id = employee_salary.employee_id
join roles_employee
on roles_employee.employee_id = employees.id
join roles 
on roles.id = roles_employee.role_id 
join salary 
on salary.id = employee_salary.salary_id 
where salary.mounthly_salary in (1100, 1500, 2000)
order by salary.mounthly_salary;
```
