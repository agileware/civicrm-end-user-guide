# Introduction

This chapter covers different ways to find information you've stored in
CiviCRM. 

We will start off with some simple searches and then move on to more
advanced techniques. CiviCRM beginners should be familiar with
Quick search, Advanced Search and the component searches. More advanced
users should also look at [SearchKit](../searching/searchkit/what-is-searchkit.md) reports, and custom searches.

## Overview
In this introduction we will discuss at various level of detail:

* **Quick search** - how to quickly search for contacts.
* **Advanced search** - how to really dig deep for contacts with lots of search possibilities.
* **Full-text search** - how to search for something in all the available text fields in the database.
* **Component search** - on searching within specific component entities like events, memberships, cases, contributions etc.
* **Custom searches** - using the available custom made searches that can be from CiviCRM core or from one or more of your specific extensions.
* **Search actions** - what you can do with the results of your search (or sometimes report).
* **The contact summary pop** - what you can see and change in the popup when hovering over a contact icon in your search results.
* **The wildcard** - using "%" or "%_%" in your searches as a wildcard.
* **Case sensitivity** - what you can do with upper or lower case in your search.
* **Default number of rows** - how many results are returned in your searches and how you can change that number.
* **SearchKit** - a brief link to the [SearchKit](../searching/searchkit/what-is-searchkit.md) functionality.

## Searching and reporting

There are three main reasons to search:

-   To find a specific contact: the Quick search box can find contacts
    by name, email address or a variety of other characteristics
-   To perform an action on a contact or contacts that meet certain
    criteria. For example, you might want to find all contacts in
    the advisory group in order to invite them to a meeting, find all
    those whose memberships have recently expired to send a renewal
    reminder, or find all contacts aged under 25 in a specific location
    to send them an email about an upcoming event nearby
-   For ad-hoc reporting

As a form of ad-hoc reporting, searching is often useful but does have
limitations. For example, you can't group results by particular
criteria, summarize, or easily produce graphs of the results. For more
advanced reporting, see the [CiviReport](../reporting/what-is-civireport.md) section.

## Quick search

![Quicksearch](../img/the-user-interface/searching/quicksearch.png)

The easiest way to find a specific contact is to use the Quick search box that appears in the navigation menu at the top left of the screen. You may choose to search by one of several criteria. The criteria can be modified by going to **Administer > Customize Data and Screens > Search Preferences**. On the *Search Preferences* page, options are available to customize CiviCRM's Quick search to hide contacts' basic fields that are not normally used in a Quick search and to add custom field options.

Once you click in the Quick search box, you can start typing immediately to use the default Name/Email search or you can click again to expose several other criteria in a dropdown selection list. Contacts that match the phrase you enter will appear in a dropdown list below the box. For example, if you are searching with Name/Email and you have left
automatic wildcard enabled via *Search Preferences*, entering "peter" will find:

-   people who's first or last name is **Peter**
-   people who have Peter appearing as part of their name, e.g. Mary
    **Peter**son
-   people who have Peter as part of their email address, e.g.
    blue**peter**@gmail.com  
-   organisations with Peter in their name, e.g. Al**peter**
    Community Centre.

You often don't need to type the full name of the person - just the first few letters.  However, if you don't see the contact you are looking for, either refine the search by typing more characters, or hit the Return key to convert your search into an Advanced Search.

Quick search displays up to 10 results (by default). You can change the number of results returned from the *Search Preferences* screen described above by changing the *Autocomplete Results* setting.

CiviCRM also allows for the collection of a nickname when entering new contacts.  For example, "Joe" can be a nickname for "Joseph" and "IBM" can be a nickname for "International Business Machines".  When you first install CiviCRM you will find "Joseph" when searching for "Joe" and you'll find "International Business Machines" when searching for "IBM".

You can change this behavior from the *Search Preferences* screen described above by changing the *Include Nickname* setting to *yes*.

!!! note
    If you search by **phone** then you will need to enter the digits of 
    the phone number without any formatting. The **phone** search is done 
    against a field that consists only of digits with all non-numeric 
    characters stripped out.
    
!!! tip 
    If you want to search by **first** and **last** name, use the format 
    "Lastname, Firstname", not "Firstname Lastname".  
    For example, "Peterson, Mary" not "Mary Peterson".

## Advanced search
![Screen shot of advanced search](../img/the-user-interface/searching/user-interface-advanced-search-main-screen.png)

Advanced search allows you to search across all the information you have
about your contacts. For example, you could find "all contacts in
Venezuela" or "all advisory group members". If you specify two or more
categories of information, the search displays every contact that
matches all the categories. For instance, you can combine the two
criteria just mentioned to find "all advisory group members in
Venezuela".

