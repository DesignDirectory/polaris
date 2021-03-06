---
name: Choice list
category: Forms
keywords:
  - form
  - input
  - choices
  - select
  - group of radio buttons
  - radio button group
  - group of checkboxes
  - group of check boxes
  - list of choices
  - list of radio buttons
  - list of checkboxes
  - list of check boxes
  - multi-choice list
  - single-choice list
---

# Choice list

A choice list lets you create a list of grouped radio buttons or checkboxes.
Use this component if you need to group together a related list of interactive
choices.

---

## Purpose

Think about the merchant problem this component solves when you’re using it:

### Problem

Merchants need to be able to select from a set of options that are related to
one another.

### Solution

Grouping things together in a choice list is a way to visually present options
so that merchants can decide what to select.

---

## Best practices

Choice lists should:

* Include a title that tells the merchant what to do or explains the available options
* Label options clearly based on what the option will do
* Avoid mutually exclusive options when allowing multiple selection

---

## Content guidelines

### List titles

List titles should:

* Help merchants understand how the items in the list are grouped together, or
should explain what kind of choice the merchant is making

<!-- usagelist -->
#### Do
Pick a shipping method

#### Don’t
Pick one
<!-- end -->

* Be concise and scannable:
  * Use simple, clear language that can be read at a glance
  * Keep list titles to a single sentence
  * It the title introduces the list, it should end with a colon
  * Should be written in sentence case

<!-- usagelist -->
#### Do
Shipping options

#### Don’t
Shipping Options
<!-- end -->

* Not use colons

<!-- usageblock -->
#### Do
If the customer abandons their checkout, send them an email reminder to complete their order

<input type="radio" name="foo"> Never
<input type="radio" name="foo"> 6 hours later
<input type="radio" name="foo"> 24 hours later

#### Don’t
If the customer abandons their checkout, send them an email reminder to complete their order:

<input type="radio" name="foo"> Never
<input type="radio" name="foo"> 6 hours later
<input type="radio" name="foo"> 24 hours later
<!-- end -->

### List choices

Every item in a choice list should:

* Start with a capital letter

<!-- usageblock -->
#### Do
- Option 1
- Option 2
- Option 3

#### Don’t
- option 1
- option 2
- option 3
<!-- end -->

* Not use commas or semicolons at the end of each line

<!-- usageblock -->
#### Do
- Red
- Yellow
- Blue

#### Don’t
- Red;
- Yellow;
- Blue.
<!-- end -->

* Be written in sentence case (the first word capitalized, the rest lowercase)

<!-- usageblock -->
#### Do
- Item one
- Item two
- Item three

#### Don’t
- Item One
- Item Two
- Item Three
<!-- end -->

### Helper text and descriptions

If your list contains helper text, only the description below the list item should contain punctuation.

| Prop | Type | Description |
| ---- | ---- | ----------- |
| title | string | Label for list of choices |
| choices* | Choice[] | Collection of choices |
| selected* | string[] | Collection of selected choices |
| name | string | Name for form input |
| allowMultiple | boolean | Allow merchants to select multiple options at once |
| titleHidden | boolean | Toggles display of the title |
| onChange | function(selected: string[], name: string) | Callback when the selected choices change |

## Examples

### Single choice list

Use when you need merchants to make a single selection from a list of choices.

```jsx
<ChoiceList
  title="Company name"
  choices={[
    {label: 'Hidden', value: 'hidden'},
    {label: 'Optional', value: 'optional'},
    {label: 'Required', value: 'required'},
  ]}
  selected={['hidden']}
/>
```

### Multi-choice list

Use when to let merchants make multiple sections from a list of choices.

```jsx
<ChoiceList
  allowMultiple
  title="While the customer is checking out"
  choices={[
    {
      label: 'Use the shipping address as the billing address by default',
      value: 'shipping',
      helpText: 'Reduces the number of fields required to check out. The billing address can still be edited.',
    },
    {
      label: 'Require a confirmation step',
      value: 'confirmation',
      helpText: 'Customers must review their order details before purchasing.',
    },
  ]}
  selected={['shipping']}
/>
```

---

## Related components

* To present a long list of radio buttons or when space is constrained, [use the select component](/components/forms/select)
* To build a group of radio buttons or checkboxes with a custom layout, use the [radio button component](/components/forms/radio-button) or [checkbox component](/components/forms/checkbox)
* To display a simple, non-interactive list of related content, [use the list component](/components/lists/list)
