# Joins:


## Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
``` sql

SELECT `students`.`*` , `degrees`.`name` AS `degree_name` 
FROM `students` 
JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id` 
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';

```


## Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
``` sql

SELECT `degrees`.*, `departments`.`name` AS `department_name` 
FROM `degrees` 
JOIN `departments` ON `degrees`.`department_id` = `departments`.`id` 
WHERE `degrees`.`level` = 'Magistrale' 
AND `departments`.`name` = 'Dipartimento di Neuroscienze';

```


## Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
``` sql

SELECT `courses`.`id`,`courses`.`name`, `teachers`.`name`,`teachers`.`surname`
FROM `courses`
JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`id` = 44;

```


## Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome
``` sql

SELECT DISTINCT `students`.* , `degrees`.`name` AS `degree`, `departments`.`name` AS `department`
FROM `students`
JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`  
ORDER BY `students`.`name` ASC, `students`.`surname` ASC;

```


## Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
``` sql

SELECT DISTINCT `degrees`.`name` AS `degree_name`, `courses`.`name` AS `course	_name`, `teachers`.`name` AS `teacher_name`,`teachers`.`surname` AS `teacher_surname`
FROM `degrees`
JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;

```


## Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
``` sql

SELECT DISTINCT `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`,`departments`.`name`
FROM `teachers`
JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id`
JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica';

```


## BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
``` sql



```

