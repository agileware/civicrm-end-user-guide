# Example Soft Credit Search and Display

In this example I am going to create a Soft Credit search and a table display. 

!!! Note "A little background on Soft Credits"
    Soft Credits in CiviCRM are a way to keep track of someone you should also thank for a contribution other than the donor. For example, if I ask people to donate for my birthday and John Doe contributes 25 euro I can get recognition for that with a soft credit. For more information read the [Soft Credits section](../../contributions/soft-credits.md).

In this search I want to combine data from the contact that has the Soft Credit with data from the contact that actually contributed with data from the contribution. It should show me who my best contribution sollicitors are :-). The outcome will be something like this:\

![Soft Credits Overview](../../img/search-kit/soft-credit-search-result.png)

## Starting from the Saved Searches

First step is to navigate to Search Kit from the Search menu. I will then get a page with saved searches like this:

![Saved Searches page](../../img/search-kit/soft-credit-saved-searches.png)

On this page I get an overview of the existing searches. As you can see my Soft Credit example is already on the list but I am now going to create a new one step by step. First step is to click on the **New Search** button.

## Creating the Search

Once I clicked the **New Search** button I get an empty form where I can create the search:

![Create New Search](../../img/search-kit/soft-credit-empty-new-search.png)

On the left you see a text box with _Untitled Search_, where you can and should enter the name of your search. So I will enter _Soft Credit Example Search_.

Below that name you will see a selection box for _tags_. You can add a tag to a search which will allow you to categorize your searches, for example all Fundraising searches.

