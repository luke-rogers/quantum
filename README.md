# quantum
Simple command line time tracking app

## Usages

### Starting and stopping a task
You can start by using `start` followed by the task name and optionally a ref.
Stopping follows a similar fashion by using `stop` followed by the task name. Once the task has been stopped it will be
added to the full list of tasks.

```
quantum start "FMO-123" "REF-001"
quantum stop "FMO-123"
```

#### List in-progress tasks
To list in-progress tasks use `list inprogress`

```
+--------+-----+---------------------+
|  TASK  | REF |       STARTED       |
+--------+-----+---------------------+
| tester |     | 2018-02-12 22:41:24 |
+--------+-----+---------------------+
```

### Manually add a task
Add a task using `add` or `a`. Arguments are task (mandatory), followed by number of hours (mandatory) and ref (optional).

```
quantum add "Build quantum cli" 10.5 "Ref code: 123"
quantum a "Build quantum cli" 10.5 "Ref code: 123"
```

### Listing tasks

List the tasks by using `list` or `l`. By default this will show the tasks in the last 7 days. Optional parameter allows you to configure the number of previous days to search over.
```
quantum list
quantum l 10
```
There is also additional support for easy sub commands to search over the past month or year using `list month` or `list year` respectively.
```
quantum list month
quantum list year
```

#### List by task or ref
List tasks by task name or ref using `list task` and `list ref` followed by a space separated list of values to match against
```
quantum list task "QUANTUM-001" "QUANTUM-002"
quantum list ref "QUANTUM-001" "QUANTUM-002"
```

#### List Result
```
+---------+-------+-----------+---------------------+-----------------------------+
|  TASK   | HOURS |    REF    |        DATE         |             UID             |
+---------+-------+-----------+---------------------+-----------------------------+
| FMO-123 |  5.00 |           | 2018-02-12 21:21:17 | 10T0qh4Pm4CPVZw2Z1KaNcjYuXr |
| FMO-456 |  8.00 |           | 2018-02-12 21:21:23 | 10T0rZ93n1Y8kGLTtXU4hOpU24R |
| FMO-789 |  8.00 |           | 2018-02-12 21:21:28 | 10T0s6DZxZ54uWtWcgX6xeP2Vkt |
| FMO-123 |  4.00 |           | 2018-02-12 21:21:33 | 10T0skk088OMfccTTfvb8SeFnK7 |
| FMO-501 |  5.00 | RANDOMREF | 2018-02-12 21:38:37 | 10T2xUQGOJYL9cHown55rc9II3F |
| FMO-110 |  4.50 |           | 2018-02-12 21:49:27 | 10T4H7UzAnUWeVKBUrIQbgCJkBK |
+---------+-------+-----------+---------------------+-----------------------------+
|                                   TOTAL HOURS     |            34 50            |
+---------+-------+-----------+---------------------+-----------------------------+
```

### Deleting tasks
Delete a task by using `delete` or `d`. Takes a space separated list of uids.

```
quantum delete 10Q9i8n6x2djb53ClMSswxFaD9l 10T0qh4Pm4CPVZw2Z1KaNcjYuXr
quantum d 10Q9i8n6x2djb53ClMSswxFaD9l
```

#### Delete all tasks

Delete all tasks by using quantum 'delete all' or 'd all'.

```
quantum delete all
quantum d all
```
