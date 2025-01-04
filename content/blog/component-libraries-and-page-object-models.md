---
title: Component Libraries and Page Object Models
description: Extending a common design pattern
date: 2024-12-28
tags: ['Frontend testing']
---

Writing automated tests for an application's frontend often involves a UI driver to handle interactions with the interface. A widely adopted design pattern to structure this test code is the **Page Object Model**.

Modern web applications frequently use reusable component libraries (think buttons, modals, or dropdowns that appear on multiple pages). Test frameworks often don’t reflect this reuse, and page objects may contain duplicate interaction logic as a result.

## Component Models

To reduce this duplication, we can extend the Page Object Model pattern to create **Component Models**. Just like page objects, these would encapsulate interactions, but at the component level. These component objects would then be imported into page object models so that they can be exercised in the context of a particular page.

### Example: Button Component

Let’s say your application uses a custom button component that is used across multiple pages. Traditionally, we might reflect this in test code by defining the interaction within the respective page objects:

```javascript
// In Page Object A
async clickSaveButton() {
    await this.page.getByLabel('Save').click();
};

// In Page Object B
async clickSaveButton() {
    await this.page.getByLabel('Save').click();
};
```

Of course, if the component changes in a way that requires us to update our test code, we'd need to update all occurrences. Instead, we can separate it out into a component object, then import it:

```javascript
// Button Component Model
class SaveButton {
    constructor(page) {
        this.page = page;
    };

    async click() {
        await this.page.getByLabel('Save').click();
    };
};

// Page Object A
const saveButton = new SaveButton(page);
saveButton.click();

// Page Object B
const saveButton = new SaveButton(page);
saveButton.click();
```

## Benefits of Component Models

Similar to Page Object Models, some benefits of this approach include reduced duplication, increased maintainability, and usability.

## Caveat

There are a few things to consider if following, or planning to follow this model:

* Not all components are reused, and some may be exclusive to a page. It is up to you whether these should be separated into component models, or defined within a page object
* It is not uncommon for components to be nested (think a button in a header). The granularity of component models is going to be situational
