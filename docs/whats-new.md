---
sidebar_position: 11
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

* [Public Devices](./public-devices/) - Healix can now run on a kiosk or tablets in a waiting room.
* [Secure Landing Pages](./admin/plan-locking) - Landing pages can be locked down so that links expire or a user must complete another flow before accessing the page.
* [Adding to a Work Queue](./work-queues/adding-to-a-work-queue) - Users can now be added to a work queue.
* [Integration Configuration](./admin/configuring-integrations) - Integrations can now be configured to use a WebHook or a Pub/Sub model.
* [Export Plan](./admin/export-plan) - Plan data can now be exported to a json file

## September 2024, v6.2

* User added to the [Dynamic Data Model](./dynamic-data-model/).  This allows Content Managers to use rules towrite form values to a user's profile and user data is available.
* A Content Manage can now configure the Order of [Work Queue Items](./work-queues/creating-work-queues/edit-presentation)
* Work Queue definitions where moved from the main menu to the Work Queues tab of the [Plan Editor](./creating-plans/index.md)
* [Work Queue Displays](./work-queue-display/) allow content managers to configure the display of work queues on large monitors intended for a waiting room or similar area.
* A Content Manager can now define a rule that log out a user and end their session. See [Action](./creating-plans/rules/action.md) for more information.

## October 2024, v6.3

* A Content Manager can now define Service Locations associated with a work queue status.  See [Edit Work Queue](./work-queues/creating-work-queues/edit-work-queue.md) for more information.
* The Public Device and Work Queue Display are now subject to IP White Listing.  See [IP White Listing](./admin/ip-white-list/) for more information.
* A Content Manage can better configure the landing page and if a user should be invited to sign up or not. This was accomplished by removing the *Availability Type* field on the [Overview Tab](./creating-plans/overview-tab.md) of the Plan Editor and adding new options to the *Landing Page* section of the [Presentation Tab](./creating-plans/presentation/landing-page).
* Work Queues can now be consolidated into a single list. (DOCS TODO)
* A Work Queue definition can now be imported from a different plan. (DOCS TODO)