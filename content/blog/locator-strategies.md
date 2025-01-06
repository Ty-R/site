---
title: Locator Strategies
description: Understanding the importantance of locators
date: 2025-01-06
tags: ['Frontend testing']
---

To interact with a page element using a UI driver, it needs to be told how to find it; this is done through "locators", for example, to click a submit button:

```js
await page.getByLabel('Submit').click();
```

Certain locators will be faster and more reliable than others, and they can generally be broken down into four categories:

<div style="display: flex; gap: 1rem;">
    <div style="flex: 1;">
        <strong>User-Facing (Recommended)</strong>
        <p>Labels and text content may seem brittle and likely to change over time, but these attributes closely reflect what real users interact with. Tests using user-facing locators provide the highest levels of assurance by simulating actual user behaviour</p>
    </div>
    <div style="flex: 1;">
        <strong>Data Attributes (Recommended)</strong>
        <p>Test IDs are data attributes often used to improve reliability of automated tests; this is perfectly fine, but relying exclusively on data attributes might overlook potential issues like typos or layout problems that real users could encounter</p>
    </div>
</div>
<br>
<div style="display: flex; gap: 1rem;">
    <div style="flex: 1;">
        <strong>Structural Attributes (Acceptable)</strong>
        <p>IDs and classes are acceptable as locators but generally discouraged. These attributes are closely tied to the implementation details of the application and are prone to change as the UI evolves</p>
    </div>
    <div style="flex: 1;">
        <strong>XPath (Last Resort)</strong>
        <p>XPath can be used for complex queries where other strategies fall short, but this is not a positive. In most cases, simple XPath can be replaced with standard CSS selectors which are not only more readable, but faster. When a test requires a complex XPath query, it's often a smell - the test might be doing too much, or the testability of the application is lacking</p>
    </div>
</div>

## Advice

Ultimately, tests exist to provide assurace, so it's in the best interest of the business to support them. Slow, or unreliable tests as a result of poor locator practices are common, but we as QA Engineers should not just accept this, and workaround it, but push for the business to meet in the middle.

One example of this might be bringing up testability during planning or refinment, such as requesting that data attributes are added as part of the feature's acceptance criteria.

If writing complex locators, it is always worth stepping back and considering whether the test is trying to cover too much, or if the UI can be made more test-friendly.