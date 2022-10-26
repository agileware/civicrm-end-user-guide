# Relative date filters

The list of relative date filters below ship with CiviCRM. You can see the
list on your site at the URL `civicrm/admin/options/relative_date_filters`.
It is possible to add some additional ones within fairly tight constraints
(this is explained after the list)

| value | Means |Defines|
| ---- | ---- |---- |
| `current.month` | Current calendar month to-date |start and end|
| `current.year` | Current calendar year to-date |start and end|
| `current.quarter` | Current quarter to-date |start and end|
| `current.week` | Current week to-date |start and end|
| `previous_before.day` | Day prior to yesterday |start and end|
| `greater_previous.month` | From end of previous calendar month |start|
| `greater_previous.year` | From end of previous calendar year |start|
| `greater_previous.quarter` | From end of previous quarter |start|
| `greater_previous.week` | From end of previous week |start|
| `greater.month` | From start of current calendar month |start|
| `greater.year` | From start of current calendar year |start|
| `greater.day` | From start of current day |start|
| `greater.quarter` | From start of current quarter |start|
| `greater.week` | From start of current week |start|
| `ending.year` | Last 12 months including today |start and end (now)|
| `ending_2.year` | Last 2 years including today |start and end (now)|
| `ending_3.year` | Last 3 years including today |start and end (now)|
| `ending_30.day` | Last 30 days including today |start and end (now)|
| `ending_60.day` | Last 60 days including today |start and end (now)|
| `ending.week` | Last 7 days including today |start and end (now)|
| `ending_90.day` | Last 90 days including today |start and end (now)|
| `previous_before.month` | Month prior to previous calendar month |start and end|
| `starting.year` | Next 12 months including today |start (now) and end|
| `starting.month` | Next 30 days including today |start (now) and end|
| `starting_2.month` | Next 60 days including today |start (now) and end|
| `starting.week` | Next 7 days including today |start (now) and end|
| `starting.quarter` | Next 90 days including today |start (now) and end|
| `next.month` | Next calendar month |start and end|
| `next.year` | Next calendar year |start and end|
| `next.fiscal_year` | Next fiscal year |start and end|
| `next.quarter` | Next quarter |start and end|
| `next.week` | Next week |start and end|
| `previous_2.month` | Previous 2 calendar months |start and end|
| `previous_2.year` | Previous 2 calendar years |start and end|
| `previous_2.fiscal_year` | Previous 2 fiscal years |start and end|
| `previous_2.day` | Previous 2 days |start and end|
| `previous_2.quarter` | Previous 2 quarters |start and end|
| `previous_2.week` | Previous 2 weeks |start and end|
| `previous.month` | Previous calendar month |start and end|
| `previous.year` | Previous calendar year |start and end|
| `previous.fiscal_year` | Previous fiscal year |start and end|
| `previous.quarter` | Previous quarter |start and end|
| `previous.week` | Previous week |start and end|
| `previous_before.quarter` | Quarter prior to previous quarter |start and end|
| `this.month` | This calendar month |start and end|
| `this.year` | This calendar year |start and end|
| `this.fiscal_year` | This fiscal year |start and end|
| `this.quarter` | This quarter |start and end|
| `this.week` | This week |start and end|
| `less.month` | To end of current calendar month |end|
| `less.year` | To end of current calendar year |end|
| `less.quarter` | To end of current quarter |end|
| `less.week` | To end of current week |end|
| `earlier.month` | To end of previous calendar month |end|
| `earlier.year` | To end of previous calendar year |end|
| `earlier.quarter` | To end of previous quarter |end|
| `earlier.week` | To end of previous week |end|
| `earlier.day` | To end of yesterday |end|
| `this.day` | Today |start and end|
| `starting.day` | Tomorrow |start and end|
| `previous_before.week` | Week prior to previous week |start and end|
| `previous_before.year` | Year prior to previous calendar year |start and end|
| `previous_before.fiscal_year` | Fiscal year prior to previous fiscal year |start and end|
| `previous.day` | Yesterday |start and end|

## Adding new filters

The code for some of the patterns supports the addition of more filters
(via the api or the URL `civicrm/admin/options/relative_date_filters`)

Making other patterns more flexible is generally 'patch-welcome' - the hardest
part is the non-code part, figuring out what the definition is and how it relates
to the other patterns.

### ending

The trick to the `ending` prefix is that it is a 'count backwards from now' type filter.
If you are in the middle of a month and you use `ending` it will start from the middle of
the relevant month (if it's the 15th today then it would start from the 16th of the month)

Additional filters can be added with the syntax (where 3 can be any number you choose)

- `ending_3.day` - Last 3 days, including today
- `ending_3.week` - Last 3 weeks, including today, equivalent to `ending_21.day`
- `ending_3.month` - Last 3 months, including today, e.g if today is 25 Dec 2021 then from 26 Sep 2021)
- `ending_3.quarter` - Last 3 quarters, including today - equivalent to `ending_9.month`
- `ending_3.year` - Last 3 years, including today (e.g if today is 25 Dec 2021 then from 26 Dec 2018)

### this

The `this` term works in full date units - for example `this_3.year` starts from 1 Jan and ends
on 31 December. So if today is 25 December 2021 then `this_3.year` runs from 1 Jan 2019 to
31 December 2021.


- `this_3.day` - Last 3 days, including today - equivalent to ending_3.day
- `this_3.week` - From start of two weeks ago to end of this week (total of 3)
- `this_3.month` - From start of two months ago to end of this month (total of 3)
- `this_3.quarter` - From start of two quarters ago to end of this quarter (total of 3)
- `this_3.year` - From start of two years ago to end of this year (total of 3)
- `this_3.fiscal_year` - From start of 2 fiscal years ago to end of this fiscal year (total of 3 years)
