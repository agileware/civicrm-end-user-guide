# What is Search Kit?

Search Kit is new functionality which started as a new search interface to provide a more intuitive and powerful search than older CiviCRM search tools and in later versions of CiviCRM opens up new roads to manage your data in CiviCRM.

Searches can be saved, have any number of unique displays on their own or connected to the dashboard or contact screen. Searches can have exposed filters for easy filtering and even be connected to a Smart Group. And you can use Search Kit for your own entities and with an additional extension even create your own entities. So although Search Kit is part of the Searching and Reporting section of this Guide it might some day end up with a Guide of its own as the possibilities evolve.

It ships as an extension which you can enable on the Extensions screen from 5.29 onwards. Once enabled it can be found under the menu **Search > Search Kit**.

!!! note
    Search Kit ships as an extension as part of our strategy of
    putting significant functionality leaps into extensions rather than
    overhauling existing code. This allows us to demarcate rapidly evolving
    code and to keep long-standing code more stable. People can opt into
    the extension or not. However, it is maintained as part of core against
    the specific release it ships with (as it is closely tied to API v4
    functionality).

## Search Kit components

There are always 2 and potentially 3 components to Search Kit: search screen, displays and forms. Depending on what you are doing you may not use all 3.

1. The Search screen (or Compose Search)
   This is where the search criteria (what you are searching for so for example Events and Participants) and available fields are configured.
2. Displays
   Displays is where you decide and define how you are going to present your search results. One search defined in the Compose Search section can have more displays presenting the results in a different way. Search displays
   currently available are table views, list views, grid views, or Smart Groups.
3. Forms
   Forms (only in the screen if you have enabled the [Form Builder](../../the-user-interface/creating-new-forms.md) extension that is shipped with CiviCRM core) allow you to create a form to present your search results on. 

## How to create searches and displays

The best way to find out how to create searches and displays and what options are available is by reading the examples provided in this chapter.
