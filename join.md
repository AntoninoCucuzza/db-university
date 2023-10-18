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



```


## Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
``` sql

sasa

```


## Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)
``` sql

sasa

```


## BONUS: Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.
``` sql



```

