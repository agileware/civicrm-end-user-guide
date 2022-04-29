# Case: Creating a public Membership List

There are many use cases where you'd like to show structured data from CiviCRM on a public page of your website. Let's say you are using CiviCRM as a membership organization and you are having several membership levels. Now wouldn't it be nice to have a filterable or searchable list of them with live data from CiviCRM exposed on your website? With the help of Search Kit and Form Builder it is an easy thing to do this. To show how we will create a Logo Grid with tooltips and links to our member's websites that can be filtered by membership types:

![Grid showing filterable Memberships](../../img/search-kit/membership-listing-goal.png)

Let's build this step by step.

## Step 1: Create a New Search and define the Data Sources you need

Go to **Administer > Search > Search Kit** and click **New Search**.

Then:

* fill in the name of the search (e.g. Our Members)
* select 'Memberships' from the **Search for** list
* add one **With** for 'Membership Contact' as we need data from the contact being a member – e.g. the display name to show it in a tooltip 
* add a second **With** for 'Contact Websites' as we want to link to the member's homepage

![Search Screen](../../img/search-kit/membership-listing-creating-search.png)

You can always tap **Search** to check the results of your current configuration. Here we have six memberships in total as a result. Note that when adding Membership Contact and Contact Websites Search Kit automatically added some colums with data from these sources:

![Search results](../../img/search-kit/membership-listing-search-results.png)

## Step 2: Add Columns to output additional Data

The columns we see in our search result will be the data we can later use on our public website, too. So we need to add what is missing before we proceed. In our case this is only the URL of the logo:

* tap **+Add** top right of the results table
* choose 'Membership Contact: Image URL'
* again check the results clicking **Search**

This means that in our case we use the standard contact image. You could also use custom fields for that but would have to add another data source then. 

Your result will now look like this:

![Search results with one more column](../../img/search-kit/membership-listing-search-results-url.png)

!!! Tip
    Don't forget to **Save** your work.

## Step 3: Adding and configuring Grid as Display

To show our search results we now need to add a display. In our case we choose a 'Grid' for that with which we can organize our Output in tiles:

![Adding Grid as Display](../../img/search-kit/membership-listing-add-grid.png)

You could name this view 'Our Members'. By default Search Kit will now add all the fields (columns) of your search as dragable items:

![Adding Grid as Display](../../img/search-kit/membership-listing-grid-items.png)

When you tap **Preview** you will see the output in a 3x3 pattern grid. You will see now that this is not yet the output we want to have there. So now we are going to change this to what you can see on the screenshot below. Take the following steps:

* **Remove** all items not needed (red arrow in screenshot above) – only leave 'Membership Contact: Image URL' there
* Check the **Image checkbox** as we want to show a logo as an image
* optional: set size attributes to make the logo sizes match – here we just adjust the height to 200px
* Check **Link** > select **'Other...'** in dropdown > select 'Membership Contact - Contact Websites: Website' in the **token dropdown** appearing now
* **Attention:** remove the '/civirm' in front of the token: 'civicrm/[Membership_Contact_contact_id_01_Contact_Website_contact_id_01.url]' becomes '[Membership_Contact_contact_id_01_Contact_Website_contact_id_01.url]' only as the token will fill in the absolute url of the member's website
* Check **Tooltip** and also add it using a token representing the display name

When you tap **Refresh** now you should see the logos as we want them to be there:

![changing Grid items and preview](../../img/search-kit/membership-listing-change-grid-items.png)

Note that this configuration will only show members with logos in their data. If you want to output those without, too, you could use the checkbox **Alternative image** in addition.

## Step 4: Adding and configuring a Form

In order to show the results on our public website we need to create an Afform Form now. To do so navigate back to the Search Kit dashboard an tap **Forms > + Create Form for Our Members Grid**:

![adding Form from Search Kit dashboard](../../img/search-kit/membership-listing-add-form.png)

Then:

* Give the Form a name and a description
* enter a URL for the page on which you want your membership grid to be shown – here we use 'civicrm/members':

![configuring new Afform Form](../../img/search-kit/membership-listing-form-created.png)

As soon as you tap 'Save' the link **View Page** will appear. You should now see our grid as we know it.

Let's add a filter to influence which membership types shall be shown to us. To do so switch from 'Form Settings' tab to the tab 'Our Members Grid' and **drag the item 'Membership type' into the tab 'Form Layout'**:

![adding a filter](../../img/search-kit/membership-listing-form-adding-filter.png)

Then:

* change the preset of our filter so that it shows the membership types we want and
* change details in layout – we could add texts etc., here we only change the title of a container element:

![configuring a filter](../../img/search-kit/membership-listing-form-configuring-filter.png)

When you now open the specified URL (your.civicrm.tdl/civicrm/members/) everything looks fine already – unless you're logged out...

## Step 5: Setting Permissions

That brings us to our last step: We need to allow our form to be accessible for anonymous users. To do that you first have to go back to the configuration of the search display and **switch of the Permission handling** there so that it looks like this:   

![switching permissions for search display](../../img/search-kit/membership-listing-grid-permissions.png)

Don't forget to **save changes** before you go back to the form configuration.

Now we can define who can view the page showing our grid. In our case we simply need to do two things:
* **remove all restrictions** by choosing 'Generic: Allow all users (including anonymous)' from the dropdown list. 
* check **Accessible on front-end of website**:

![switching permissions for search display](../../img/search-kit/membership-listing-form-permissions.png)

Now with the help of Afform logged out users will also be able to load our form and filter them, too.