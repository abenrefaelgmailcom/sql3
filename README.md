# sql3
summery in sql

CREATE TABLE grades (
    grade_id INTEGER PRIMARY KEY AUTOINCREMENT,
    student_name TEXT NOT NULL,
    subject_name TEXT NOT NULL,
    exam_year INTEGER NOT NULL,
    grade INTEGER NOT NULL
);

INSERT INTO grades (student_name, subject_name, exam_year, grade) 
VALUES 
('Jon Snow', 'Mathematics', 2022, 87),
('Arya Stark', 'Physics', 2024, 92),
('Tyrion Lannister', 'Biology', 2022, 89),
('Daenerys Targaryen', 'History', 2023, 91),
('Bran Stark', 'Chemistry', 2023, 81),
('Cersei Lannister', 'Mathematics', 2023, 85),
('Jaime Lannister', 'Physics', 2022, 83),
('Sandor Clegane', 'History', 2024, 77),
('Samwell Tarly', 'Chemistry', 2023, 93),
('Jorah Mormont', 'Biology', 2022, 79),
('Arya Stark', 'Mathematics', 2023, 95),
('Jon Snow', 'Physics', 2023, 91),
('Daenerys Targaryen', 'Mathematics', 2023, 89),
('Sandor Clegane', 'Physics', 2024, 79),
('Tyrion Lannister', 'Chemistry', 2024, 94),
('Samwell Tarly', 'Mathematics', 2024, 92),
('Bran Stark', 'History', 2022, 83),
('Cersei Lannister', 'Biology', 2023, 80),
('Jaime Lannister', 'Chemistry', 2024, 86),
('Jorah Mormont', 'History', 2023, 77),
('Arya Stark', 'History', 2024, 90),
('Jon Snow', 'Biology', 2022, 84),
('Samwell Tarly', 'Physics', 2022, 91),
('Tyrion Lannister', 'History', 2023, 95),
('Daenerys Targaryen', 'Physics', 2024, 92),
('Bran Stark', 'Mathematics', 2024, 88),
('Sandor Clegane', 'Biology', 2023, 78),
('Cersei Lannister', 'Chemistry', 2022, 77),
('Jorah Mormont', 'Mathematics', 2022, 78),
('Jaime Lannister', 'History', 2023, 84),
('Jon Snow', 'Chemistry', 2024, 88),
('Arya Stark', 'Biology', 2023, 88),
('Samwell Tarly', 'Biology', 2024, 90),
('Daenerys Targaryen', 'Chemistry', 2022, 85),
('Tyrion Lannister', 'Physics', 2023, 93),
('Cersei Lannister', 'History', 2024, 82),
('Bran Stark', 'Physics', 2022, 82),
('Jorah Mormont', 'Physics', 2023, 76),
('Sandor Clegane', 'Chemistry', 2022, 76),
('Jaime Lannister', 'Mathematics', 2022, 84);

---1 sum all grades for each year---
SELECT exam_year, AVG(grade) AS average_grade
FROM grades
GROUP BY exam_year;


---2 sum grade for each studednt in seperate for year 2024---
SELECT student_name, AVG(grade) AS average_grade
FROM grades
WHERE exam_year = 2024
GROUP BY student_name;

---3 highest and lowest grade in each subject for every year---
SELECT exam_year, subject_name, MAX(grade) AS max_grade, MIN(grade) AS min_grade
FROM grades
GROUP BY exam_year, subject_name;


----4 test count for each subject each year---
SELECT exam_year, subject_name, COUNT(*) AS exam_count
FROM grades
GROUP BY exam_year, subject_name;

--- 5 subjects which sum grades is bigger then 85---
SELECT subject_name, AVG(grade) AS average_grade
FROM grades
GROUP BY subject_name
HAVING AVG(grade) > 85;

---6 how many times grade 90 appeared ---
SELECT grade, COUNT(*) AS occurrences
FROM grades
WHERE grade > 90
GROUP BY grade;




