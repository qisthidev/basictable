# BasicTable v3.1.0 Release Notes

## 🎉 What's New in v3.1.0

This release focuses on **API simplification** and **bug fixes** to make BasicTable even easier to use and more reliable.

### 🚀 Key Changes

#### API Simplification
- **Removed Equal Separator Option**: The `inlineSeparator: 'equal'` option has been removed to simplify the API
- **Streamlined Choices**: Now only supports two separator styles:
  - `'colon'` (default): "Field: Value" 
  - `'none'`: "Field Value"

#### Bug Fixes
- **Fixed Double Separator Bug**: Resolved issue where nested `.bt-content` spans caused duplicate separators to appear
- **Improved CSS Specificity**: Updated selectors to use direct child combinator for more precise styling

#### Visual Improvements  
- **Consistent Alignment**: Default colon separator now uses the same 6rem min-width as other separators for perfect alignment
- **Cleaner Spacing**: Removed unnecessary margin-bottom from base label selectors

### 🔧 Migration Guide

If you were using the equal separator option:

```javascript
// ❌ This no longer works
new basictable('.table', {
  cardStyle: 'inline',
  inlineSeparator: 'equal'  // REMOVED
});

// ✅ Use one of these instead
new basictable('.table', {
  cardStyle: 'inline',
  inlineSeparator: 'colon'  // Default - shows "Field: Value"
});

// OR
new basictable('.table', {
  cardStyle: 'inline', 
  inlineSeparator: 'none'   // Shows "Field Value"
});
```

### 💡 Why This Change?

The equal separator was creating alignment complexity and the double separator bug. By removing it, we've:
- Simplified the API surface
- Eliminated the CSS specificity issues that caused the bug
- Made the library more maintainable
- Provided cleaner, more predictable styling

### 🛠️ Technical Details

**Files Updated:**
- CSS: Removed `bt-inline-equal` class and related styles
- JavaScript: Simplified separator logic
- Documentation: Updated README and demo examples

**Breaking Changes:**
- `inlineSeparator: 'equal'` option is no longer supported
- `bt-inline-equal` CSS class removed

### 📦 Installation

```bash
npm install basictable@3.1.0
```

Or include via CDN:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/basictable@3.1.0/dist/css/basictable.min.css">
<script src="https://cdn.jsdelivr.net/npm/basictable@3.1.0/dist/js/basictable.min.js"></script>
```

### 🙏 Acknowledgments

Special thanks to the community for reporting the double separator bug and helping identify areas for API improvement.

---

**Full Changelog**: [v3.0.0...v3.1.0](https://github.com/jerrylow/basictable/compare/v3.0.0...v3.1.0)