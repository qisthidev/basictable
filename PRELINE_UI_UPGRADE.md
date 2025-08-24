# Preline UI-Compliant Responsive Table Upgrade - Version 3.0.0

## Overview

This major version upgrade transforms the Basic Table library to focus exclusively on modern Vanilla JavaScript with Preline UI-compliant design patterns. The library now implements a beautiful card-style responsive layout that provides superior mobile user experience while maintaining full desktop functionality.

## Breaking Changes - Version 3.0.0

⚠️ **jQuery Support Removed**: This version drops jQuery entirely to focus on pure JavaScript performance and modern web standards.

### Migration from 2.x to 3.0
- Replace jQuery initialization `$('table').basictable()` with `new basictable('table')`
- Remove jQuery dependency from your project
- Update method calls from `$('table').basictable('method')` to `tableInstance.method()`

## Key Changes Made

### 1. Enhanced CSS (src/css/basictable.css)
- **Card-Style Layout**: Each table row transforms into a beautifully styled card on mobile
- **Modern Design**: Added shadows, rounded corners, and proper spacing
- **Typography Improvements**: Enhanced label styling with proper hierarchy
- **Hover Effects**: Smooth transitions and interactive states
- **Dark Mode Support**: Automatic adaptation using `prefers-color-scheme`
- **Three Style Variants**: Default, compact, and shadow options

### 2. JavaScript Enhancements (src/js/basictable.js)
- **New Options Added**:
  - `cardStyle`: Choose between 'default', 'compact', or 'shadow'
  - `scrollable`: Enable scrolling for tall tables
  - `maxHeight`: Set maximum height with automatic scrolling
- **Enhanced Wrapper Management**: Automatic CSS class application
- **Backward Compatibility**: All existing options and methods remain functional

### 3. Updated Demos
- **Main Demo**: Renamed to `index.html` with comprehensive Preline UI examples
- **New Comparison Demo**: `preline-comparison.html` showing old vs new approaches
- **Real-world Examples**: Customer data, product catalogs, events, and transactions
- **jQuery Demo Removed**: Focus on modern Vanilla JS implementation

### 4. Documentation Updates
- **Updated README.md**: Complete documentation of new features
- **New Options Documented**: Full descriptions and usage examples
- **Feature Comparison**: Benefits of the new approach clearly outlined

## Design Philosophy

### Traditional Approach (Before)
- Simple stacked rows on mobile
- Basic label:value format
- Minimal styling
- Functional but plain appearance

### Preline UI Approach (After)
- Beautiful card-based layout
- Modern shadows and spacing
- Enhanced typography and visual hierarchy
- Smooth hover effects and transitions
- Multiple style variants
- Superior mobile user experience
- Dark mode support

## Usage Examples

### Basic Implementation
```javascript
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'default'
});
```

### Compact Style for Dense Data
```javascript
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'compact'
});
```

### Enhanced Shadows
```javascript
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'shadow'
});
```

### Scrollable Container
```javascript
new basictable('.table', {
  tableWrap: true,
  scrollable: true,
  maxHeight: '400px'
});
```

## Benefits

1. **No Horizontal Scrolling**: Eliminates the need for horizontal scrolling on mobile devices
2. **Enhanced Readability**: Clear visual separation between data items
3. **Modern Design**: Follows current UI/UX best practices
4. **Flexible Styling**: Multiple variants to match different design needs
5. **Accessibility**: Improved contrast ratios and semantic markup
6. **Performance**: Smooth animations and transitions
7. **Responsive**: Seamless adaptation across all screen sizes

## Compatibility

- **Backward Compatible**: All existing options and methods work unchanged
- **Progressive Enhancement**: New features are opt-in
- **Cross-Browser**: Works on all modern browsers
- **Mobile-First**: Optimized for touch interactions

## Files Modified

- `src/css/basictable.css` - Complete responsive design overhaul
- `src/js/basictable.js` - Added new options and wrapper management
- `demo/index.html` - Main demo with Preline UI examples (renamed from vanilla-js.html)
- `demo/preline-comparison.html` - New comparison demo
- `README.md` - Updated documentation focusing on Vanilla JS
- `package.json` - Updated to version 3.0.0, removed jQuery references
- `dist/` - Compiled files updated (jQuery files removed)

## Files Removed

- `src/js/jquery.basictable.js` - jQuery version removed
- `dist/js/jquery.basictable.js` - jQuery compiled version removed
- `dist/js/jquery.basictable.min.js` - jQuery minified version removed
- `demo/jquery.html` - jQuery demo removed

## Testing

The implementation has been tested with:
- Various screen sizes and breakpoints
- Different data types and table structures
- All style variants and options
- Pure Vanilla JS implementation
- Light and dark mode appearances

This upgrade maintains the simplicity and lightweight nature of the original library while providing a modern, Preline UI-compliant responsive experience that significantly improves mobile usability.