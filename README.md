# quantum
Simple command line time tracking app

## Usages

### Add
Add a task using `add` or `a`. Arguments are task (mandatory), followed by integer number of hours (mandatory) and ref (optional).

```
quantum add "Build quantum cli" 10 "Ref code: 123"
quantum a "Build quantum cli" 10 "Ref code: 123"
```

### List
List the tasks by using `list` or `l`. By default this will show the tasks in the last 7 days. `--days` optional flag allows you to configure the number of days to search over.

```
quantum list
quantum l --days 10
```
```
+-------------------+-------+---------------+---------------------+-----------------------------+
|       TASK        | HOURS |      REF      |        DATE         |             UID             |
+-------------------+-------+---------------+---------------------+-----------------------------+
| Build quantum cli |    10 | Ref code: 123 | 2018-02-11 21:04:43 | 10Q9i8n6x2djb53ClMSswxFaD9l |
| Jira QUANTUM-001  |     5 |               | 2018-02-11 21:06:13 | 10Q9tYiMyl8EiLRZGAETGyiIS2A |
+-------------------+-------+---------------+---------------------+-----------------------------+
|                                                 TOTAL HOURS     |             15              |
+-------------------+-------+---------------+---------------------+-----------------------------+
```
### Delete
Delete a task by using `delete` or `d`. Takes a single uid argument or the record to delete.

```
quantum delete 10Q9i8n6x2djb53ClMSswxFaD9l
quantum d 10Q9i8n6x2djb53ClMSswxFaD9l
```

#### Delete all

Delete all tasks by using quantum 'delete all' or 'd all'.

```
quantum delete all
quantum d all
```
