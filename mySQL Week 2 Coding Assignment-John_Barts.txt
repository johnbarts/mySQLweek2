SELECT t.title AS "Employee title",
COUNT(*) AS "Number of employees born after 1965-01-01" 
FROM employees e
NATURAL JOIN titles t
WHERE e.birth_date > '1965-01-01' 
AND t.to_date = '9999-01-01'
GROUP BY t.title;



SELECT t.title AS "Employee Title",
AVG(s.salary) AS "Average Salary"
FROM salaries s
INNER JOIN titles t ON s.emp_no = t.emp_no
WHERE t.to_date = '9999-01-01'
AND s.to_date = '9999-01-01'
GROUP BY t.title;



SELECT d.dept_name AS "Department", 
SUM(s.salary) AS "Total of salaries spent on Marketing dept between 1990 and 1992"
FROM departments d
INNER JOIN dept_emp de ON de.dept_no = d.dept_no
INNER JOIN salaries s ON s.emp_no = de.emp_no
WHERE de.from_date >= '1990-01-01'
AND de.to_date <= '1992-12-31'
AND d.dept_name = 'Marketing'
GROUP BY d.dept_name;









