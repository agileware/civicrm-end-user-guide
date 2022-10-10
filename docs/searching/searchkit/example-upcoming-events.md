# Example: Upcoming Events

When you click the **Event** tab from the toolbar and then select **Manage Events**, the default event overview looks like this:

![Default Magange Events screen](../../img/search-kit/default-manage-events.png)

Searchkit gives the option to create an alternative to the Manage Event overview screen that could be customized in many ways:

![upcoming event](../../img/search-kit/upcoming-events-final.png)

This Searchkit built event overview includes features such as:

 * a clickable event title that leads to the event's Info and Settings page
 * a list of speakers and hosts for each event
 * the number of registered/attended participants 
 * the number of cancellations/no-shows
 * the ability to click on the registered/attended or cancellations/no-shows numbers to view a list of participants with that status

This section will walk through how to create the above functionality step by step.

## Step 1: Create a New Search

Go to **Administer > Search > Searchkit** and click **New Search**.

![New Search empty screen](../../img/search-kit/new-search.png)

Then:

* fill in the name of the search (e.g. Upcoming Events)
* select Events from the **Search for** list
* in the **Where** section of the form, filter for upcoming events by using the drop-down fields to select **Event Start Date**, then **>=**, and finally **Now** (note that you can also **Pick a Date** or tailor the search with other options).

![Filled in search screen](../../img/search-kit/upcoming-events-step1.png)

!!! Tip
    Don't forget to **Save** your work.

Click **Search** to view the result.

## Step 2: Add Event Columns

By default we see the event ID and event title. For this example, we will also want to display the event start date.

You can do this by selecting that column from the list on the right-hand side.

![Add Event Start Date](../../img/search-kit/upcoming-events-add-start-date.png)

## Step 3: Add Participant Information

So far, we only have event information. We also want to show the host(s) and speaker(s) of the event. This information comes from the participants.

We will add this entity:

![Add participants](../../img/search-kit/upcoming-events-add-participants.png)

...with a filter on role in **Where**:

![Add where](../../img/search-kit/upcoming-events-add-participants-where.png)

We use Contains because a participant can have multiple roles, and these roles are stored in the participant role field.
The participant role should be either Speaker or Host.

Lastly, we add the entity Participant Contact to be able to show the name of the speakers and hosts.

The search now looks like this:

![Final search](../../img/search-kit/upcoming-events-add-participants-final-search.png)

## Step 4: Grouping on Event ID

If you run the search at this point, you will notice that an event is listed multiple times if you have more than one speaker or host. We can avoid this by grouping on event ID.

![Group by event id](../../img/search-kit/upcoming-events-add-participants-group-by.png)

The search will display the speakers and hosts in a comma-separated list thanks to a field transformation:

![List](../../img/search-kit/upcoming-events-add-participants-list.png)

## Step 5: Add the Number of Participants

Our next task is to add the number of participants.

To achieve this we need the field transformation **Count** on the field Participant ID.

But... if we do this right now, we count only the hosts and speakers because of the filter in **Where**.

The trick is to add Event Participants again as an entity:

![Attended participants count](../../img/search-kit/upcoming-events-add-participants-registered.png)

To display a count of the no-shows and cancellations, add another Event Participants entity.

![Attended participants count](../../img/search-kit/upcoming-events-add-participants-cancelled.png)

Add the Participant ID (2 and 3) columns by clicking **Add** on the upper right side of the search results display. Then, under **Field Transformations**, select **Count** and check the **Distinct** box next to the Participant ID (2 and 3) labels:

![counts](../../img/search-kit/upcoming-events-add-participants-count-distinct.png)

## Step 6: Change Column Names and Sort Order

To be able to change the column names, we need to first create a table display. Click the **Add...** button on the left side of the form (under **Compose Search**) and select **Table**.

![add display](../../img/search-kit/upcoming-events-add-display.png)

Give the display a name and add a Sort By:

![name and sort order](../../img/search-kit/upcoming-events-display-table.png)

Scroll down and give the columns a meaningful name in the Header fields.

The preview might look like this now:

![preview](../../img/search-kit/upcoming-events-display-table-renamed.png)

## Step 7: Make the Values Clickable

To make the number of participants clickable, we will add a **Link** to their respective overview page.

![links](../../img/search-kit/upcoming-events-display-table-links.png)

The link to enter for the registered/attended count is:

 * civicrm/event/search?reset=1&force=1&event=[id]&status=true

The link to enter for the cancelled/no-show count is:

 * civicrm/event/search?reset=1&force=1&event=[id]&status=false

If you want, you can add a **Link** for the event title as well:

 * civicrm/event/manage/settings?reset=1&action=update&id=[id]

![link event](../../img/search-kit/upcoming-events-display-table-link-event.png)

This will lead to the Info and Settings page of the event.

The final result looks like this:

![upcoming event](../../img/search-kit/upcoming-events-without-form.png)

## Step 8: Add Optional Filtering

We can add a form on top of the upcoming events list for optional filtering.

In the upper right corner of the search, we find a button to do that:

![add form](../../img/search-kit/upcoming-events-add-form.png)

This will bring us to the form builder. Give the form a name and a page link:

![add form name](../../img/search-kit/upcoming-events-form-name.png)

Click on the tab **Upcoming Events Table**. Drag and drop the form elements to the form layout pane:

![add form elements](../../img/search-kit/upcoming-events-add-form-elements.png)

You probably want to add a Container first in order to nicely layout the other form elements.

![add panel](../../img/search-kit/upcoming-events-form-panel.png)

## Step 9: Add the Overview in the Navigation Menu

In the previous step, we specified a page link for our form: **civicrm/upcoming-events**.

We can create a new navigation menu item with this link.

See **Administer > Customize Data and Screens > Navigation Menu**.

![upcoming event](../../img/search-kit/upcoming-events-menu.png)

As a result, your users have a convenient way to access the upcoming events:

![upcoming event](../../img/search-kit/upcoming-events-menu2.png)

This will lead to our finalized search form:

![upcoming event](../../img/search-kit/upcoming-events-final.png)





















