# Creating new forms

CiviCRM ships with an extension that allows you to create your own forms.

The extension is called form builder (or sometimes afform) and can be enabled
on the extensions page if not already enabled

![Enable Form Builder.png](../img/the-user-interface/form-builder/enable-form-builder.png)

Once enabled a 'Form Builder' link will appear in the menu under
Administer->customize data and screens.

A good use for the form builder is if you do data entry where only a few fields need to be 
entered. For example the image below shows a form embedded in the main
dashboard that has been created to quickly create activities of a particular type (schedule a phone call) and assign
them. The only details the user needs to enter are the contacts 
involved and optionally enter the details and subject.

![activitiy_dashlet.png](../img/the-user-interface/form-builder/activity-dashlet.png)

The steps to create a form like this are

1) Create the form - go to Administer->Customize data and screens->form builder
As of writing only contact and activity forms are offered - but is expected
other entities will be added soon (they can be added programatically)
![new form.png](../img/the-user-interface/form-builder/new-form.png)

2) Configure the form settings
The form configuration screen broadly has 2 parts - a configuration pane (left)
and a layout pane (right). On the left you will specify
- the title (required and visible on the form)
- the description (highly recommended so you can remember why you created the form)
- the permission required to access the form
- the url at which the form will be found (must start with civicrm/)
Once the url has been saved it will be possible to view the form at this
url and a link to it will appear on the right.
![view line](../img/the-user-interface/form-builder/view-form.png)
- whether users can add the form to their dashboard
- whether the form should be available for placement to the contact
layout editor
![Configure the form](../img/the-user-interface/form-builder/configure-form.png)

3) Build the form
The second tab on the left has elements relating to the activity that can
be configured or dragged to the layout on the right
![Build the layout](../img/the-user-interface/form-builder/build-layout.png)
- In the values section are fields with pre-set values - for our example
we have renamed the tab to 'Schedule call' and pre-set 3 values
![Preset values](../img/the-user-interface/form-builder/pre-set-values.png)
- We can then drag the fields we want to the layout. Note that under
'Elements' there are some formatting elements - allowing us to add
blocks of text or other html and to add 'containers' to group fields.
![Layout](../img/the-user-interface/form-builder/layout.png)
To the right of each field is a settings widget. This widget has options to
- change the widget for data entry - for example if you choose
'RichTextEditor' then a full wysiwig input widget will show up.
- specifiy if the field is required
- add a default value
- specify if the label is shown
- add any pre or post help text

In addition you can click on the layout elements to
- rename the label
- add placeholder text that will show in text boxes.

![Field settings](../img/the-user-interface/form-builder/field-settings.png)

The html elements also have a bunch of options
![Container](../img/the-user-interface/form-builder/container.png)
facilitating such dubious artistry as this...

![Art](../img/the-user-interface/form-builder/art.png)

Containers can also be saved as 'blocks' - which can be used on other
forms as well - potentially facilitating updating a bunch of forms at once.
If you had, for example, a number of activity forms for different use
cases but the custom fields you wanted to have filled in changed
quarterly these custom fields could be in their own block and changing
that block once a quarter would change all the forms using that block.
