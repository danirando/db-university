```sql

1.

SELECT `students`.*
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = "corso di laurea in economia"

2.

SELECT `degrees`.*
FROM `departments`
INNER JOIN `degrees`
ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = "dipartimento di neuroscienze" AND `degrees`.`level` = "magistrale"

3.

SELECT `courses`.*
FROM `teachers`
INNER JOIN `course_teacher`
ON `teachers`.`id` = `course_teacher`.`teacher_id`


INNER JOIN `courses`
ON `courses`.`id` = `course_teacher`.`course_id`

WHERE `teacher_id` = 44

4.

SELECT `students`.`name` `student_name`,
		`students`.`surname` `student_surname`,
        `degrees`.`name` `degree_name`,
        `departments`.`name` `department_name`
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`

ORDER BY `students`.`surname`

5.

SELECT `degrees`.`name` `degree_name`,
		`courses`.`name` `course_name`,
        `teachers`.`name` `teacher_name`,
        `teachers`.`surname` `teacher_surname`
FROM `degrees`
INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

6.

SELECT DISTINCT `teachers`.*
        
FROM `degrees`
INNER JOIN `courses`
ON `degrees`.`id` = `courses`.`degree_id`

INNER JOIN `course_teacher`
ON `courses`.`id` = `course_teacher`.`course_id`

INNER JOIN `teachers`
ON `course_teacher`.`teacher_id` = `teachers`.`id`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`

WHERE `departments`.`name` = "dipartimento di matematica"

