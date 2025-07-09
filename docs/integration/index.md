---
sidebar_position: 7
---

# Integration

Healix integrates with other systems through a classic enterprise bus, pub/sub design pattern.

![Concepts](./img/concepts.png)

* System level events are published by Healix to the bus.  These system events include when a plan is assigned to a person, when a person submits a form or when a work queue item's status is changed.
* Third parties can work directly with the Healix NATS bus or or exchange information via a REST API / WebHook.
* The Plan Template Editor, is used to configure how to respond to inbound messages
* If multiple inbound messages with the same data are received, Healix will only process the first message.

## Configuring Healix to Respond to Incoming Events

A third party system can publish events to the Healix integration bus.  In order for Healix to react to these incoming events, a content manager must describe the inbound event payload and then implement rules to respond.  For example, if a scheduling system posts a time slot, a rule can assign a form to the user that displays the upcoming appointment time.

Configuring the integration event payload is done in the [template editor's integrations section](../creating-plans/forms-and-fields/integrations).  Configuring the reaction is done in the [rules](../creating-plans/rules/) section.

## System Events (Outgoing Events)

An event's payload is in JSON format.  For example:
```
{
  "messageType": "healix.hrh.planCreated",
  "orgId": "hrh",
  "requestedBy": "15eba04e-0e95-4d03-916e-e6cd9807006b",
  "info" {
    "planId": "242b7766-ac9e-451f-9fe4-dd54489108c1",
    "templateName": "sAI-ERComp".
    "userId": "2a925299-aee7-4749-bf10-909d3f6c6770",
    "isTest": false,
    "roleAssignments": [
      {
        "roleId": "Patient",
        "userId": "2a925299-aee7-4749-bf10-909d3f6c6770"
      }
    ]
  },
  "branch": "master"
}
```
Each payload has the following common fields:

* *messageType* - prefixed with healix.  Then the organization Id, then the logical message type which is one of *planCreated*, *formSubmitted*, or *workQueueStatusUpdated*
* *orgId* - the organization id 
* *requestedBy* - the user id of the user who triggered the event
* *traceId* - an id that identifies the origination event.  Useful for debugging across microservices
* *branch* - identifies the instance of Healix the emitted the event
* *info.planId* - the plan id (identifies the instance of a template assigned to a user)
* *info.isTest" - true if the event originates from a test user, not a real user
 
### Payload Attributes Specific to planCreated

* *info.templateName" - the name of the template (app)
* *roleAssignments[n].roleId* - the id of the role as defined in the plan template
* *roleAssignments[n].userId* - the user that has been assigned to the associated role

### Payload Attributes Specific to formSubmitted

* *info.formName* - the name of the form that was submitted
* *info.formAssignmentId* - uniquely identifies a form / user
* *info.data* - the contents of the form submission

### Payload Attributes Specific to workQueueItemStatusUpdated

* *info.workQueueName* - the name of the work queue
* *info.workQueueItemId* - the id of the work queue item
* *info.status* - the new status, as defined in the work queue [configuration](../work-queues/creating-work-queues/) 
* *info.oldStatus* - the status that is being overwritten
* *priority* - the current priority of the workQueueItem
* *serviceLocation* - where the service is being performed


## Accessing the Bus via NATS

Please contact support@healix.me.  In the future this process will be automated with an API Key.

## Configuring Web Hooks and HTTP Post

As an alternative to working with the pub/sub mechanisms provided by NATS, you can configure a URL and filter criteria so that a system message is converted to an HTTP post.  See [Configuring HTTP Integrations](../admin/configuring-integrations)




