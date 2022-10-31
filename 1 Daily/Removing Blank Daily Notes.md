
## Tasks List
```tasks
path includes Diary/Daily Notes
```

## Table for empty files
```dataview
TABLE URL as "Url", NewDiscovery as "ND", LifeEvent as "LE", PersonalProjects as "PP", ReadingLog as "RL", ListeningLog as "LL", VideoLog as "VL", WorkoutLog as "WL" FROM "1 Daily/Diary/Daily Notes" where contains(URL, "") and contains(NewDiscovery, "") or contains(LifeEvent, "") or contains(PersonalProjects, "") or contains(ReadingLog, "")or contains(ListeningLog, "") or contains(VideoLog, "") or contains(WorkoutLog, "")
```




`dataview 
table NewDiscovery as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(NewDiscovery, "")
sort file.name desc
`