The Advanced search screen is accessible from the navigation menu
**Search > Advanced Search**. On this screen, search criteria are
grouped into sections which refer to different types of data that you
can search on, such as address data, notes and information from
components such as Contributions or Events. Each group of criteria is
shown as a blue bar (known as an "accordion" because it expands when you
click on it). For example, if you want to search for all people in your
database from 16 to 18 years old, click on the **Demographics** accordion.
When it opens, you can specify the birth date range you are interested
in.

#### Display Settings For Results

![Screen shot of Display Results As](../img/the-user-interface/searching/user-interface-display-results-as.png)

Advanced Search returns your results as Contact records by default.
However, you may want to get another record type instead. For example,
you may want to search on the Membership renewal activity to find
everyone who renewed their membership last week then display the results
as Memberships so that you can export name, address and Membership
expiration date to create and then post out membership cards to those
contacts. Simply select the record type you want from the **Display Results As** dropdown.

#### Views for Display Contacts

![Screen shot of Display Contacts](../img/the-user-interface/searching/user-interface-new-contact-view-profile.png)

Advanced search allows you to change the columns displayed in your
search results. The default columns are Name, Street Address, City,
State, Postal Code, Country, Email and Phone. If you want to display a
different set of columns (perhaps to include a custom field or remove a
column you don't need), create a Profile with the Search Views option
selected. Make sure that the fields in this Profile are set to "Expose
Publicly and for Listings" visibility, and are marked as Results Columns.
(For more information about creating Profiles, which are described in
detail in the Profiles chapter in the Configuration section.)

For example you may want to include columns for Gender and Date of Birth, while eliminating Country.
Create a profile that includes birth date, gender and address fields.

![Screen shot of Search View setting in a profile](../img/the-user-interface/searching/user-interface-profile-search-view-setting.png)

![Screen shot of Visibility setting in a profile](../img/the-user-interface/searching/user-interface-profile-search-view-setting-2.png)

![Screen shot of a profile](../img/the-user-interface/searching/user-interface-new-contact-view-profile.png)

Read more about creating profiles in the [Profiles](../organising-your-data/profiles.md) section of the chapter
on *Organising Your Data*.

Combining this feature with the "Batch Update via Profile" action
provides a powerful method of viewing and updating a specific set of
fields across a batch of contact records.

### Search settings
The **Search Operator** determines whether your criteria are combined with AND statements, or combined with OR statements. For example, you may want to find all individuals who are in the Volunteers group AND who have a Volunteer Training activity recorded for them. In this case use the AND operator. If you need to find everyone who is in the Volunteers group OR has a Volunteer Training activity recorded, use the OR operator.

The **Search in Trash** allows you to search contacts that have been deleted but not deleted permanently. When a contact is deleted, the contact and all related data are moved to trash. Only users with the relevant permission will be able to search in trash and will be able to restore the contact from trash.

![Screen shot of Search in Trash](../img/the-user-interface/searching/user-interface-search-in-trash.png)

### The Date Range Filter

![Screen shot of Date Range Filter](../img/the-user-interface/searching/user-interface-date-filter.png)

Most component searches include a date range filter. The images below
show examples of both:

-   by using an absolute date range, e.g. "1st Jan 2010" to "31 July
    2010"
-   by using a relative date range, e.g. "Previous week"

Relative date ranges are especially useful for searches that you would
like to then save as Smart Groups (automatically populated groups that
are configured to include contacts that share a certain set of
characteristics or activities). For more information see the [Groups and
tags](../organising-your-data/groups-and-tags.md) section in the *Organising your data* chapter.

![Screen shot of Relative Date Range Filter](../img/the-user-interface/searching/user-interface-date-filter-relative.png)

For example you may want to use a relative date range search to find:

-   Contacts who have contributed in the last 7 days (Relative date
    range - "From 1 Week ago")
-   This (financial) year's registered Event Participants (Relative date
    range - "This Year")
-   Contacts who are a certain age


Relative dates filters based on the time interval "week" assume that Sunday is the first day of the week.   This is not true in all countries, for example Europe and many countries in Asia/Pacific region consider Monday to be the first day of the week. To set which day is the first day of the week, you need to go to **Administer > Localization > Date Format**.

![Screen shot of how to change the first day of the week](../img/the-user-interface/searching/user-interface-searching-week-begins.png)


#### Combining search criteria

Different criteria are combined by "ANDing" them. For example, if you
select the tag "major donor" and the country "Mexico", the search will
return major donors from Mexico. The search will not return major
donors who are *not* from Mexico, nor those from Mexico who are *not*
major donors.

You can change the default search operator from AND to OR in the Search Settings.

Within criteria groups that allow you to check boxes for more than one
value, these options are also combined by "ANDing". For example, you
can search for contacts whose Preferred Communication Method is both
Email *AND* SMS.

With fields that allow you to select more than one value from a dropdown list,
the values are always combined with OR. For example, you could find contacts
that live in Alaska or in Arizona.

