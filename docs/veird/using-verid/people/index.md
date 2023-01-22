---
sidebar_position: 3
---

# People

The **People** option on the main menu, displays a list of people who have a relationship with the selected organization.

![People List](img/people-list.png)

## Many to Many People to Organization Relationships

It is important to understand that a person may have a relationship with many organizations.  And, of course, a organization has a relationship to many people.

When viewing a list of people, it is a list of people who have a relationship with the organization selected at the top of the screen.  (A choice of organizations is displayed only when you are a member of more than one organization.)

On the server, the system tracks three distinct entities to manage this:

* **Organizations** 
* **People** - there should only be one of these per real person
* **PersonOrg** - Think of this like an _Account_.  There is a PersonOrg record when a person has a relationship with an organization.  This is where the person's role is defined.  So, any person might be a User role in one organization, a Staff role at a different organization and an Admin in a third organization, etc.

## Adding a Person

![Person Add](img/people-add.png)

The first step to adding a person is to search to see if the person already exists.

![Person Search](img/people-search.png)

If the person is found, then click the **Use** button beside the person's name.

If the person is not found, then click **Add Person**.

![Person Add Dialog](img/person-add-dialog.png)
