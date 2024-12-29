# What is N + 1 Problem

When you query to get a set of records, we assume it is N records (1 query)

And then we perform each query for each record (N query)

=> This is N + 1 problem

N+1 problem is typical issue for database performance

ex:
composer
| id | name|
|----|-------------|
| 1 | Roddy Rich |
| 2 | The Weekn |

song
| id | composer_id | song |
|----|-------------|------------|
| 1 | 1 | The Box |
| 2 | 2 | Blinding Lights |
| 3 | 1 | High Fashion |

```sql
select * from composer

select * from song where composer_id = '1'
select * from song where composer_id = '2'

```

# How to fix

1. Using Join

```sql
select *
from composer Join song on composer.id = song.composer_id
```

2. Using Where ... IN

```sql
select * from song
where composer_id in (1, 2)
```
