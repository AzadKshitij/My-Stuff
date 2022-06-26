<- [[00 Daily Notes Hub | Daily Notes Hub]]


# Ship's Log
💡 [[1 Daily/00 New Discoveries Log| New Discoveries]] | 🛳️ [[1 Daily/00 Ship's Log|Ship's Log]] | 📚 [[1 Daily/00 Media Log| Media Log]] | 🏋️ [[1 Daily/00 Workout Log| Workout Log]]

The Ship's Log is divided into two sections: **Life Happenings** and **Personal Projects**.

Life Happenings for any event and accomplishments made. Personal Projects is for anything related to a non-work project that you do (i.e. blog, YouTube video, streaming)




## Life Happenings
---

```dataview
table LifeEvent as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(LifeEvent, "")
sort file.name desc
```

## Personal Projects
---
```dataview
table PersonalProjects as "Log"
from "1 Daily/Diary/Daily Notes"
where contains(PersonalProjects, "")
sort file.name desc
```