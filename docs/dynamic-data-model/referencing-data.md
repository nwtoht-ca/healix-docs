---
sidebar_position: 1
---

# Data References

To reference data, names for levels are separated by ``` . ``` are used when functions need coordinates for a data point.  For example: 

```
entity.category.field
```

## Entities
Entity is the highest level of categorization for data. Two entities currently exist

* **integration** - any incoming payload that a plan has been configured to receive
* **plan** - fixed plan attributes (e.g. start date) and calculated columns
* **submission** - any form or rule derived data
* **user** - user profile data
* **workQueueItem** - fixed work queue item attributes

## Categories

Some entities must define a second level:

* *integration*, category is the subject (a.k.a topic) name
* *plan*, there is no category and the reference requires only two levels
* *submission*, category is the form name
* *user*, category is the user's role as defined in the plan
* *workQueueItem*, category is the work queue name

## Fields 

A field is defined by a name and type category.

Usually fields are dynamically defined based on the configuration of the form, plan, and integration.

## Examples

For example, to get a field named "field1" from a form named "form1":

```
submission.form1.field1
```

Or to read the status of a plan:

```
plan.status
```

These data references are used by by *[Healix Expression Grammar](/dynamic-data-model/healix-calculation-grammar)* discussed next.

## Catalog

The following fixed attributes are available

<table>
  <thead>
    <tr>
      <td>
        Entity
      </td>
      <td>
        Category
      </td>
      <td>
        Field
      </td>
      <td>
        Permitted Values
      </td>
      <td>
        Writeable
      </td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        integration
      </td>
      <td>
        $subject
      </td>
      <td>
        _submitted
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        submission
      </td>
      <td>
        $formName
      </td>
      <td>
        _submitted
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        plan
      </td>
      <td>
      </td>
      <td>
        title
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        plan
      </td>
      <td>
      </td>
      <td>
        startDate
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        plan
      </td>
      <td>
      </td>
      <td>
        endDate
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        plan
      </td>
      <td>
      </td>
      <td>
        status
      </td>
      <td>
        OPEN, CLOSED
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        plan
      </td>
      <td>
      </td>
      <td>
        riskStatus
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        title
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        firstName
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        middleName
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        lastName
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        fullNam
      </td>
      <td>
      </td>
      <td>
        read
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        email
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
        <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        phone
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        dateOfBirth
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        user
      </td>
      <td>
        $role
      </td>
      <td>
        gender
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        title
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        createdAt
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        ticketNumber
      </td>
      <td>
      </td>
      <td>
        read only
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        priority
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        serviceLocation
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        queuePosition
      </td>
      <td>
      </td>
      <td>
        read-write
      </td>
    </tr>
    <tr>
      <td>
        workQueueItem
      </td>
      <td>
        $workQueueName
      </td>
      <td>
        status
      </td>
      <td>
        statuses defined in the work queue definition
      </td>
      <td>
        read-write
      </td>
    </tr>

  </tbody>
</table>

Where $formName, $subject, $workQueueName, and $roleName are the names of the form, subject, work queue, and role respectively.


