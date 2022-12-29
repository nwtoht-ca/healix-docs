---
sidebar_position: 3
---

# Running Test

Typically tests should be run when releasing a new version of a plan.  Although, tests are also useful to generate data as part of the authoring process or for demos.

To run one or more test cases, first select the tests from the test case list:

![Multi Select](img/test-case-multi-select.png)

And then click *Run*.  A confirmation screen is displayed:

![Test Run Launch](img/test-launch-screen.png)

**Generate Screenshots and Save** - If this selected, the test results will be recorded in the test history.  This can also be very useful for compliance with quality programs.  It will also generate and download screenshots. (In the future the screenshots will be saved to the server and used for comparison.)

The system then start executing the steps in sequence:

![Test Run](img/test-run.png)

Then the results of the test is shown.

![Test Results](img/test-results.png)

If a test fails, the expander shows the reason for the failure.

![Test Failure Reason](img/test-fail-reason.png)