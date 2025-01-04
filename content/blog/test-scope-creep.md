---
title: Test Scope Creep
description: Bringing QA back down to earth
date: 2024-12-10
tags: ['QA processes', 'Frontend testing', 'Backend testing']
---

In project management, "scope creep" happens when new features, requirements, or ideas keep getting added during the development process.

In the testing world, this typically translates to over-testing -- a tendency to expand testing efforts beyond what is necessary or valuable.

## Test Approaches That Suffer

In my experience, the test approaches that are generally impacted are:

* Regression tests
* End-to-end tests
* Smoke tests

Regression tests often fall victim to quantity over quality, while end-to-end and smoke tests often suffer from "bloat" given the temptation to add quick checks to a test that is already in the area.

The root causes of these issues often include poor communication between testing stages, insufficient earlier test efforts, unclear prioritisation, or a general lack of trust in prior testing, environment configurations, or deployment processes.

## Staying Focused

To avoid test scope creep and stay focused, teams need to establish a disciplined approach to their testing efforts. Start by clearly defining the objectives for each type of test and agreeing on the critical paths or features that require the most attention. Risk-based prioritisation is an effective tool here, allowing teams to focus their efforts where they will have the greatest impact.

Regular communication is also essential. Teams must align on the purpose of each test phase and avoid duplication by maintaining a shared understanding of what has already been covered.

Tests should also be regularly reviewed, pruned, and updated to stay relevant and effective.
