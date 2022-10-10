# What is Searchkit?

Searchkit is new functionality which started as a new search interface to provide a more intuitive and powerful search than older CiviCRM search tools and in later versions of CiviCRM opens up new roads to manage your data in CiviCRM.

Searches can be saved, have any number of unique displays on their own or connected to the dashboard or contact screen. Searches can have exposed filters for easy filtering and even be connected to a Smart Group. And you can use Searchkit for your own entities and with an additional extension even create your own entities. So although Searchkit is part of the Searching and Reporting section of this Guide it might some day end up with a Guide of its own as the possibilities evolve.

It ships as an extension which you can enable on the Extensions screen from 5.29 onwards. Once enabled it can be found under the menu **Search > Searchkit**.

!!! note
    Searchkit ships as an extension as part of our strategy of
    putting significant functionality leaps into extensions rather than
    overhauling existing code. This allows us to demarcate rapidly evolving
    code and to keep long-standing code more stable. People can opt into
    the extension or not. However, it is maintained as part of core against
    the specific release it ships with (as it is closely tied to API v4
    functionality).

## Searchkit components

There are always 2 and potentially 3 components to Searchkit: search screen, displays and forms. Depending on what you are doing you may not use all 3.

1. The Search screen (or Compose Search): is where the search criteria (what you are searching for so for example Events and Participants) and available fields are configured.
2. Displays:  is where you decide and define how you are going to present your search results. One search defined in the Compose Search section can have more displays presenting the results in a different way. Search displays
   currently available are table views, list views, grid views, or Smart Groups.
3. Forms: (only in the screen if you have enabled the [Form Builder](../../the-user-interface/creating-new-forms.md) is an extension that is shipped with CiviCRM core) allow you to create a form to present your search results on. 

## How to create searches and displays

The best way to find out how to create searches and displays and what options are available is by reading the examples provided in this chapter.

## Filtering on search results by the url

You can add filters to the url by which you access a search and it will filter the results.  The syntax looks like field=value - e.g to filter to cash payments `civicrm/search#/my-search-url?payment_instrument_id:label=Cash` (To get the syntax for a field in the search display click on 'rewrite' to see the field name. ) 

A few notes about URL filters:

1) The field needs to be exposed in the search (but not necessarily the search display) to be available for filtering.
2) If the field is already filtered (e.g receive date before this week) then the URL filter will further narrow down the results rather than replace the existing filter.
3) When the field has a `:` in it that indicates that the field is a 'pseudoconstant'. The underlying database value is generally
a number which maps to a name and label. In this case the database field `payment_instrument_id` is a number. In some cases we know the number instead, in which case we could use `payment_instrument_id=1` in our URL or `payment_instrument_id:name=Cash`. This variant is more useful for implementers who work with multiple sites.
4) For dates we can use the following formats
   - `receive_date=2021-09-23`
   - `receive_date=20210923`
   - `receive_date=20210923234040` (i.e. time is 23:40:40)
   - `receive_date=this.month` (See [the list](../relative-date-formats.md))