Right under that box is an _Add_ selection box, which we will ignore for now but will discuss in the [Adding a display](#adding-a-display) section of this chapter.

The next step is to select the entities that we want data from.

### Selecting entities

At the middle top of the form we can choose what entity to search for. Initially it will have the value _Contacts_:

![Search for entity](../../img/search-kit/soft-credit-entity-start.png)

You can choose what entities you want and the list is quite extensive. 

I am initially going to select Contribution Soft Credits entity. This will give me the contact that has the Soft Credit, the ID of the contribution the Soft Credit is linked to, the amount of the Soft Credit (which can be different from the contribution amount) and the type of Soft Credit. 

But I also want to include information about the actual contribution and about the contact that made the contribution so I need to add those entities too.

So I will use the box that says _With (optional)_ to specify the additional entities I want. Search Kit will work it out by itself how to link those entities, so it will know it needs to use the contribution ID to link to the Contribution and the contact ID in the contribution to link to Contact.

I can add additional conditions, so in this example I will only want to use the contributions that have the financial type Donation because I do not want to show payments for memberships or events.

There is also a box with _Where_. Here I can add selection criteria for my search. In this case I am only interested in contributions between 1 Jan 2021 and 30 April 2022 so I have entered these criteria.

The complete selection of my entities looks like this:

![Entities](../../img/search-kit/soft-credit-entities.png)

If you are trying this yourself whilst reading the documentation, you will probably notice that there are is also a _Group By_ box. 
We are not going to use that in this example. You have the option here to select a field on which the results will be grouped. If for example you would select _Contact Display Name_ here it would group the results for each Soft Credit contact.

In the next step I am going to select the fields I want to see on my search.

### Selecting the fields

At the bottom of the form I can select what fields I am going to show as the result of my search. Initially there will probably just be an ID and sometimes a name selected so it will look like this:

![Initial fields](../../img/search-kit/soft-credit-empty-fields.png)

If I press the _Search_ button above the field names it will actually display the data:

![Initial fields with data](../../img/search-kit/soft-credit-empty-fields-search.png)

Next to the _Search_ button you see an _Action_ box. In this case you can use it to download your search results in a CSV file. This is the standard action with your search, if you want to you can switch it off on your display as I will show later.

On the right side of the form I have a list where I can select fields from the selected entities. I can add those fields to my search:

![Adding fields](../../img/search-kit/soft-credit-add-fields.png)

In my example I am going to remove the Soft Credit ID, keep the name of the Soft Credit contact and add:
* the soft credit amount
* the soft credit type
* the name of the contributing contact
* the contribution total amount
* the contribution date
* the contribution source
* the contribution status
* the contribution payment method

When I have selected them all and pressed _Search_ again my results will be:

![Fields added](../../img/search-kit/soft-credit-fields.png)

In the next step I am going to transform some of those fields.

### Transforming fields

Just below the entities section you see a section with the caption _Field Transformations_. If you open this you will see a list of the fields that are on your search with a box where you can select the transformation for that field.

![Field Transformations](../../img/search-kit/soft-credit-empty-transformations.png)

For each field I can select some transformations. Have a play yourself to check what is going to happen. In this example I am going to make the name of the contribution contact upper case because I want them to stand out. I am also going to select the _date only_ for the contribution receive date as I am not interested in the time.

![My transformations](../../img/search-kit/soft-credit-transformations.png)

If I press on the _Search_ button I can check the results of my transformations:

![Result after transformation](../../img/search-kit/soft-credit-transform-result.png)

### Having a look at the query

Just below the _Field Transformations_ section you will see a section _Query Info_. This section will show information about the technical translation of what we selected as entities and fields. It is very interesting for developers but can be ignored if you are not technically oriented. 

In my example it will show this:

```
{
  "version": 4,
  "select": [
    "ContributionSoft_Contribution_contribution_id_01_Contribution_Contact_contact_id_01.display_name",
    "amount",
    "soft_credit_type_id:label",
    "UPPER(ContributionSoft_Contribution_contribution_id_01.contact_id.display_name) AS UPPER_ContributionSoft_Contribution_contribution_id_01_contact_id_display_name",
    "ContributionSoft_Contribution_contribution_id_01.total_amount",
    "DATE(ContributionSoft_Contribution_contribution_id_01.receive_date) AS DATE_ContributionSoft_Contribution_contribution_id_01_receive_date",
    "ContributionSoft_Contribution_contribution_id_01.source",
    "ContributionSoft_Contribution_contribution_id_01.contribution_status_id:label",
    "ContributionSoft_Contribution_contribution_id_01.payment_instrument_id:label"
  ],
  "orderBy": [],
  "where": [
    [
      "ContributionSoft_Contribution_contribution_id_01.receive_date",
      "BETWEEN",
      [
        "2021-01-01 11:09:00",
        "2022-04-30"
      ]
    ]
  ],
  "groupBy": [],
  "join": [
    [
      "Contribution AS ContributionSoft_Contribution_contribution_id_01",
      "LEFT",
      [
        "contribution_id",
        "=",
        "ContributionSoft_Contribution_contribution_id_01.id"
      ],
      [
        "ContributionSoft_Contribution_contribution_id_01.financial_type_id:name",
        "=",
        "\"Donation\""
      ]
    ],
    [
      "Contact AS ContributionSoft_Contribution_contribution_id_01_Contribution_Contact_contact_id_01",
      "LEFT",
      [
        "ContributionSoft_Contribution_contribution_id_01.contact_id",
        "=",
        "ContributionSoft_Contribution_contribution_id_01_Contribution_Contact_contact_id_01.id"
      ]
    ]
  ],
  "having": []
}
```
### View results

During the building of my search and once it his completed I can use the _View Results_ button to see what the results are:

![View results](../../img/search-kit/soft-credit-view-results.png)

## Adding a display

I have specified what I want to search for and what fields I want to see. So now I can add a display which shows my results. That can be added as a CiviCRM menu option. I am going to do that using the select box with the _Add_ caption on the left hand side of the form:

![Add display](../../img/search-kit/soft-credit-add-display.png)

As you can see there are different types of displays that can be added:
* a smart group which will create a smart group of my search results
* a table which shows an overview in table form of my results
* a list list which will show a (vertical) list of my results
* a grid which will show an unformatted grid of my search results

The table option is most common and what I will need in my example.
So I am going to select _Table_ and will then see a form like this:

![New table](../../img/search-kit/soft-credit-empty-table.png)

First of all I am going to name my table with results at the top of the form and press _Save_.

!!! Tip
    Do not forget to press _Save_ regularly when building your search or table so you do not lose stuff....

In the section _Sort by_ I can select what fields I want my table sorted by. In this example on Soft Credit contact name, contribution contact name and receive date in descending order:

![Sort by](../../img/search-kit/soft-credit-sort.png)

In the section just below that I can specify if I want to allow an _actions_ box on my table, how many results I want to show, the table style, what text to show if I have no results and if the search should be run automatically.
In my example I have changed the text for no results and left the rest with default values:

![Actions and such](../../img/search-kit/soft-credit-enable-actions.png)

Next I see a list of all the fields that are on my search. I can drag them around and change the order by clicking and holding the handle and moving it around:

![Column handle](../../img/search-kit/soft-credit-column-handle.png)

To remove a column I can click on the remove icon:

![Remove column](../../img/search-kit/soft-credit-column-remove.png)

For each column I can change the heading, change the alignment, if inline-edit is allowed etc.

If I want to I can click on the _Add_ button at the top of the column list. From the list I can add a column that is in my defined search results but not yet on my table. Or add a link, a button, a menu of a bit of custom code. In my example I want to add a little menu that allows:
* viewing the soft credit contact
* viewing the contribution contact
* viewing the contribution

First I have clicked on the _Add_ button and selected the menu option:

![Add menu](../../img/search-kit/soft-credit-add-menu.png)

This will add a new menu column at the bottom of my list. I have edited this menu to look like this:

![My menu](../../img/search-kit/soft-credit-menu.png)

If you click on the _add_ within the menu column you will get a few suggestions based on the entities you have selected and luckily they include all the ones I want for this example.

At this point, also changing the headers, I am really content with my table. I click on _View Results_ to see my final table:

![Final table](../../img/search-kit/soft-credit-final.png)

Now I can add a menu option for my table by copying the URL in my browser:

![Copy url](../../img/search-kit/soft-credit-copy-url.png)

and adding it to the CiviCRM menu.
I will do this by navigating to Administer>Customize Data and Screens>Navigation Menu and then clicking on the _Add Menu Item_ button:

![New menu item](../../img/search-kit/soft-credit-add-menu-option.png)

I will enter all the options and add the URL (at least the part starting with _civicrm/_)

![Add menu item](../../img/search-kit/soft-credit-new-menu-item.png)
