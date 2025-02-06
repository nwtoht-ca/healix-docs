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

* **submission** - any form or rule derived data
* **plan** - fixed plan attributes (e.g. start date) and calculated columns
* **integration** - any incoming payload that a plan has been configured to receive
* **workQueueItem** - fixed work queue item attributes

## Categories

Some entities must define a second level:

* *submission*, category is the form name
* *integration*, category is the subject (a.k.a topic) name
* *workQueueItem*, category is the work queue name
* *plan*, there is no category and the reference requires only two levels

## Fields 

A field is defined by a name and type information

## Examples

For example, to get a field named "field1" from a form named "form1":

```
submission.form1.field1
```

Or to read the status of a plan:

```
carePlan.status
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
        plan
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
        workQueueItem
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




