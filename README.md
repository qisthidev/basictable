# Basic Table

A simple lightweight Vanilla JS responsive table library with modern Preline UI-compliant card-style design. Transform your tables into beautiful, responsive layouts that become stylish cards on mobile devices. Utilizing modern responsive design techniques that prioritize readability and user experience across all screen sizes.

**[View Demo](demo/index.html)**

**[View Preline UI Comparison](demo/preline-comparison.html)**

## Version 3.0.0 - Vanilla JS Only

Starting with version 3.0.0, Basic Table focuses exclusively on Vanilla JavaScript, dropping jQuery dependency for better performance and modern web development practices.

### Key Changes:
- **jQuery version removed** - Focusing on pure JavaScript for better performance
- **Preline UI-compliant design** - Modern card-style responsive layout
- **Enhanced mobile experience** - No horizontal scrolling required
- **Multiple style variants** - Default, compact, and shadow options
- **Dark mode support** - Automatic adaptation to user preferences

## Getting Started

Include the CSS and basictable library in the `<head>` of your page.

```html
<link rel="stylesheet" type="text/css" href="basictable.min.css" />
<script type="text/javascript" src="basictable.min.js"></script>
```

Initiate on any table(s) with:

```javascript
new basictable('table');
```

## Quick Example

```html
<table class="data-table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Email</th>
      <th>Plan</th>
      <th>Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>John Smith</td>
      <td>john@example.com</td>
      <td>Premium</td>
      <td>Active</td>
    </tr>
    <!-- more rows -->
  </tbody>
</table>

<script>
new basictable('.data-table', {
  tableWrap: true,
  cardStyle: 'default'
});
</script>
```

## Options

### breakpoint

`integer` `default: null`

Define the breakpoint (viewport's width) when the table will engage in responsive mode. If the `containerBreakpoint` is `null` (which is the default) the value will be 568px.

### containerBreakpoint

`integer` `default: null`

Define the breakpoint of the table's container when the table will engage in responsive mode.

### contentWrap

`boolean` `default: true`

Wraps the original content within the cell in a span with class .bt-content, to help with CSS selection.

### forceResponsive

`boolean` `default: true`

The library will always force the table into responsive mode once the breakpoint is met. If this is set to false the table will only change mode when the table itself is larger than its immediate parent's inner width.

### noResize

`boolean` `default: false`

Disable Basic Table's JS resize. The table won't engage in responsive mode unless media query or another resize bind outside of Basic Table is defined.

### tableWrap

`boolean` `default: false`

When the library is initialize create a div wrapper around the table with class .bt-wrapper. This wrapper will toggle an active class when the table mode changes.

### showEmptyCells

`boolean` `default: false`

When true, empty cells will be shown.

### header

`boolean` `default: true`

Set to false if table does not have a header row. Table will just be responsive with table body and optional footer.

### cardStyle

`string` `default: 'default'`

Choose the card style for responsive mode. Options are:
- `'default'` - Standard card styling with modern shadows and spacing
- `'compact'` - Reduced padding and spacing for tables with many rows
- `'shadow'` - Enhanced shadows for a more elevated appearance
- `'inline'` - Compact inline format where labels and values appear on the same line

### scrollable

`boolean` `default: false`

Enable scrolling within the table container when in responsive mode. Useful for tables with many rows.

### maxHeight

`string` `default: null`

Set a maximum height for the table container in responsive mode (e.g., '300px', '50vh'). Automatically enables scrollable behavior.

### inlineSeparator

`string` `default: 'colon'`

Choose the separator style for inline card mode. Options are:
- `'colon'` - Uses colon separator (e.g., "Name: John Doe")
- `'equal'` - Uses equal sign separator (e.g., "Name = John Doe")
- `'none'` - No separator, just space (e.g., "Name John Doe")

## Methods

Methods demonstrated assuming you've defined the object as `table`.

```javascript
const table = new basictable('.table');
```

### start

Engage the table in responsive mode. This method can only run after the table has been initialized.

```js
table.start();
```

### stop

Toggle the table back to normal mode, removing the responsive look. This does not destory the Basic Table data and wrappers. The table will still work once the breakpoint is met.

```js
table.stop();
```

### destroy

Destroy the the responsive bind on the table. This will remove all data and generated wrappers from the table, returning it to its initial state.

```js
table.destroy();
```

### restart

Run `destroy`, `setup` then `check` without resetting the table data. Run this if the table dynamically updates.

```js
table.restart();
```

## Preline UI-Compliant Design Features

### Card-Style Responsive Layout

This library now features modern card-style responsive design that follows Preline UI patterns:

- **Traditional table on desktop/large screens** - Full horizontal layout with all columns visible
- **Card-style layout on mobile** - Each row transforms into a styled card with proper spacing, shadows, and typography
- **No horizontal scrolling** - Eliminates the need for users to scroll horizontally on small screens
- **Enhanced readability** - Field labels are clearly displayed above their values in mobile view

### Styling Options

Choose from multiple card styles to match your design:

```javascript
// Default card style
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'default'
});

// Compact cards for dense data
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'compact'
});

// Enhanced shadows for elevated appearance
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'shadow'
});

// Inline format - labels and values on same line
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'inline'
});

// Inline with equal sign separator
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'inline',
  inlineSeparator: 'equal'
});

// Inline with no separator
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'inline',
  inlineSeparator: 'none'
});
```

### Scrollable Containers

For tables with many rows, enable scrolling within the responsive container:

```javascript
new basictable('.table', {
  tableWrap: true,
  scrollable: true,
  maxHeight: '400px'
});
```

### Dark Mode Support

The card-style design includes automatic dark mode support using CSS `prefers-color-scheme` media queries.

### Modern Features

- **Smooth transitions** - Hover effects and state changes are animated
- **Accessible design** - Proper contrast ratios and semantic markup
- **Mobile-first approach** - Optimized for touch interactions
- **Flexible typography** - Scales appropriately across devices
