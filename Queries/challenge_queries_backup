SELECT e.emp_no, e.first_name, e.last_name, t.title, t.from_date, t.to_date
INTO retirement_titles
FROM employees AS e
INNER JOIN titles as t
ON e.emp_no=t.emp_no
WHERE birth_date BETWEEN '1952-01-01' AND '1955-12-31'
ORDER BY e.emp_no;

SELECT * FROM retirement_titles;

DROP TABLE retirement_titles;

-- Use Dictinct with Orderby to remove duplicate rows
SELECT DISTINCT ON (emp_no) emp_no,
first_name,
last_name,
title

INTO unique_titles
FROM retirement_titles
ORDER BY emp_no, to_date DESC;

SELECT COUNT(title) as t_count, title
INTO retiring_titles
FROM unique_titles
GROUP BY(title)
ORDER BY t_count DESC;

SELECT * FROM dept_employees;

SELECT DISTINCT ON(e.emp_no) e.emp_no, e.first_name, e.last_name, e.birth_date, 
		d.from_date, d.to_date, t.title
INTO mentorship_eligibility
FROM employees AS e
INNER JOIN dept_employees as d
ON e.emp_no=d.emp_no
INNER JOIN titles as t
ON e.emp_no=t.emp_no
WHERE d.to_date='9999-01-01'
AND e.birth_date BETWEEN '1965-01-01' AND '1965-12-31'
ORDER BY e.emp_no;