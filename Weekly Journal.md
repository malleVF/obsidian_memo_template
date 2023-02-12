---
tags:
 - "#calendar/weekly/<% tp.date.now('YYYY') %>"
Created:: [[<% tp.date.now('YYYY-MM-DD') %>]] <% tp.date.now('HH:mm') %>
Updated:: <% tp.date.now('YYYY-MM-DD HH:mm') %>
ID:: <% tp.date.now('YYYYMMDDHHmmss') %>

---

# <% tp.date.now("YYYY-MM [Week] WW") %>

[[01 Personal Note/<% tp.date.now("YYYY[/Weekly/]YYYY-MM [Week] WW", -7) %>|↶ Previous Week]] | [[01 Personal Note/<% tp.date.now("YYYY[/Weekly/]YYYY-MM [Week] WW", 7) %>|Following Week ↷]]


###### Table of Contents:
```toc
style: number
min_depth: 1
max_depth: 3
```

___

## Memos
- [[<% tp.date.weekday("YYYY-MM-DD", 1) %>|Monday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 1) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 2) %>|Tuesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 2) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 3) %>|Wednesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 3) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 4) %>|Thursday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 4) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 5) %>|Friday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 5) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 6) %>|Saturday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 6) %>#^memo-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 7) %>|Sunday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 7) %>#^memo-link]]

## Work Log
- [[<% tp.date.weekday("YYYY-MM-DD", 1) %>|Monday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 1) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 2) %>|Tuesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 2) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 3) %>|Wednesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 3) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 4) %>|Thursday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 4) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 5) %>|Friday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 5) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 6) %>|Saturday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 6) %>#^work-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 7) %>|Sunday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 7) %>#^work-link]] 

## ToDo

- [x] Heizung in Lank prüfen #kb/todo #project/lank #who/markus ✅ 2023-02-04

## Overview
### Week Statistics
```dataviewjs
const daysPath = dv.current().file.folder;

const attributes = {
	'bloodpressure_sys': {
		label: '📈',
		backgroundColor: 'rgba(85, 174, 229, 0.2)',
		borderColor: 'rgba(85, 174, 229, 1)',
		average: 100,
	},
	'bloodpressure_dia': {
		label: '📉',
		backgroundColor: 'rgba(20, 85, 182, 0.2)',
		borderColor: 'rgba(20, 85, 182, 1)',
		average: 100,
	},
	'pulse': {
		label: '💗',
		backgroundColor: 'rgba(255, 211, 101, 0.2)',
		borderColor: 'rgba(255, 211, 101, 1)',
		average: 100,
	},
	'bloodpressure_pp': {
		label: '🩸',
		backgroundColor: 'rgba(255, 211, 101, 0.2)',
		borderColor: 'rgba(255, 211, 101, 1)',
		average: 100,
	}, 
	'steps': {
		label: 'Steps',
		backgroundColor: 'rgba(141, 82, 188, 0.2)',
		borderColor: 'rgba(141, 82, 188, 1)',
		average: 100,
	},
	'hours-worked': {
		label : 'Hours Worked',
		backgroundColor: 'rgba(143, 208, 50, 0.2)',
		borderColor: 'rgba(143, 208, 50, 1)',
		average: 100
	},
};

const date = "<% tp.date.now('YYYY-MM-DD') %>";

customJS.DvCharts.renderWeeklyChart({
	dv,
	context: this,
	daysPath: '01 Personal Note/<% tp.date.now("YYYY") %>/Daily',
	attributes,
	type: 'average',
	date
})
```

```dataview
TABLE WITHOUT ID
	link(file.name) as "Day",
	bloodpressure_sys AS "📈",
	bloodpressure_dia AS "📉",
	pulse AS "💗",
	bloodpressure_pp AS "🩸",
	steps AS "👣",
	hours-worked AS "🧰"
FROM "01 Personal Note"
WHERE week = [[<% tp.date.now("YYYY [Week] WW") %>]]
SORT file.name ASC
```

### Habits
```dataview
TABLE WITHOUT ID
	file.link AS "Day",
	water AS "🍶",
	drinks AS "🍷",
	workout AS "🏋️",
	lecture AS "📑"
FROM "01 Personal Note"
WHERE week = [[<% tp.date.now("YYYY [Week] WW") %>]]
SORT file.name ASC
```

### Learnt Words
```dataviewjs
dv.table(
	["Learnt Word", "Meaning"],
	dv.pages('"01 Personal Note"')
	.filter(p => p["Learnt Word"] && p.week.path == "<% tp.date.now("YYYY [Week] WW") %>")
	.sort(p => dv.date(p.file.name), 'asc')
	.flatMap(p =>
		Array.from(
			{
				length: Math.floor(
					p["Learnt Word"].length / 2
				)
			},
			(_, i) => [
				`${'**'}${p["Learnt Word"][i * 2]}${'**'}`,
				p["Learnt Word"][(i * 2) +1]
			]
		)
	)
)
```

## Energie-Tagebuch
```dataview
TABLE WITHOUT ID
	file.link AS "Day",
	morgens AS "morgens",
	mittags AS "mittags",
	nachmittags AS "nachmittags",
	abends AS "abends"
FROM "01 Personal Note"
WHERE week = [[<% tp.date.now("YYYY [Week] WW") %>]]
SORT file.name ASC
```

### Emotionstracker
- [[<% tp.date.weekday("YYYY-MM-DD", 1) %>|Monday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 1) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 2) %>|Tuesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 2) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 3) %>|Wednesday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 3) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 4) %>|Thursday]] 
    ![[<% tp.date.weekday("YYYY-MM-DD", 4) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 5) %>|Friday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 5) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 6) %>|Saturday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 6) %>#^emotion-link]]
- [[<% tp.date.weekday("YYYY-MM-DD", 7) %>|Sunday]]
	![[<% tp.date.weekday("YYYY-MM-DD", 7) %>#^emotion-link]] 
