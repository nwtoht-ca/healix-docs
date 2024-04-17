---
sidebar_position: 8
---

# Simulator

The Simulator, accessed via the *Test* tab, is used to demonstrate, manually test and automatically test a plan.

![Simulator](img/simulator.png)

## Role Testing

The simulator will run the app in a simulated phone for each role defined in the plan.  A test user with a randomly generated name is created. This allows for convenient testing of the plan.  For example, if completing a task in one role leads to the addition of a task to another role, this is immediately shown.

To put a role into desktop mode, use the full screen icon in the upper right corner of the simulated phone.

## Landing Page

If you have a [landing page](../presentation/landing-page) defined, a simulation windows is included.

![Landing Page](./img/landing-page.png)

Note that the simulation window is only intended to allow you to preview the landing page configuration.  The call to action buttons do not function.  If you want to create test users that come through the landing page, use the button above the simulated phone window.

## Work Queue

If you have associated a [work queue](../../work-queues/) with the plan template, a work queue simulation window is also provided.

![Work Queue](./img/work-queue.png)

## As At (Time Warp)

By change the As At setting, the plan is run at the specified time.  For example, if form assignments have been configured to appear N days after the start or if you have configured [time elapsed](/creating-plans/rules/when-to-evaluate) rules, then these conditions can be conveniently tested.

:::caution

Time travel to the past leads to unpredictable results.  For example, if *as at* was set to the future in order to trigger a time elapsed rule and a task was assigned to a user, setting the clock back to an earlier time does not undo the form assignment.

:::

## Fire Event

If  [integration events](../../integration/) have been [configured](../forms-and-fields/integrations.md), then a Fire Event button can be used to trigger a simulated inbound event to allow the testing rules or data display.

![Fire Event Button](./img/fire-event.png)

A pop window allows for the entry data that is received.

![Integration Event Data](./img/fire-event-pop-up.png)

## Reset (User Counts)

The *Reset* button pops a dialog where you can specify how users in each role to create.  When OK is pressed, new test users are created and simulation starts fresh.

![Reset](img/reset.png)

## Test Automation

As well as supporting manual testing, specific scenarios can be recorded, edited and played back in order to automatically tests a plan.  Creating automated tests makes it faster to release new versions of a plan.

