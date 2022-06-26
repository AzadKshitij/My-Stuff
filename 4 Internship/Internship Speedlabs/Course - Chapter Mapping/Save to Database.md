---
date: 27/05/2022
tag: #speedlabs #callback
---

# To-Do
I need to store newly added values to a Data-Frame with proper column and order.

> [!note]+ SQL Query
> ``` sql
> SELECT TOP (1000) [CourseChapterId]
> ,[CourseId], [ClassId], [SubjectId], 
> [TopicId], [ChapterId], [IsActive], [DisplayRank]
> FROM [speedanon].[new].[CourseChapter]
> ```

## Table Structure
CourseChapterId | CourseId | ClassId | SubjectId | TopicId | ChapterId | IsActive
----------------|----------|---------|-----------|---------|-----------|----------
==3711== | 54 | 26 |32 |NULL | 2601 | 1 | 1

> [!question]+ What dose the display rank means????
> ![[Assets/Pasted image 20220528095516.png]]

