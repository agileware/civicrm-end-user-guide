# Soft Credits

Soft Credits are a familiar concept to many fundraisers, and are useful
for a better understanding of the sources of contributions received by
your organisation. They allow you to assign credit for a donation to
one or more people who are not the donor.

## Soft Credit Types

CiviCRM's soft crediting allows users to assign Soft Credit Types to
contributions. Assigning an appropriate reserved or custom Soft Credit
Type enables administrators to properly attribute contributions received
through one or more charitable contribution types (such as Donor Advised
Funds, Scholarships, Family Bequests, etc) whether solicited (P2P) or
not.

CiviCRM uses the following reserved Soft Credit Types:

-   In Honor of
-   In Memory of
-   Solicited
-   Personal Campaign Page
-   Gift

Lets say that a very active member of your organization was responsible
for getting 10 other people to make a contribution. Soft Credits
provide a way for you to credit this person and the actual donor,
without counting the contribution twice.

You can use CiviCRM's soft crediting to credit parts of a donation to
multiple people.

In the screenshot below, you can see that we have credited Magan
Cooper's contribution of $1,500.00 to three different people.

![A contribution of $1,500 with three soft contributions of $500.](../img/soft-credit-donation-1.png)

CiviCRM can also handle more complicated scenarios. For instance, Joe is
an active member of a community foundation that regularly contributes to
your organization. Joe solicited a contribution from Jane on behalf of
the community foundation. Your organization would therefore receive a
check from the community foundation. Using Soft Credit Types, users can
properly attribute the credit without duplicating contributions. In this
case:

-   The community foundation is the donor.
-   Joe would receive the solicited Soft Credit.
-   Jane would receive the donor advised Soft Credit.

This scenario is illustrated in the screenshot below.

![A constribution with a soft contribution from Joe, and one from Jane.](../img/soft-credit-donation-2.png)

As well as recording Soft Credits, we can also report on them. The
contribution detail report has optional columns which show Soft Credit
details. When checked, these will show four extra columns in CiviReport, which
can be used to view soft credit information.

![Screenshot of the report.](../img/z_sprint14_contributions_soft_credit.png)



## Honoree information and profiles

When creating a contribution page you will have the option to allow your
end users to make a contribution on behalf of an Honoree. To do so you
must select the **Honoree Section Enabled** checkbox.

This will reveal additional fields that will allow you to specify the
Honor Types and Profile to be included in this section.

![The form in CiviCRM.](../img/z-sprint14_honoree_section.png)

Once configured your end users will be able to enter Honoree info for
online contributions. CiviCRM will check to see if the Honoree exists
within CiviCRM already using the default duplicate checking rules on
your site, if a duplicate is not found a new contact record will be
created. A soft credit will be added to the contact record of the
Honoree.

![The form as the user will see it on the website.](../img/soft-credit-honoree-info.png)

## Soft Credits and Personal Campaign Pages

The concept of Soft Credits is closely related to
[Personal Campaign Page](personal-campaign-pages.md). When someone donates by a
Personal Campaign Page, their donation is soft credited to the owner of
the Personal Campaign Page.
