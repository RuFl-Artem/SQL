# Практическая работа SQL
Создать базу по указанной ниже картинке

![image](https://user-images.githubusercontent.com/100138324/155129257-fabc141f-4f69-409a-8e99-603a70ada647.png)

У каждой таблицы должно быть поле id. id автоинкрементальный и является первичным ключом
```
create table employees_roles (
	id serial primary key,
	id_role int not null,
	id_employee int not null,
	foreign key (id_role)
		references roles (id),
	foreign key (id_employee)
		references employees (id)
);
```
```
create table roles (
	id serial primary key,
	role_title varchar (50) not null
);
```
```
create table roles_salary (
	id serial primary key,
	id_role int not null,
	id_salary int not null,
	foreign key (id_role)
		references roles (id),
	foreign key (id_salary)
		references salary (id)
);
```
```
create table salary (
	id serial primary key,
	monthly_salary int not null
);
```
```
create table employees (
	id serial primary key,
	employee_name varchar (50) not null
);
```
```
create table claim (
	id serial primary key,
	service_id int not null,
	employee_id int not null,
	material_id int not null,
	claim_date date not null,
	sales_manager int not null,
	foreign key (employee_id)
		references employees (id),
	foreign key (sales_manager)
		references employees (id),
	foreign key (service_id)
		references Service (id),
	foreign key (material_id)
		references materials (id)
);
```
```
create table Service (
	id serial primary key,
	service_title varchar (50) not null,
	price int not null
);
```
```
create table materials (
	id serial primary key,
	material_title varchar (50) not null,
	amount int not null
);
```
Заполните таблицы данными. Не менее 12 строк в каждой таблице;
```
insert into employees_roles (id, id_role, id_employee) values (default, 1, 12);
insert into employees_roles (id, id_role, id_employee) values (default, 2, 11);
insert into employees_roles (id, id_role, id_employee) values (default, 3, 10);
insert into employees_roles (id, id_role, id_employee) values (default, 4, 9);
insert into employees_roles values (default, 5, 8);
insert into employees_roles values (default, 6, 7);
insert into employees_roles values (default, 7, 6);
insert into employees_roles values (default, 8, 5);
insert into employees_roles values (default, 9, 4);
insert into employees_roles values (default, 10, 3);
insert into employees_roles values (default, 11, 2);
insert into employees_roles values (default, 12, 1);
```
```
insert into roles (id, role_title) values (default, 'Manager');
insert into roles (id, role_title) values (default, 'Manager');
insert into roles (id, role_title) values (default, 'Manager');
insert into roles (id, role_title) values (default, 'Manager');
insert into roles values (default, 'Engineer');
insert into roles values (default, 'Engineer');
insert into roles values (default, 'Engineer');
insert into roles values (default, 'Engineer');
insert into roles values (default, 'HR');
insert into roles values (default, 'HR');
insert into roles values (default, 'HR');
insert into roles values (default, 'HR');
```
```
insert into roles_salary (id, id_role, id_salary) values (default, 1, 20);
insert into roles_salary (id, id_role, id_salary) values (default, 2, 21);
insert into roles_salary (id, id_role, id_salary) values (default, 3, 22);
insert into roles_salary (id, id_role, id_salary) values (default, 4, 26);
insert into roles_salary values (default, 5, 30);
insert into roles_salary values (default, 6, 31);
insert into roles_salary values (default, 7, 32);
insert into roles_salary values (default, 8, 33);
insert into roles_salary values (default, 9, 37);
insert into roles_salary values (default, 10, 10);
insert into roles_salary values (default, 11, 5);
insert into roles_salary values (default, 12, 2);
```
```
insert into salary (id, monthly_salary) values (default, 120);
insert into salary (id, monthly_salary) values (default, 100);
insert into salary (id, monthly_salary) values (default, 500);
insert into salary (id, monthly_salary) values (default, 300);
insert into salary values (default, 320);
insert into salary values (default, 350);
insert into salary values (default, 800);
insert into salary values (default, 1000);
insert into salary values (default, 1500);
insert into salary values (default, 3000);
insert into salary values (default, 4000);
insert into salary values (default, 2500);
```
```
insert into employees (id, employee_name) values (default, 'Artem');
insert into employees (id, employee_name) values (default, 'Ivan');
insert into employees (id, employee_name) values (default, 'Boris');
insert into employees (id, employee_name) values (default, 'Anton');
insert into employees values (default, 'Roman');
insert into employees values (default, 'Victor');
insert into employees values (default, 'Victor');
insert into employees values (default, 'Olga');
insert into employees values (default, 'Ann');
insert into employees values (default, 'Dima');
insert into employees values (default, 'Igor');
insert into employees values (default, 'Angelika');
```
```
insert into claim values (default, 1, 12, 1, '01.03.2022', 1);
insert into claim values (default, 2, 11, 2, '02.03.2022', 2);
insert into claim values (default, 3, 10, 3, '21.03.2022', 3);
insert into claim values (default, 4, 9, 4, '10.02.2022', 4);
insert into claim values (default, 5, 8, 5, '08.02.2022', 5);
insert into claim values (default, 6, 7, 6, '26.02.2022', 6);
insert into claim values (default, 7, 6, 7, '11.04.2022', 7);
insert into claim values (default, 8, 5, 8, '12.12.2021', 8);
insert into claim values (default, 9, 4, 9, '16.12.2021', 9);
insert into claim values (default, 10, 3, 10, '11.01.2022', 10);
insert into claim values (default, 11, 2, 11, '21.01.2022', 11);
insert into claim values (default, 12, 1, 12, '22.01.2022', 12);
```
```
insert into Service values (default, 'Desktop', 100);
insert into Service values (default, 'Desktop', 50);
insert into Service values (default, 'Desktop', 200);
insert into Service values (default, 'Desktop', 1000);
insert into Service values (default, 'Mobile', 200);
insert into Service values (default, 'Mobile', 40);
insert into Service values (default, 'Mobile', 2000);
insert into Service values (default, 'Mobile', 350);
insert into Service values (default, 'Web', 100);
insert into Service values (default, 'Web', 600);
insert into Service values (default, 'Web', 300);
insert into Service values (default, 'Web', 50);
```
```
insert into materials values (default, 'A', 50, 101);
insert into materials values (default, 'A', 20, 102);
insert into materials values (default, 'B', 30, 103);
insert into materials values (default, 'B', 31, 104);
insert into materials values (default, 'C', 22, 105);
insert into materials values (default, 'C', 41, 106);
insert into materials values (default, 'K', 44, 107);
insert into materials values (default, 'K', 40, 108);
insert into materials values (default, 'O', 11, 109);
insert into materials values (default, 'L', 15, 110);
insert into materials values (default, 'R', 18, 109);
insert into materials values (default, 'T', 36, 110);
```
Добавить таблицу suppliers с полями id, name
```
create table suppliers (
id serial primary key,
name varchar (50) not null
);
```
Добавить 12 строк в таблицу suppliers
```
insert into suppliers values (DEFAULT, 'Huawei');
insert into suppliers values (DEFAULT, 'Lenovo');
insert into suppliers values (DEFAULT, 'Zarya');
insert into suppliers values (DEFAULT, 'Microsoft');
insert into suppliers values (DEFAULT, 'Motorolla');
insert into suppliers values (DEFAULT, 'Samsung');
insert into suppliers values (DEFAULT, 'Microsoft');
insert into suppliers values (DEFAULT, 'Dom');
insert into suppliers values (DEFAULT, 'Samsung');
insert into suppliers values (DEFAULT, 'Nikon');
insert into suppliers values (DEFAULT, 'Omsk');
insert into suppliers values (DEFAULT, 'Samsung');
```
Обновить таблицу Materials. Добавить поле suplier_id которое связано с полем id в таблице Suppliers
```
alter table materials 
	add column supplier_id int,
	add foreign key (supplier_id)
		references suppliers (id);
```
Обновить таблицу Employees. Добавить varchar поле surname на 50 символов
```
alter table employees add column surname varchar (50);
```
Обновить таблицу Salary. Добавить varchar поле currency на 10 символов
```
alter table salary add column currency varchar (10);
```
Вывести имена всех сотрудников таблицы employees
```
select employees_name from employees;
```
Вывести всех сотрудников с именем «Victor»
```
select * from employees where employees_name = ‘'Victor';
```
Вывести всех сотрудников у которых имя оканчивается на «an»
```
select employees_name from employees where employees_name like ‘%an’;
```
Вывести количество поставщиков с названием Samsung
```
select count(*) as count from suppliers where name = 'Samsung';
```
Вывести id пользователя, имя, дату создания пользователя. Отсортировать по порядку возрастания даты добавления пользователя.
```
select user_id, username, created_on from qa_users order by created_on asc;
```
Вывести всех работников у которых ЗП меньше 1500
```
select employee_name, monthly_salary
from employees
join employees_salary
on employees.id = employees_salary.employee_id 
where monthly_salary < 2000;
```
Найти всех работников кому не начислена ЗП
```
select employee_name, monthly_salary 
from employees
left join employees_salary
on employees.id = employees_salary.employee_id
where monthly_salary is null;
```
Вывести всех работников с названиями должности
```
select employee_name, role_name
from roles_employees
full join employees
on roles_employees.employee_id = employees.id
left join roles
on role_id = roles.id;
```
Вывести имена сотрудников, у которых должность Engineer
```
select employee_name, role_name
from roles_employees
join employees
on roles_employees.employee_id = employees.id
join roles
on role_id = roles.id
where role_name like '%Engineer%';
```
Вывести количество HR
```
select COUNT(monthly_salary)
from employees
join employees_salary
on employees_salary.employee_id = employees.id
join roles_employees
on roles_employees.employee_id = employees.id
join roles
on role_id = roles.id
where role_name like '%HR%';
```
Вывести имена, должности и ЗП всех сотрудников по возрастанию
```
select employee_name, role_name, monthly_salary
from employees
left join employees_salary
on employees_salary.employee_id = employees.id
left join roles_employees
on roles_employees.employee_id = employees.id
left join roles
on role_id = roles.id
order by monthly_salary ASC;
```
Вывести имена, должности и ЗП всех сотрудников по возрастанию у сотрудников у которых ЗП меньше 1200
```
select employee_name, role_name, monthly_salary
from employees
left join employees_salary
on employees_salary.employee_id = employees.id
left join roles_employees
on roles_employees.employee_id = employees.id
left join roles
on role_id = roles.id
where "monthly_salary" < '2300'
order by monthly_salary ASC;
```
