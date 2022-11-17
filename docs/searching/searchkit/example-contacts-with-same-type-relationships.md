# Example: Listing Contacts who have relationships of the same type

There are some scenarios in which a user may want a list of contacts who have more than one (or any number) of the same relationship type. For example, a children’s summer camp may want to know which contacts within their CiviCRM installation have more than one child. The user could then turn the search results into a mailing list to offer enrollment discounts to multi-child families.

## Step 1: Create a new search and set initial criteria

1. Go to **Administer > Search > Search Kit** and click **New Search**.
1. Ensure that the default **Contacts** is selected as the primary entity to Search for
1. Select **With (required)** and **Contact Related Contacts** on a new entity
1. Click the *+Group By** button and group by both **Contact ID** and **Relationship Type**

![Search criteria](docs/img/search-kit/multirelationships-search-settings.png)

## Step 2: Add the Relationship column to the search

1. Below where the criteria is configured, click on the **+Add** button and select **Contact Related Contacts: Relationship**
1. Though not necessary, it might be helpful to add the **Contact Related Contacts: Relationship from contact** column to indicate the relationship type for clarity, especially if your search will include more than one type of relationship.

![Relationship column](docs/img/search-kit/multirelationships-columns.png)


## Step 3: Transform the Relationship column

1. Click on the **Field Transformations** section just below the **Having** drop down list
1. Select **Count** as the transformation for **Relationship**

![Field Transformations](docs/img/search-kit/multirelationships-fieldtransformations.png)


## Step 4: Add a Having clause

1. Select **(Count) Contact Related Contact: Relationship** from the Select field* drop down list under the **Having** section
1. In this scenario, select the greater than symbol (>) and enter 1 in the field to the right of the symbol.
1.  Click **Search** to view your results. Don’t forget to name and save your search as well!

![Having clause](docs/img/search-kit/multirelationships-having.png)