![advanced search address selected](../img/the-user-interface/searching/user-interface-advanced-search-address-selected.png)

If you expand one of the dropdown sections, and make selections, as shown above,  a cross appears at the right end of the header, indicating that this panel is being used in the search. If you no longer wish to use Address Fields as a part of the search, it is not enough just to close the panel. You must click the cross on the header.

#### Limitations of Advanced Search

The Advanced Search is an effective way to search for many things in CiviCRM. However, there is an issue with searches where Contacts are the client in more than one Case, and they are engaged in the same Activity Type in each of these Cases. The Advanced Search is currently not able to filter these Activities correctly by Case Type. This issue is expected to be resolved in the near future. 

## Full-text Search

You can use this to search for text values all fields of the database.
This is particularly useful, for example, if you can remember specific
words that you have used but can't remember where you have put them. For
example, lets say that you recorded an activity with a contact and added
specific words to the description but have now forgot the contact's
name. You can use Full text search to find the contact and activity by
words that you remember from the description.

## Component searches

Most CiviCRM components offer a search on the data they maintain, such
as **Find contributions**, **Find members**, etc. These forms work in a similar
way to **Advanced Search** but return rows of the main objects associated
with the components, instead of contacts. **Find Members** returns
memberships, **Find Participants** shows event registrations, **Find
Contributions** returns contributions and so on.

Each component search has its own Action list. See the *Component*
chapters for more details.

Note that you can also use the Advanced Search in conjunction with
**Display Results As** to search for component objects based on criteria
available in Advanced earch. For example, you could find all event
attendances from contacts that are also members.

## The 'search-action' workflow

After you retrieve your search results, you can perform a number of
actions. An Actions box appears above the results. You can select either
all records or specific records, then carry out an action with the
selected records. Different actions are covered in more detail in the
chapter on Everyday Tasks.

![Screen shot of Action Dropdown](../img/the-user-interface/searching/user-interface-searching-actions-dropdown.png)

Some of the most commonly used actions are Add Contacts to Group, Export
Contacts, Map Contacts, and creating and printing Mailing Labels. (To
use Map Contacts, you will need to configure Mapping and Geocoding. You
can read more about this in the *Installation* chapter of the
*Configuration* section of this manual).

For example, to send email to a selected number of contacts, mark the
contacts you are interested in and then select **Send Email to Contacts** in
the dropdown list of actions.

## The contact summary pop-up

You can see a pop-up box with detailed information for any contact
listed in your search results by hovering over the contact icon in the
left column, as shown below. You can adjust the fields shown in this
"pop-up view" by modifying the fields included in the "Summary Overlay"
profile (**Administer** > **Customize Data and Screens** >
**Profiles**).

![Screen shot of Contact Summary pop-up](../img/the-user-interface/searching/user-interface-searching-summary-overlay.png)

## The wildcard (%)

Understanding wildcards greatly expands your search options. A wildcard
represents any character (letter, numeral or punctuation mark). In
CiviCRM, the wildcard is represented by the % symbol (you may be
familiar with other symbols such as * from other applications). It is
most easily understood through examples.

Suppose that somebody asked you to find a contact with a first name
similar to "Michael", but possible something different such as
"Michelle" or "Michał". If you search for "Mich%" you will find all
these variations, including a contact who is supposed to be named
"Michael" but whose name was misspelled as "Micheal". Wildcards can be
used before, after, or even within words. For example, searching on
'Mich%el' will exclude "Michał" and "Micheal" but still find "Michelle"
and "Michael".  

However, using % by itself can produce unexpected results for data where the value in the database is 'empty' (as opposed to NULL). Using a single % will return results for empty values. To avoid these results, eg if you are searching "any record which has any data in this field" usw %_% instead. This will return results only where there is at least a single character, and will ignore all empty (as well as NULL) results.

## Case sensitivity

Note that when you search for character strings, the search is not
case-sensitive. For example, if you search for 'brooklyn', the search
will return strings with capitalised letters if the string exists, e.g.
'Brooklyn' or 'BROOKLYN'. Entering "mi%el" in lowercase will also find
contacts with an upper case 'M' in their name.

## Default number of rows to be returned.

In CiviCRM Advanced Searches and in CiviCRM reports the number of rows displayed on the screen has by default been 50 previously.
As of CiviCRM version 5.39 System Administrators can under **Administer** > **Customize Data and Screens** > **Search Preferences** 
change the number of rows to be outputted on the screen. You should not set too high a number as the higher the number, the slower the screen will be 
to load.

## SearchKit
**SearchKit** is more powerful than Advanced Search but requires more technical knowledge. It is suitable for site builders and power users, and is covered in the [SearchKit](../searching/searchkit/what-is-searchkit.md) section.
