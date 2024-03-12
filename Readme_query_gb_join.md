## GROUP BY

1. Contare quanti iscritti ci sono stati ogni anno

```SQL
SELECT `enrolment_date`, COUNT(`enrolment_date`) AS `num_enrolment` FROM `students` GROUP BY `enrolment_date`;
```

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

```SQL
SELECT `office_address`, COUNT(`name`) AS `num_teachers` FROM `teachers` GROUP BY `office_address`;
```

3. Calcolare la media dei voti di ogni appello d'esame

```SQL
SELECT `exam_id` , AVG(`vote`) FROM `exam_student` GROUP BY `exam_id`;
```

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

```SQL
SELECT `department_id` AS `deparment`, COUNT(`name`) AS `num_courses` FROM `degrees` GROUP BY `department_id`;
```

## JOIN

1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```SQL
SELECT `students`.*
FROM `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
INNER JOIN `courses` ON `courses`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
   Neuroscienze

```SQL
SELECT `courses`.*
FROM `courses`
INNER JOIN `degrees`
ON `courses`.`degree_id` = `degrees`.`id`
INNER JOIN `departments`
ON `degrees`.`department_id` = `departments`.`id`
WHERE
    `departments`.`name` = 'Dipartimento di Neuroscienze'
        AND
    `degrees`.`name` LIKE 'Corso di Laurea Magistrale%';
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```

```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
   sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
   nome

```

```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di
   Matematica (54)

```

```

7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
   per ogni esame, stampando anche il voto massimo. Successivamente,
   filtrare i tentativi con voto minimo 18.

```

```
