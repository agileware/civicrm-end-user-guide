# Viewing the CiviContribute dashboard

The CiviContribute main page or dashboard summarises the contributions made,
including lists of contributions received in the current Month-To-Date, Year-To-Date, and cumulatively since inception 
(i.e. all contribution records in your CiviCRM installation). This allows you to easily browse contributions that have 
been recorded automatically or added manually. The dashboard also provides buttons to manage and add contribution pages.
Different layouts are available for viewing summaries. The following screenshot
shows the most recent contribution to a campaign using the Table Layout tab:

![ContactSummary1a](../img/CiviCRM-CiviContribute-EveryDayTasks-ContactSummary1a-en.png)

You can also view bar or pie charts to compare contribution totals across
months of a given year and across years by clicking on the Chart Layout tab:

![ContactSummary1b](../img/CiviCRM-CiviContribute-EveryDayTasks-ContactSummary1b-en.png "ContactSummary1b")

Finally, you can add any number of contribution [Report Dashlets](../the-user-interface/menu-dashboard-and-dashlets.md#dashlets) to your
personal CiviCRM Dashboard. These might include a bar chart summary of
Year-To-Date contributions by Financial Type or month, a list of the top 10
donors, etc.

# Finding contributions

CiviCRM makes an important distinction between contributions and the
people that made the contributions. It is important to appreciate the
difference between the two when you are searching contributions. For
example, if you want to send a gift to all people that made a
contribution in the last year, what would be more appropriate? Contacts
or contributions? The answer depends on whether you want to send two
gifts to people that made two contributions and there is of course no
right or wrong answer - it just depends on your approach. It is
important to think about this each time you do a search.

The **Find Contributions** search allows you to search based on contribution
data and return contribution records. It is found at **Contributions > Find
Contributions**.

![Contribution Find Screenshot](../img/contributions-find-search.png)

You can search based on a number of criteria, such as Date Range, Contribution
Amount, Contribution Status etc. Contributions must match all specified criteria
in order to be returned, so the more criteria you enter, the narrower the search
 will be. For example, searching for the Financial Type "donation" and the Date
 Range "January 1st to May 31st" will return contributions that meet both
 criteria. Relative Date Ranges such as "Last Month" or "Last Year" are often
 quite useful.

 As well as the subset of records resulting from the search, the results screen
 from a Find Contributions search displays the Total Amount, Number of
 Contributions, Average Contribution Mean and Mode for the search results.

 ![Screen shot batch update from search](../img/contributions-find-editcriteria.png)

 You can select an action to perform from the **Actions** menu once you select
 all or a subset of the results. You can:

 - **Update multiple contributions**: This is useful if you want to update a
 large number of contributions' thank-you date at once, for example. You need to
 [create the profile](../organising-your-data/profiles.md) you want to use *before*
 you perform the search and batch update.

 - **Delete contributions**: This removes contributions entirely from the
 system, as if they had never been entered in the first place. Editing
 contributions and updating their status to canceled provides a better audit
 trail, but there may be situations where you do want to Delete, such as a
 contribution entered on the wrong contact's record.
 - **Export contributions**: This is an export of contributions.  If you
 choose to export multiple contributions from the same contact you will end up
 with one row for each contribution in your export file. If you want to do
 searches that return one result per contact, use the contact advanced search.

 - **Receipts - Print or Email Contribution:** This allows you to create a PDF
 file of all the receipts in the search, or email the receipts to the associated
 donors. See "Sending thank you letters" below for more information.

 - **Email - send now**: Send an email to all or selected contacts found in the
 search.

 - **Thank-you letters - print or email**: Create a custom PDF letter for each
 of the contributions selected, with the option to update the receipt or thank
 you date for each.

 - **Record payments for contributions**: This allows you to record payments
 details for all or selected online "Pay Later" contributions. This action only
 works for contributions with the status of Pending (Pay Later).

The **Advanced search** returns contacts by default, but you can choose
**Contributions** for the **Display Results As** field to show contributions
rather than contacts. The standard contribution search criteria are available
when you expand the Contribution pane, however you can also filter your results
with additional criteria ("Find all donations to the tax appeal made by members of my organisation" or "Show me all contacts who have contributed more than
$100 last year AND who live in California").
