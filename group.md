# Group by:


## Contare quanti iscritti ci sono stati ogni anno
```sql

SELECT YEAR(`enrolment_date`) AS `enrolment_year`, COUNT(*) AS `student_count`
FROM `students`
GROUP BY YEAR(`enrolment_date`);

```


## Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql

SELECT `office_address`, COUNT(*) AS `teachers`
FROM `teachers`
GROUP BY `office_address`;

```


## Calcolare la media dei voti di ogni appello d'esame
``` sql

SELECT COUNT(`exam_id`) AS `exams_count`, AVG(`vote`) AS `avg_vote` 
FROM `exam_student` 
GROUP BY `exam_id` 

```


## Contare quanti corsi di laurea ci sono per ogni dipartimento
``` sql

SELECT COUNT(*) AS `corsi di laurea`, `department_id`
FROM `degrees`
GROUP BY `department_id`;

```

