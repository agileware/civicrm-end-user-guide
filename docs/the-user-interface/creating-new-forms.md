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
2) ![new form.png](../img/the-user-interface/form-builder/new-form.png)
