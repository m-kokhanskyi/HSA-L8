Використав laradock, обновивши версії percona і postgres до останньої
> docker-compose up -d percona postgres

І в консолці відтворив феномини:  
   
Percona

| Isolation level | Dirty reads | Nonrepeatable Read | Phantom Read | Lost update |
| :--- | :--- | :--- | :--- | :--- |
| Read uncommitted | + | + | + | + |
| Read committed | - | + | + | + |
| Repeatable read | - | - | + | + |
| Serializable | - | - | - | - |

Postgres

| Isolation level | Dirty reads | Nonrepeatable Read | Phantom Read | Lost update |
| :--- | :--- | :--- | :--- | :--- |
| Read uncommitted | - | + | + | - |
| Read committed | - | + | + | - |
| Repeatable read | - | - | - | - |
| Serializable | - | - | - | - |
