# Dates

## Date Localization

Date and time conventions often vary by country and language. To configure the optimal conventions for your locale, use **Administer > Localization > Date Formats**.
The page includes several sections.

### Date Display

Dates display differently depending on the context.  An *accounting report* may list 1,000 donations in a data-table; to conserve space, the data-table uses a short
notation (eg `09/19/22`).  By contrast, an *event registration form* uses a long notation (eg `September 19th, 2022`) to maximize clarity.

CiviCRM defines ~7 common ways to format a date or time -- and each one can be tuned to local preferences. For example, in the United States, the typical configuration might look like this:

|Format Name|Example Configuration|Example Value|
|----|-----|-----|
| "Complete Date and Time" | `%B %E%f, %Y %l:%M %P` | September 18th, 2022 11:58 PM |
| "Complete Date"          | `%B %E%f, %Y`     | September 19th, 2022 |
| "Short Date"             | `%m/%d/%Y` | 09/18/2022 |
| "Month and Year"         | `%B %Y`  | September 2022 |
| "Time Only"              | `%l:%M %P`     | 1:34 PM |
| "Year Only"              | `%Y`     | 2022 |
| "Financial Batch"        | `%m/%d/%Y`| 09/19/2022 |

For a full listing of formatting codes, please see [PHP Manual: strftime()](https://www.php.net/manual/en/function.strftime.php).

### Date Input Fields

Some forms require the user to enter a date or time. The  **Date Input Format** and **Time Input Format** will adjust the data-entry screens.

### Calendar

Type in the day you want for the beginning of the week, and the month and and day you want for the start of the fiscal year.

## Date Preferences

By default, CiviCRM provides ranges for input on specific date fields. For instance, the default range for Activity Dates are 20 years prior to the current year all the way through to 10 years beyond the current year. If you would like to track activities that have occurred, say, 25 years ago then you would need to update this range to enable your end users to log these activities. To update these settings to the appropriate range go to **Administer > Customize Data and Screens > Date Preferences**. If you were to leave these settings as the default you will see an error such as this: Please enter a date between 01/01/1994 and 12/31/2024.

![Advanced Date Input Settings](../img/configure-localization-advanced-date-input-settings.png)
