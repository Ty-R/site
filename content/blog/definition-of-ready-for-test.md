---
title: Definition of Ready for Test
description: Unblurring the line between dev and test
date: 2024-12-29
tags: QA processes
---

The production line of many teams flows through development and testing stages, but between these often lies an ambiguous "grey area" where responsibilities blur and assumptions creep in.

When picking up a test-ready ticket, it is not uncommon for QA Engineers to:
* Spend time trying to find a change only to realise it has not yet been deployed
* Encounter unexpected, uncommunicated deviations from original requirements
* Chase down missing information required to fully test a change

This often results in developers being pulled back into work they thought was complete, disrupting their flow.

## The Grey Area

Once code has been written, reviewed, and merged, it's reasonable to assume that it's ready for test, so a developer wouldn't be in the wrong for changing the ticket's status. It's also reasonable for testers to assume that tickets in a test-ready status are indeed test-ready, so they aren't in the wrong either.

The issue lies in the assumptions being made due to both sides having a separate idea of what it means for a change to be test-ready. The solution involves working together to agree on a set of conditions that, once met, means a change is ready for test.

### Example

The specific conditions are naturally going to vary between teams but ultimately, we want to ensure a smooth handover process. Here's a baseline checklist:

* ✅ Changes have been successfully deployed to the correct environment
* ✅ Any requirement deviations have been clearly communicated
* ✅ Function-oriented acceptance criteria have been fully met
* ✅ Results of tests already performed have been shared
* ✅ Any challenges that may impact testing have been shared
* ✅ Any extra information that may facilitate testing has been shared
