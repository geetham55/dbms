CREATE TABLE department (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(100) NOT NULL,
    manager_id INT,
    location VARCHAR(100)
);

desc department;

CREATE TABLE employee (
    emp_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    hire_date DATE NOT NULL,
    job_id VARCHAR(20) NOT NULL,
    salary DECIMAL(10,2) NOT NULL,
    commission_pct DECIMAL(5,2),
    manager_id INT,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES department(dept_id)
);

desc employee;


INSERT INTO department (dept_id, dept_name, manager_id, location) VALUES
(101, 'Information Technology', 1005, 'New York');

INSERT INTO department (dept_id, dept_name, manager_id, location) VALUES
(102, 'Human Resources', 1005, 'San Francisco');

INSERT INTO department (dept_id, dept_name, manager_id, location) VALUES
(103, 'Sales', 1006, 'Los Angeles');

INSERT INTO department (dept_id, dept_name, manager_id, location) VALUES
(104, 'Marketing', 1007, 'Chicago');

select * from department;


INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1001, 'Rama', 'Rao', 'ramarao@site.edu', '15-MAR-05', 'IT_PROG', 60000, 0.10, 1005, 101);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1002, 'Vyshnavi', 'Priya', 'vyshnavipriya@sasi.edu', '22-JUL-10', 'HR_REP', 45000, NULL, 1005, 102);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1003, 'Bhuvana', 'Reddy', 'bhuvanareddy@site.edu', '01-DEC-08', 'SR_REP', 50000, 0.05, 1006, 103);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1004, 'Manisha', 'Rao', 'manasharao@site.edu', '17-MAY-12', 'MK_MAN', 55000, 0.15, 1007, 104);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1005, 'Lakshmi', 'Pati', 'lashmipati@sasi.edu', '10-JAN-00', 'IT_MANAGE', 80000, NULL, NULL, 101);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1006, 'Sakhsi', 'Reddy', 'sakhsireddy@site.edu', '19-AUG-14', 'HR_REP', 48000, NULL, 1005, 102);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1007, 'Mounika', 'Murthy', 'mounikamurthy@sasi.edu', '10-APR-15', 'IT_PROG', 65000, 0.08, 1005, 101);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1008, 'Obul', 'Reddy', 'obulreddy@site.edu', '25-FEB-16', 'MK_REP', 47000, 0.05, 1004, 104);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1009, 'Jhansi', 'Rani', 'jhansirani.edu', '18-SEP-17', 'SA_REP', 52000, 0.10, 1006, 103);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1010, 'Indira', 'Devi', 'indiradevi@sasi.edu', '30-NOV-18', 'HR_REP', 46000, NULL, 1005, 102);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1011, 'Edu', 'Konsalu', 'edukondalu@sasi.etu', '20-MAR-19', 'IT_PROG', 70000, 0.12, 1005, 101);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1012, 'Mani', 'Mohan', 'manimohan@site.edu', '15-JUL-20', 'SA_REP', 51000, 0.07, 1006, 103);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1013, 'Jaswanth', 'Naidu', 'jaswanthnaidu@site.edu', '05-JAN-21', 'MK_REP', 48000, 0.06, 1004, 104);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1014, 'Mahi', 'Rao', 'mahirao@site.edu', '13-AUG-21', 'IT_PROG', 69000, 0.09, 1005, 101);

INSERT INTO employee (emp_id, first_name, last_name, email, hire_date, job_id, salary, commission_pct, manager_id, department_id) VALUES
(1015, 'Nageswar', 'Rao', 'nageswararao@site.edu', '08-JUN-22', 'SR_REP', 54000, 0.11,1006, 103);


select * from employee;

select count(emp_id) from employee;

select sum(salary) from employee;

select avg(salary) from employee;

select max(salary) from employee;

select min(salary) from employee;

select department_id as "Department Id",avg(salary) as "Average Salary"  from employee group by department_id;

select department_id , count(emp_id) from employee group by department_id;

select department_id  ,max(salary) as "Higgest Salary" from employee group by department_id;

select department_id, sum(salary) from employee group by department_id having sum(salary)>300000;
