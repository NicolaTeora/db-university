# DB-univesity

### Dipertimenti

| FILED       | TYPE_DATA | ATTRIBBUTES |
| ----------- | --------- | ----------- |
| id          |           |             |
| settore_dip |           |             |
| nome_dip    |           |             |

### corsi laurea

| FILED      | TYPE_DATA | ATTRIBBUTES |
| ---------- | --------- | ----------- |
| id         |           |             |
| id_diparti |           |             |
| nome_cors  |           |             |

### Corso

| FILED           | TYPE_DATA | ATTRIBBUTES |
| --------------- | --------- | ----------- |
| id              |           |             |
| id_dipartimento |           |             |
| id_appello      |           |             |
| nome_corso      |           |             |
| materia         |           |             |
| num_studenti    |           |             |

### insegnanti

| FILED      | TYPE_DATA | ATTRIBBUTES |
| ---------- | --------- | ----------- |
| id         |           |             |
| nome       |           |             |
| cognome    |           |             |
| competenza |           |             |

### appelli d'esame

| FILED        | TYPE_DATA | ATTRIBBUTES |
| ------------ | --------- | ----------- |
| id           |           |             |
| data_appello |           |             |

### studenti

| FILED           | TYPE_DATA | ATTRIBBUTES |
| --------------- | --------- | ----------- |
| id              |           |             |
| nome            |           |             |
| cognome         |           |             |
| corso           |           |             |
| crediti         |           |             |
| anno_iscrizione |           |             |
