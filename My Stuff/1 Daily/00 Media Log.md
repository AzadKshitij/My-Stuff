<- [[00 Daily Notes Hub | Daily Notes Hub]]


# Media Log
💡 [[00 New Discoveries Log | New Discoveries]] | 🛳️ [[00 Ship's Log|Ship's Log]] | 🏋️ [[00 Workout Log | Workout Log]]  | ❗[[00 Tasks Log | Tasks Log]]

Media Log contains mini-reviews on the books/articles I read and the videos I watch.





## Listening Log
---
```dataview
table ListeningLog as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(ListeningLog, "")
sort file.name desc
```

## Reading Log
---
```dataview
table ReadingLog as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(ReadingLog, "")
sort file.name desc
```


## Video Log
---
```dataview
table VideoLog as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(VideoLog, "")
sort file.name desc
```
