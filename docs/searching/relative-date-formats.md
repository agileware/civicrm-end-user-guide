# Relative date filters

The list of relative date filters below ship with CiviCRM. You can see the
list on your site at the url civicrm/admin/options/relative_date_filters.
It is possible to add some additional ones within fairly tight constraints
(this is explained after the list)

| value | Means |
| ---- | ---- |
| current.month | Current calendar month to-date |
| current.year | Current calendar year to-date |
| current.quarter | Current quarter to-date |
| current.week | Current week to-date |
| previous\_before.day | Day prior to yesterday |
| greater\_previous.month | From end of previous calendar month |
| greater\_previous.year | From end of previous calendar year |
| greater\_previous.quarter | From end of previous quarter |
| greater\_previous.week | From end of previous week |
| greater.month | From start of current calendar month |
| greater.year | From start of current calendar year |
| greater.day | From start of current day |
| greater.quarter | From start of current quarter |
| greater.week | From start of current week |
| ending.year | Last 12 months including today |
| ending\_2.year | Last 2 years including today |
| ending\_3.year | Last 3 years including today |
| ending\_30.day | Last 30 days including today |
| ending\_60.day | Last 60 days including today |
| ending.week | Last 7 days including today |
| ending\_90.day | Last 90 days including today |
| previous\_before.month | Month prior to previous calendar month |
| starting.year | Next 12 months including today |
| starting.month | Next 30 days including today |
| starting\_2.month | Next 60 days including today |
| starting.week | Next 7 days including today |
| starting.quarter | Next 90 days including today |
| next.month | Next calendar month |
| next.year | Next calendar year |
| next.fiscal\_year | Next fiscal year |
| next.quarter | Next quarter |
| next.week | Next week |
| previous\_2.month | Previous 2 calendar months |
| previous\_2.year | Previous 2 calendar years |
| previous\_2.day | Previous 2 days |
| previous\_2.quarter | Previous 2 quarters |
| previous\_2.week | Previous 2 weeks |
| previous.month | Previous calendar month |
| previous.year | Previous calendar year |
| previous.fiscal\_year | Previous fiscal year |
| previous.quarter | Previous quarter |
| previous.week | Previous week |
| previous\_before.quarter | Quarter prior to previous quarter |
| this.month | This calendar month |
| this.year | This calendar year |
| this.fiscal\_year | This fiscal year |
| this.quarter | This quarter |
| this.week | This week |
| less.month | To end of current calendar month |
| less.year | To end of current calendar year |
| less.quarter | To end of current quarter |
| less.week | To end of current week |
| earlier.month | To end of previous calendar month |
| earlier.year | To end of previous calendar year |
| earlier.quarter | To end of previous quarter |
| earlier.week | To end of previous week |
| earlier.day | To end of yesterday |
| this.day | Today |
| starting.day | Tomorrow |
| previous\_before.week | Week prior to previous week |
| previous\_before.year | Year prior to previous calendar year |
| previous.day | Yesterday |

## Adding new filters

The code for some of the patterns supports the addition of more filters
(via the api or the url civicrm/admin/options/relative_date_filters)

Making other patterns more flexible is generally 'patch-welcome' - the hardest
part is the non-code part, figuring out what the definition is and how it relates
to the other patterns.

### ending

The trick to the 'ending' prefix is that it is a 'count backwards from now' type filter.
If you are in the middle of a month and you use 'ending' it will start from the middle of
the relevant month (if it's the 15th today then it would start from the 16th of the month)

Additional filters can be added with the syntax (where 3 can be any number you choose)
ending_3.day - Last 3 days, including today
ending_3.week - Last 3 weeks, including today, equivalent to ending_21.day
ending_3.month - Last 3 months, including today, e.g if today is 25 Dec 2021 then from 26 Sep 2021)
ending_3.quarter - Last 3 quarters, including today - equivalent to ending_9.month
ending_3.year - Last 3 years, including today (e.g if today is 25 Dec 2021 then from 26 Dec 2018)

### this

The 'this' term works in full date units - for example this_3.year starts from 1 Jan and ends
on 31 December. So if today is 25 December 2021 then this_3.year runs from 1 Jan 2019 to
31 December 2021.

this_3.day Last 3 days, including today - equivalent to ending_3.day
this_3.week from start of two weeks ago to end of this week (total of 3)
this_3.month from start of two months ago to end of this month (total of 3)
this_3.quarter from start of two quarters ago to end of this quarter (total of 3)
this_3.year from start of two years ago to end of this year (total of 3)
this_3.fiscal_year from start of 2 fiscal years ago to end of this fiscal year (total of 3 years)