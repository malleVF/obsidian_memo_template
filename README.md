# obsidian_memo_template
 inspired by [mulfok/periodic-note-templates ](https://github.com/mulfok/periodic-note-templates)

## Required Community Plugins
- [CustomJS](https://github.com/samlewis0602/obsidian-custom-js)
- [Dynamic Table of Contents](https://github.com/Aidurber/obsidian-plugin-dynamic-toc)
- [Dataview](https://github.com/blacksmithgu/obsidian-dataview)
- [Obsidian Charts](https://github.com/phibr0/obsidian-charts)
- [Periodic Notes](https://github.com/liamcain/obsidian-periodic-notes)
- [Tasks](https://github.com/schemar/obsidian-tasks)
- [Templater](https://github.com/SilentVoid13/Templater)

## Recommended Community Plugins
- [Emoji Toolbar](https://github.com/oliveryh/obsidian-emoji-toolbar)
- [CardBoard](https://github.com/roovo/obsidian-card-board)

## User Manual

### Create new 'Daily Log' and 'Weekly Journal' note

Recommendation: 
1. Create only a new 'Daily Log' note for the current day!
1. Create only a new 'Weekly Journal' note at the begin of the new week!

The memo has some limitations.

In the created 'Daily Log' note you can jump back to the previous day and forwards to the next day. If the 'Daily Log' note for next day does not exist, it will create a new note with timestamp of next day.

**But caution!** In the metada section of the new created note, the created day is still the current day and not the next day and the week is the current week. That could cause some issues in case of creating a new note for the next day at the last day of the week. Then, the week of the 'Daily Log' for the next day in next week is still the current week.

### How to add learnt words

Their is a field **Learnt Words::** in the 'Daily Log' note, where you can add list of words, like a vocabulary.

You can have any number of words in the field, but it must always be key-value formatted as "word","meaning"
```
- Learnt Word:: "my new learnt word","what a great idea to create a list of new learnt words to my daily memo"
```
![learntword](https://user-images.githubusercontent.com/40318953/214413602-29a372aa-e0b3-4b1e-8f43-34f087dae699.png)

### How to use tasks
You can create tasks in the Daily Log, but they are not listed in the Weekly Journal. Therefore I recommend CardBoard (see recommended community plugins).
Following hashtags helps me to show my tasks in CardBoard:
```
#kb/todo
#kb/inprogress
```
To assign the task to a person (e.g. Bob, Alice, Family, ...):
```
#who/bob
#who/alice
#who/family
```
To add the task to a project (e.g. Office task, Home task, China travel, ...):
```
#project/office
#project/home
#project/china-travel
```
To add the due date
```
@due(2023-01-31)
```

To show up the tasks in CardBoard, you have to create couple of **Tag boards** with title
1. Task
1. Who
1. Project

![cb_who](https://user-images.githubusercontent.com/40318953/214409660-022a6503-67b4-4312-a4b3-e85a4817a540.png)




To show tasks based on due date, you have to create a **Date Board**.
1. When

![cb_when](https://user-images.githubusercontent.com/40318953/214407632-50670aa2-753b-48b7-b8ca-4c374d47a804.png)

## Settings to get it running:

### Final folder structure
![folder_Structure](https://user-images.githubusercontent.com/40318953/214385423-c285956c-b250-49b7-98a3-5af25672cda9.png)

Create folders 
```
01 Personal Note
   0 Templates
```

### Folder 0 Templates
Copy templates and DvCharts.js into the template folder 

![folder_0 Template_structure](https://user-images.githubusercontent.com/40318953/214386222-6ead6a56-8686-4438-81ed-5eb01828699d.png)

### Setup Plugins CustomJS

Individual files: ```DVCharts.js```

Folder: ```01 Personal Note/0 Templates```

### Setup Plugin Dataview

Enable **JavaScript Queries**

Data Format: ```yyyy-MM-dd```

Date + Time Format: ```yyy-MM-dd @ h:mm```

### Setup Plugin Periodic Notes
**Enable Daily Notes**

Format: ```MM MMMM/YYYY-MM-DD```

looks like this: 01 January/2023-01-24

Daily Note Template: ```01 Personal Note/0 Templates/Daily Log.md```

Note Folder: ```01 Personal Note/2023/Daily```

Enable **Weekly Notes**

Format: ```YYYY-MM [Week] WW```

looks like this: 2023-01 Week 04

Daily Note Template: ```01 Personal Note/0 Templates/Weekly Journal.md```

Note Folder: ```01 Personal Note/2023/Weekly```

### Setup Plugin Templater

Enable **Syntax Highlighting**

Enable **Trigger Templater on new file creation**

Enable **Enable Folder Templates**

**Add new** folder template:

|||
|---|---|
|01 Personal Note/2023/Daily | 01 Personal Note/0 Templates/Daily Log.md|
|01 Personal Note/2023/Weekly | 01 Personal Note/0 Templates/Weekly Journal.md|



