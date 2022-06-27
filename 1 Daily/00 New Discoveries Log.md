<- [[00 Daily Notes Hub | Daily Notes Hub]]


# New Discoveries Log
💡 [[1 Daily/00 New Discoveries Log| New Discoveries]] | 🛳️ [[1 Daily/00 Ship's Log|Ship's Log]] | 📚 [[1 Daily/00 Media Log| Media Log]] | 🏋️ [[1 Daily/00 Workout Log| Workout Log]]

A log containing the interesting discoveries from the Daily Notes.


## List
---
```dataview
table NewDiscovery as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(NewDiscovery, "")
sort file.name desc
```



```dataview
table URL as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(URL, "")
sort file.name desc
```
