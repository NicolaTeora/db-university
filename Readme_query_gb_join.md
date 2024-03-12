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
