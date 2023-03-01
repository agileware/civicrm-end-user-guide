# What is SearchKit?

## About

SearchKit is a powerful search query builder with extensive options for displaying results. It is appropriate for site builders, power users and developers but non-technical staff are likely to need training or to spend some time learning the inteface. Alternatively a more experiences user may create SearchKit searches and make them available to other users via the menu system or as a dashlet on the main CiviCRM screen.


Searches built and saved in SearchKit can be targeted for use by different roles of staff users as well as unauthenticated end users.

## Getting started

You can access SearchKit under the menu **Search > SearchKit**.

## Concepts and terminology

Getting familiar with SearchKit requires some understanding of it's components and concepts

### Entities

And entity is a developer word for a 'thing'. In most cases the 'thing' (Entity) you want to search for will be something like a Contact, a Contribution etc. You start your search by ensuring it is set to the entity you want to search for.  


### Joins



### SearchDisplays

### Forms


## SearchKit and other CiviCRM search functionality

SearchKit fully replaces the old, more limited, Search Builder. 

It is more powerful than Advanced Search, and covers some extra parts of CiviCRM. However, many users may continue to prefer to use Advanced Search and searches like **Search > Find Contacts** and **Events > Find Participants**. We are no longer adding new features to these but they will be part of CiviCRM for the forseeable future.

The upper left Quick Search continues to be more convenient for quickly retrieving records based on part of an email or name or other single term. 


## Site Admin notes

### If SearchKit is missing.

On recent versions of CiviCRM SearchKit cannot be disabled. However, in the past SearchKit was not turned on when CiviCRM is installed. If it is not enabled on your site you can enable it on the Extensions screen. Navigate to **Administer > System Settings > Extensions**. Beside SearchKit, select the **Install** link then select the **Install** button.

## Developer notes

### Features

SearchKit meets a number of developer needs as SearchKit searches can:

* be saved and exported,
* have any number of unique displays on their own,
* be connected to the dashboard, contact screen or individual URLs,
* have exposed filters for easy filtering,
* be connected to a Smart Group,
* be used for your own entities custom created for your website,
* be shipped with an additional extension.

### SearchKit and FormBuilder

SearchKit and **[FormBuilder](../../the-user-interface/creating-new-forms.md)** work together to let users search for CiviCRM data and create new user interfaces without writing code. 

SearchKit’s Graphical User Interface lets you click, drag, drop and write. SearchKit builds and defines the underlying search and provides many ways to display it. FormBuilder shows filters and database actions, and provides more options for layout.

For developers, it is useful to know that they expose all the functionalities that are given by **APIv4**. They can be used in many ways, including adding new pages to CiviCRM, tabs to the Contact Summary page, or searchlets to the CiviCRM Dashboard.

![Diagram of Searchkit & Formbuilder](../../img/search-kit/searchkit-formbuilder-schema.png)
