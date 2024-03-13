## GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno

```SQL
SELECT `enrolment_date`, COUNT(`enrolment_date`) AS `num_enrolment`
FROM `students`
GROUP BY `enrolment_date`;
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```SQL
SELECT `office_address`, COUNT(`name`) AS `num_teachers`
FROM `teachers`
GROUP BY `office_address`;
```

3. Calcolare la media dei voti di ogni appello d'esame

```SQL
SELECT `exam_id` , AVG(`vote`)
FROM `exam_student`
GROUP BY `exam_id`;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```SQL
SELECT `department_id` AS `deparment`, COUNT(`name`) AS `num_courses`
FROM `degrees`
GROUP BY `department_id`;
```

## JOIN

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL
SELECT `students`.*
FROM `students`
INNER JOIN `degrees`
ON `students`.`degree_id` = `degrees`.`id`

WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze

```SQL
SELECT `degrees`.*
FROM `degrees`

INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE
    `departments`.`name` = 'Dipartimento di Neuroscienze'
        AND
    `degrees`.`name` LIKE 'Corso di Laurea Magistrale%';
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```SQL
SELECT `courses`.`name` , `teachers`.`name`
FROM `courses`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`
WHERE `teachers`.`name` = 'Fulvio' AND `teachers`.`surname` = 'Amato';
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

```SQL
SELECT
	`students`.`name` AS `nome_studente`,
    `students`.`surname` AS `cognome_studente`,
    `degrees`.`name` AS `nome_corso`,
    `departments`.`name` AS `dipartimento`
FROM `students`
INNER JOIN `degrees` ON `degrees`.`id` = `students`.`degree_id`
INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
ORDER BY `cognome_studente`;
```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```SQL
SELECT
	`degrees`.`name` AS `corso_di_laurea`,
    `courses`.`name` AS `nome_corso`,
    `teachers`.`name` AS `nome_insegnante`
FROM `degrees`
INNER JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `course_teacher` ON `course_teacher`.`course_id` = `courses`.`id`
INNER JOIN `teachers` ON `teachers`.`id` = `course_teacher`.`teacher_id`;
```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

```SQL
SELECT
	`teachers`.`name` AS `nome_insegnante`,
	`teachers`.`surname` AS `cognome_insegnante`,
    `departments`.`name`
FROM `teachers`
INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
INNER JOIN `courses` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `degrees` ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
WHERE `departments`.`name` = 'Dipartimento di Matematica';
```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```

```
