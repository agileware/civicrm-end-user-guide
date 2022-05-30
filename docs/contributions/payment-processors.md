# Payment Processors

CiviCRM connects to a variety of different Payment Processors. Out-of-the-box, it comes with support for approximately 15 Payment Processors. Many other community contributed processors are available to download from the CiviCRM [Extensions Directory](https://civicrm.org/extensions).

Additional Payment Processors may also be available from third-party sites.

Community contributed processors are not supported by CiviCRM but there is no reason why they should not be just as reliable as the out-of-the-box Processors. If you do use a community contributed Processor, be sure that you have access to adequate technical support for that Processor, either in house, from the author of the Payment Processor, or from a trusted third party.

Browse a [comparison of the available Payment Processors](https://docs.civicrm.org/sysadmin/en/latest/setup/payment-processors/#comparison) in the System Administrator Guide.

## Selecting a Payment Processor

Below is a list various things to think about when choosing a Payment
Processor. Not all payment providers are created equal and there
are significant differences between them in terms of cost, suitability
for your use case, and availability. This is a quick guide to selecting
a Payment Processor.  If possible, you should talk to other similar and
nearby organisations that use CiviCRM about their experiences with
Payment Processors. You can also configure more than one Payment
Processor, and give constituents the option to choose the one they
prefer.

### Onsite vs offsite processors

Payment Processors can be split into those in which the user enters
credit card details directly on your site, and those that transfer the
user to another site to make the payment, and then return them to your
site once the payment is made. You can typically brand the payment site
to a limited extent – for example you might be able to add your
organisation name, logo and colours – but the workflow is less seamless
and a percentage of people tend to get lost along the way and not
complete the payment.

As well as providing a more seamless experience for end users, onsite
Payment Processors allow site admins to process card payments
(Contributions, Membership Fees, Event Payments, etc.) from CiviCRM
admin pages.

The disadvantage of processing payments directly on your site is that
you will need to have an SSL certificate to ensure the security of the
users card details as they are transmitted over the internet. SSL
certificates cost money (typically an annual fee) and they are not
straight forward to set up. Your hosting provider or system
administrator can help you here. You may also want to read the
*Security* section in the *Initial set up* chapter of this book.

It is worth noting at this point that CiviCRM never stores credit card
details on your server. It only transmits them to the payment
processor.

### Regional Availability

For many countries there are no Payment Processors written that support
their currencies. If you do not have Payment Processor support for the
Payment Processor you want to use, consider writing your own processor
or asking a third party to do so.

### Merchant account vs built-in

Most organizations that accept credit card payments will have their own
merchant account through a bank, however these usually have monthly
charges which may not suit smaller organizations (though they generally
have lower percentage payments). You can expect to pay a fee for the
merchant account and to the Payment Processor, though these may be
bundled together. Some, like World Pay and Paypal, do not require separate
merchant accounts.

### Support for Recurring Contributions

Support for Recurring Contributions and auto-renewing memberships is an
important feature for many organizations. However not all of the Payment
Processors available for CiviCRM support this feature. Many processors that allow you to manage Recurring Contributions from within CiviCRM but PayPal and Authorize.net require you to log into their own portals to manage Recurring Contributions. Some, like Moneris, have "incomplete" support.

If you have configured a Payment processor that includes Recurring Payments as a feature, you can enable Recurring Contributions in your Contribution Page settings. For more details on page-specific configuration, refer to the [Online Contributions](online-contributions.md#setting-up-a-contribution-page-full-details) chapter.


### Managing Recurring Contributions

PayPal and Authorize.net allow users to set up a Recurring Contribution, which is then managed through the Payment Processor site. Each time a payment is made, the processor creates a contribution record in CiviCRM. You must log onto the processor's site to make changes to the payment amount, frequency, etc.

Other processors (e.g IATS, eway, Payment Express, SagePay, Paypal Commerce/Checkout), expect you to manage the Recurring Contributions directly in CiviCRM. The payment is triggered from within CiviCRM, which sends a request to the processor, and returns a completed contribution record to CiviCRM if it's successful.

You can manage a Recurring Contribution by going to the **Contributions** tab on a contact record. In a separate tab, there is a separate section for Recurring Contributions. In order to be able to recharge a card, processors often store a payment token. This can be used to recharge a credit card, but only to put money into your account, not anyone elses. The rules around how these may be used vary and most Processors only use them for regular Recurring Payments.

![screenshot](../img/RecurringContribution.jpg)

You have the option to **View**, **Edit**, or **Cancel** the Recurring Contribution here. You can edit the Recurring Contribution Amount, Number of Installments, Next Scheduled Contribution Date, Financial Type, Status, Start Date, and whether or not the donor receives an email notification on each payment installation. The donation frequency (e.g. weekly, monthly) cannot be changed from within CiviCRM.

If you **View** the Recurring Contribution, you will also be able to **View**, **Edit**, or **Process** the card on file. Viewing or editing will bring up the customer and card information.

For iATS users, there is an administrative page where you can view recent iATS transactions. On the menu, navigate to **Contributions > iATS Payments Administration** to see the report.


### Cost

Determining which Payment Processor is least expensive depends on the
number and average size of the transaction you process. So the question
is not which processor is the cheapest, but which is the cheapest for
you. Commission percentages, per-transaction charges, and fixed monthly
charges vary along with set-up costs. In general, if you process many
transactions, an account with a monthly fee but low commission might be
a good option. On the other hand, if you expect infrequent transactions,
it is best to avoid monthly fees and accept paying a higher commission.

### Usability

If you do not collect the credit card information yourself on your own
site, you need to consider whether the payment workflow is intuitive and
easy to use. Paypal Standard is often confusing to end users because
they are not sure whether or not they need to create a PayPal account.
Such a barrier can result in decreased contributions.

## Support

CiviCRM supports the processors that are incorporated into the core
codebase, to the extent that they ensure they do not break in upgrade -
support and enhancements of community contributed processors are
generally expected to come from the community.

## Set up

You can configure one or more Payment Processors for your CiviCRM
installation.

You will then need to assign an active Payment Processor to each Online
Contribution Page and each paid Event. If no Payment Processors have
been configured for your site,

1.  Go to **Administer > System Settings > Payment Process** and
    click on **New Payment Processor**.
2. Choose the Payment Processor Type from the dropdown list.
3.  Assign a descriptive name to this processor configuration and an
    optional description. The name will show up when you want to select
    a Payment Processor for a Contribution Page or Event. A description
    can be useful if you are configuring multiple merchant accounts for
    different chapters or sub-organizations within your site with the
    same Payment Processor type.
4.  Select a Financial Account. You probably want to have a separate
    Financial Account for each Payment Processor, but your bookkeeper or
    accountant will be able to advise you best on this. The Financial
    Account you select records where the money gets deposited, not the
    sort of revenue you anticipate it receiving. The Contribution,
    Membership and Event money you receive will also get recorded into
    different revenue Financial Accounts as well, based on the
    configuration of contribution pages and events. For a partial
    explanation of how this works, see *Double Entry Accounting* in
    Wikipedia.
5.  Make the Processor active so that it is available for use with paid
    Events and Online Contribution Pages. If the Processor allows you to
    collect credit card information on your website, your staff will
    also be able to use it to submit credit card Contributions and
    payment for Memberships and Events.
6.  If you have multiple Payment Processors, the one you set as the default
    will be selected when you create a Contribution or Event Page or process a
    credit card payment in the admin area, although you will be able to
    override that selection manually.
7.  Fill in the appropriate live payment and test payment details for your
    Payment Processor. Note that the fields in these sections vary according to
    the Payment Processor type selected.

You will need to do some further set up on the actual payment gateway but that
is beyond the scope of this book and should be documented by your gateway.

Once done, the Processor will be available in your paid Events and
Contribution pages.

## Test payments and dummy Payment Processors

For the purposed of testing, you can configure dummy Payment Processors.

If you do use a dummy Payment Processor, or are using any payment pages
in test mode, the following card details should work:

-   Card type: Visa
-   Card number 4111 1111 1111 1111
-   CVV: any three digits
-   Expiry: any date in the future

## Writing a new Payment Processor

If you cannot find a suitable Payment Processor, or want to use a
specific payment provider that is not currently supported by CiviCRM,
you can write a new Payment Processor integration, or pay someone else
to do so.
