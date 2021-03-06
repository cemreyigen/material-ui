---
title: Snackbar React component
components: Snackbar, SnackbarContent
---

# Snackbar

<p class="description">Snackbars provide brief messages about app processes. The component is also known as a toast.</p>

[Snackbars](https://material.io/design/components/snackbars.html) inform users of a process that an app has performed or will perform. They appear temporarily, towards the bottom of the screen. They shouldn’t interrupt the user experience, and they don’t require user input to disappear.

Snackbars contain a single line of text directly related to the operation performed.
They may contain a text action, but no icons. You can use them to display notifications.

#### Frequency

Only one snackbar may be displayed at a time.

## Simple snackbars

A basic snackbar that aims to reproduce Google Keep's snackbar behavior.

{{"demo": "pages/components/snackbars/SimpleSnackbar.js"}}

## Customized snackbars

Here are some examples of customizing the component. You can learn more about this in the
[overrides documentation page](/customization/components/).

{{"demo": "pages/components/snackbars/CustomizedSnackbars.js"}}

## Positioned snackbars

There may be circumstances when the placement of the snackbar needs to be more flexible.

{{"demo": "pages/components/snackbars/PositionedSnackbar.js"}}

## Message Length

Some snackbars with varying message length.

{{"demo": "pages/components/snackbars/LongTextSnackbar.js"}}

## Transitions

### Consecutive Snackbars

When multiple snackbar updates are necessary, they should appear one at a time.

{{"demo": "pages/components/snackbars/ConsecutiveSnackbars.js"}}

### Snackbars and floating action buttons (FABs)

Snackbars should appear above FABs (on mobile).

{{"demo": "pages/components/snackbars/FabIntegrationSnackbar.js", "iframe": true, "maxWidth": 500}}

### Change Transition

[Grow](/components/transitions/#grow) is the default transition but you can use a different one.

{{"demo": "pages/components/snackbars/TransitionsSnackbar.js"}}

### Control Slide direction

You can change the direction of the [Slide](/components/transitions/#slide) transition.

{{"demo": "pages/components/snackbars/DirectionSnackbar.js"}}

## Complementary projects

For more advanced use cases you might be able to take advantage of:

### notistack

![stars](https://img.shields.io/github/stars/iamhosseindhv/notistack.svg?style=social&label=Stars)
![npm downloads](https://img.shields.io/npm/dm/notistack.svg)

This example demonstrates how to use [notistack](https://github.com/iamhosseindhv/notistack).
notistack has an **imperative API** that makes it easy to display snackbars, without having to handle their open/close state.
It also enables you to **stack** them on top of one another (although this is discouraged by the Material Design specification).

{{"demo": "pages/components/snackbars/IntegrationNotistack.js", "defaultCodeOpen": false}}

## Accessibility

(WAI-ARIA: https://www.w3.org/TR/wai-aria-1.1/#alert)

- Since alerts are not required to receive focus, content authors should not require users to close a Snackbar if the role is set to `alert` through the SnackbarContent `role` prop. This is the default role.
- If a Snackbar requires focus to close it, then content authors should use the `role` of `alertdialog`.

```jsx
<SnackbarContent
  message="This is a Snackbar message."
  role="alert"
/>
```

```jsx
<Snackbar
  ContentProps={{
    'aria-describedby': 'snackbar-fab-message-id',
    'role': 'alertdialog',
  }}
  message={<span id="snackbar-fab-message-id">Archived</span>}
  action={
    <Button color="inherit" size="small">
      Undo
    </Button>
  }
/>
```
