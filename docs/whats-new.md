---
sidebar_position: 10
---

# What's New?

## May 2024, v6.0

As of May 2024, the following major features are available:

* Forms are part of a plan template.  In previous versions, Forms were globally scoped.  This caused problems when a shared form was changed in a way that was incompatible with templates that referenced it.  Forms can still be re-used, but it requires copying the form into the template.
* [Work Queues](./work-queues/) allow staff to process patients as they interact with the system.  For example, a queue can be [configured](./work-queues/creating-work-queues/) for staff to triage patients that enter an emergency department or check in patients when they arrive for an appointment. The [simulator](./creating-plans/simulator/) has been extended so that content managers can easily test a work queue.  An administrator can [assign](./work-queues/admin-work-queue) staff to work on work queues.
* [Landing Pages](./creating-plans/presentation/landing-page) can be configured for each plan allowing users to quickly onboard onto Healix and run the plan. The [simulator](./creating-plans/simulator/) has also been extended so that content managers can easily preview landing page configurations.
* Special single-use accounts allow users to run plans without "signing up" as a Healix user.
* Healix can [integrate](./integration/) with third party systems with a pub/sub API or a WebHook/REST API
* The [Dynamic Data Mode](./dynamic-data-model/) has been extended with work queue items and inbound integration events
* Administration improves including the ability to edit a user's phone number, gender and date of birth
* The View Data command for a user includes the ability to see Integration events and rules execution history

## June 2024, v6.1

* [Public Devices](./public-devices/)
* [Secure Landing Pages](./admin/plan-locking)
* [Adding to a Work Queue](./work-queues/adding-to-a-work-queue)
* [Integration Configuration](./admin/configuring-integrations)
* Export Plan
