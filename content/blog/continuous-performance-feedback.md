---
title: Continuous Performance Feedback
description: Measuring performance every step of the way
date: 2024-12-19
tags: ['QA processes', 'Performance testing']
---

Performance testing is an umbrella term and encompasses any activity measuring performance or identifying performance-impacting factors, but often when talking about performance testing, our minds will jump to the macro - load or stress testing.

Load testing is crucial, but shouldn't be the only way we measure performance. Instead, we should aim to measure performance continuously so that by the time we get to a full-scale load test, we can be confident all components that make up the system are _**ready**_ to be tested at scale.

## A Pipeline Approach

Performance can, and should be measured throughout the cycle.

**During development**, we can:
* Use linters to surface performance impacting inefficiencies
* Measure unit or component test timings, generally
* Include tests that specifically measure component performance
* Analyse and optimise database queries
* Run small-scale load tests to find immediate issues
* Use tools like Lighthouse CI to measure page performance

**Post-deployment (pre-release)**, we can:
* Use Lighthouse for integrated system performance
* Measure page or workload performance through test timings
* Run small-scale load tests to check integrations

**Post-release**, we can:
* Conduct preliminary load tests
* Conduct full-scale load tests during downtime
* Collect real-world metrics from user interactions
* Simulate user behaviour through synthetic monitoring

Just like with defects, we want to measure early since issues only become costlier to fix at later stages. 

## Measuring Frontend Performance

When it comes to performance in the context of a frontend, there are generally two things we want to consider:
* Performance of the client-side code itself (e.g. rendering time, logic)
* Client-side behaviour when it has to wait, or deal with unexpected responses

It is certainly possible to test these post-deployment, using tools like Lighthouse while the backend is put under load, but this may be overkill. We can measure component performance in isolation, and we can verify client-side behaviour through mocking upstream provider conditions.

For higher assurance, we may want to measure the performance of pages where components may interact with eachother, or browser APIs, and may wish to set up complex state on those pages. For this, we could introduce UI drivers to handle that state setup, then begin the performance test.