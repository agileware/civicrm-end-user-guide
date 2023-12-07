# With (Optional) / With (Required) / Without 

Provide a screenshot showing where on the SearchKit page this clause is.

## Description

When creating a new search, the first choice is the starting entity. The next step is to include zero or more additional entities if you need fields from them as additional columns, or perhaps to adjust the rows returned. For example, you might start with contacts and then add addresses. 

The additional entity's rows are joined to the existing rows from the starting entity and any other previously joined entities in one of three ways: `With (optional)` / `With (required)` / `Without`. 

Which option is chosen to join the entities affects how many and which rows are returned. Sometimes you might join to additional entities just in order to restrict the rows, such as getting just the contacts who have bought tickets for the Annual General Meeting, or all those who have not yet bought tickets.

`With (optional)` treats the new entities as optional. Even if there is not a match, the rows from the earlier entity or entities will still be returned in the results. Contacts With (optional) Contact Addresses will return a row for a Contact that has no addresses, and all of that row's Contact Addresses fields will be empty/NULL.

`With (required)` only returns rows in your search if there exists an additional entity for the earlier entity or entities in the search. For example, Contacts With (required) Contact Addresses will not return any rows for Contacts that do not have addresses, but does return a row for every combination of Contact and one of its addresses.

`Without` only returns rows where the earlier entity or entities have no matching row in the new entity. For example, Contacts Without Contact Addresses will return a row for each Contact that has no Contact Address.

Each additional entity you add to the search is 'joined' to the entities already selected. Your choice of 'With (optional)` / `With (required)` / `Without` determines if rows will be added to the search or removed. 


## Option Details

If the section being described has a long list of options that have a one sentence description in the UI then probably start by just listing all of those options in an unordered list.
