```sql 

1.

SELECT YEAR(`enrolment_date`) AS `anno`, COUNT(`id`) AS `numero_studenti`
FROM `students`
GROUP BY YEAR(`enrolment_date`)
ORDER BY `anno`;

2.

