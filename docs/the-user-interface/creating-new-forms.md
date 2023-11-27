# Creating new forms

CiviCRM ships with an extension that allows you to create your own forms.

The extension is called Form Builder (also known as Afform) and can be enabled
on the extensions page if not already installed.

![Enable Form Builder.png](../img/the-user-interface/form-builder/enable-form-builder.png)

Once enabled, a Form Builder link will appear in the menu under
**Administer > Customize Data and Screens**.

Form Builder is excellent for when only a few fields are needed, such as in the image below that depict embedded form on a main dashboard that quickly creates and assigns activities of a particular type (i.e. schedule a phone call). The user only needs to enter the contacts involved, but has the option to add a subject and details.

![activity_dashlet.png](../img/the-user-interface/form-builder/activity-dashlet.png)

## Build a Form

1. ### Create the form
   Go to **Administer > Customize Data and Screens > Form Builder**

![new form.png](../img/the-user-interface/form-builder/new-form.png)

!!! Note
  Currently, only activity and contact related forms are offered, however, it is anticipated that other entities will be added soon (they can be added programatically).

2. ### Configure the form settings
  The form configuration screen can be broadly grouped into two parts:
    1. a configuration pane (left) that contains:
      * the title (required and visible on the form)
      * the description (highly recommended for clarity)
      * the permission required to access the form
      * the url at which the form will be found (must start with `civicrm/`)
      * a checkbox to add the form to the home dashboard
      * a checkbox that allows placement to be configured using Contact Layout Editor
  
  ![view line](../img/the-user-interface/form-builder/view-form.png)

    2. a layout pane (right) that contains:
      * a display of what the form looks like 
      * settings icons on the fields
      * tabs to switch between the Form Layout and read-only auto-generated Markup
      * a **Save** button

  ![Configure the form](../img/the-user-interface/form-builder/configure-form.png)

3. ### Build the form
On the left configuration pane, there are two tabs. The second tab displays the content, determined by which contact type or activtiy was chosen, that can be added to the form. Drag and drop the desired fields into the layout pane on the right, where they can be ordered and customized.

![Build the layout](../img/the-user-interface/form-builder/build-layout.png)

Under the Elements section, there are some formatting options that allow blocks of text, other html, and/or containers to group fields to be added.

![Layout](../img/the-user-interface/form-builder/layout.png)

To the right of each field on the layout pane is a settings widget. This widget has options to:
- change the widget for data entry (for example, if you choose RichTextEditor then a full WYSIWIG input widget will show up)
- specifiy if the field is required
- add a default value
- specify if the label is shown
- add any pre or post help text


Click on the layout elements to:
- rename the label
- add placeholder text that will show in text boxes.

![Field settings](../img/the-user-interface/form-builder/field-settings.png)

The html elements also have options

![Container](../img/the-user-interface/form-builder/container.png)

to customize the look and overlal layout of the form:

![Art](../img/the-user-interface/form-builder/art.png)

Containers can also be saved as blocks, which can then be used on other
forms as well. For example, a grouping of customized fields that are reused could be saved as a block and applied to multiple activity forms. Then, if that grouping of fields needs to be changed, the block would only have to be changed once instead of on each individual form.

And on the topic of reusable values, the **Values** section at the top of the left pane includes the option to pre-set data on the form. Continuing with the example from this section, the image below shows the renamed tab,'Schedule call', and three pre-set values. Having pre-set values can be useful if information, such as the Added by or Activity Status fields, should be consistent across the form's submissions.

![Preset values](../img/the-user-interface/form-builder/pre-set-values.png)


## Using URL filters in search forms
 
For search forms with pages you can make them get filter values from a special part of the URL. This means you can **link to filtered views** of the search form, e.g. from another search form (by using tokens in the Link URL field.)

When looking at the left-side panel with a search display tab selected while editing a form, there's an option called Filters. Select a field, e.g. *Hair color*, then select URL and then type a codename, e.g. `haircolor`. If the field you want is missing, it's because that field has not been added to the Search, so jump back and do that first.

To use this feature, the URL can be constructed like this:
`https://your.example.org/civicrm/path/to/your/searchformpage/#?haircolor=brown` i.e. appending `#?haircolor=brown`. If you had multiple such filters, you would add subsequent ones like `#?haircolor=brown&hairlength=short`.

When the field has a `:` in it that indicates that the field is a 'pseudoconstant'. The underlying database value is generally a number which maps to a name and label. In this case the database field `payment_instrument_id` is a number. In some cases we know the number instead, in which case we could use `payment_instrument_id=1` in our URL or `payment_instrument_id:name=Cash`. As well as being more readable and discoverable, this variant is more useful for implementers who work with multiple sites, since the actual ID numbers will likely change between sites, but the `name` is fixed.

If the field is already filtered (e.g receive date before this week) then the URL filter will further narrow down the results rather than replace the existing filter.

The following formats are acceptable for dates:
   - `receive_date=2021-09-23`
   - `receive_date=20210923`
   - `receive_date=20210923234040` (i.e. time is 23:40:40)
   - `receive_date=this.month` (See [the list](../searching/relative-date-formats.md))

## Using URL parameters to set defaults in submission forms

The method described for setting values for filters in a search form can also be used to set values for other fields in form that will be submitted. So if a form for a hair styling salon had fields for email, first name, last name, hair color and hair length, adding `#?haircolor=brown&hairlength=short` to the URL of the form will cause the haircolor field to be defaulted to brown and the hairlength field to be defaulted to short when the form is rendered. The user could modify these values before submission. 

This method also works if the default is being specified in the URL for a field not shown to the user. The field must be added to the form for it to be processed, but its type can be set to "hidden". One use case for this is to allow a single input form to be reused in different contexts. For example, a signup form could be used at different events, with the URL key-value pair indicating which in person event the signup is from. Different QR codes incorporating different key-value pairs like `#?event=May1Rally` could be used at each event.
