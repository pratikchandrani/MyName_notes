{{title}}

Tasks due from earlier
```dataviewjs
dv.taskList(dv.pages().file.tasks
	.where(t => !t.completed))
```


---
---
## Daily work updates










## End of daily work updates

## List of notes in past week

```dataview 
TABLE file.ctime AS "Created" 
WHERE file.ctime >= date(today) - dur(7 days) 
```
