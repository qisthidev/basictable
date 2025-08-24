# Basic Table v3.0.0 Release Notes

**Release Date:** January 24, 2024

## 🎉 Major New Features

### Tailwind CSS v4 Integration
Basic Table now includes full support for **Tailwind CSS v4**, bringing modern utility-first styling to your responsive tables. This integration provides:

- **Utility-First Approach** - Build custom designs with pre-built utility classes
- **Responsive Design** - Built-in responsive utilities for all screen sizes
- **Consistent Design System** - Standardized spacing, colors, and typography
- **Optimized Performance** - Automatic CSS purging for smaller bundle sizes

### Preline UI Components
Enhanced with **Preline UI**, a beautiful and accessible component library:

- **Interactive Dropdowns** - Action menus with smooth animations
- **Status Badges** - Color-coded status indicators with proper contrast
- **User Avatars** - Professional profile components
- **Modern Buttons** - Consistent button styling across all components
- **Accessibility First** - ARIA labels and keyboard navigation support

### Enhanced Mobile Experience
Complete redesign of the mobile responsive behavior:

- **Card-Style Layout** - Tables transform into elegant card layouts on mobile
- **Better Readability** - Improved spacing and typography for mobile screens
- **Enhanced Labels** - Styled column labels that are easier to read
- **Smooth Transitions** - Seamless transitions between desktop and mobile views

## 🚀 What's New

### New Demo Pages
- **`demo/preline-demo.html`** - jQuery version with Preline UI components
- **`demo/preline-vanilla-demo.html`** - Vanilla JS version with interactive elements
- Both demos showcase real-world usage patterns and interactive features

### New Build System
```bash
# Development CSS
npm run build-tailwind

# Production CSS (minified)
npm run build-tailwind-min

# Watch for changes during development
npm run build-tailwind-watch

# Build everything (JS + CSS)
npm run compile
```

### New Files Structure
```
├── tailwind.config.js              # Tailwind CSS configuration
├── postcss.config.js               # PostCSS configuration
├── src/css/basictable-tailwind.css # Tailwind source styles
├── dist/css/basictable-tailwind.css # Compiled development CSS
├── dist/css/basictable-tailwind.min.css # Minified production CSS
├── demo/preline-demo.html          # jQuery + Preline UI demo
├── demo/preline-vanilla-demo.html  # Vanilla JS + Preline UI demo
├── README-TAILWIND.md              # Complete integration guide
└── CHANGELOG.md                    # Detailed changelog
```

## 🔧 Technical Improvements

### Modern CSS Architecture
- **Component-based styling** using Tailwind's `@layer` directive
- **CSS Grid and Flexbox** for better layout performance
- **Custom properties** for theme customization
- **Responsive utilities** built into the framework

### Enhanced JavaScript
- **ES6+ features** in Vanilla JS implementation
- **Event delegation** for better performance
- **Modular architecture** for easier maintenance
- **Interactive examples** with real functionality

### Performance Optimizations
- **Smaller bundle sizes** with CSS purging
- **Faster loading** without jQuery dependency (Vanilla JS version)
- **Modern browser optimizations** using latest CSS features
- **Efficient responsive behavior** with container queries support

## 📦 Installation & Usage

### Quick Start (New Projects)
```bash
# Install dependencies
npm install

# Build Tailwind CSS
npm run build-tailwind-min
```

### HTML Setup
```html
<!-- Include Tailwind CSS with Basic Table styles -->
<link rel="stylesheet" href="dist/css/basictable-tailwind.min.css" />

<!-- Basic Table JavaScript -->
<script src="dist/js/basictable.min.js"></script>
<!-- OR jQuery version -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script src="dist/js/jquery.basictable.min.js"></script>

<!-- Preline UI (for interactive components) -->
<script src="node_modules/preline/preline.js"></script>
```

### Basic Implementation
```html
<table class="min-w-full divide-y divide-gray-200">
  <thead class="bg-gray-50">
    <tr>
      <th class="px-6 py-3 text-start text-xs font-medium text-gray-500 uppercase tracking-wider">Name</th>
      <th class="px-6 py-3 text-start text-xs font-medium text-gray-500 uppercase tracking-wider">Email</th>
    </tr>
  </thead>
  <tbody class="bg-white divide-y divide-gray-200">
    <tr class="hover:bg-gray-50">
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">John Doe</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">john@example.com</td>
    </tr>
  </tbody>
</table>
```

```javascript
// Vanilla JS
const table = document.querySelector('table');
new BasicTable(table);

// OR jQuery
$('table').basictable();

// Initialize Preline UI components
if (typeof HSStaticMethods !== 'undefined') {
  HSStaticMethods.autoInit();
}
```

## 🔄 Migration Guide

### From v2.x to v3.0 (Existing Users)
**Good news:** Your existing implementation continues to work without changes!

- Original CSS files (`basictable.css`, `basictable.min.css`) are preserved
- All JavaScript APIs remain identical
- Original demo pages are still functional
- No breaking changes to existing functionality

### Upgrading to Tailwind CSS (Optional)
To take advantage of the new styling:

1. **Install new dependencies:** `npm install`
2. **Build Tailwind CSS:** `npm run build-tailwind-min`
3. **Replace CSS file:** Change `basictable.min.css` to `basictable-tailwind.min.css`
4. **Update HTML classes:** Add Preline UI classes to your tables
5. **Initialize Preline UI:** Add `HSStaticMethods.autoInit()` if using interactive components

Detailed migration instructions: [README-TAILWIND.md](./README-TAILWIND.md)

## 📊 Comparison: Original vs Tailwind CSS

| Feature | Original CSS | Tailwind CSS + Preline UI |
|---------|-------------|---------------------------|
| Bundle Size | ~1KB CSS | ~14KB CSS (with utilities) |
| Mobile Layout | List-style | Card-style |
| Customization | Limited | Extensive with utilities |
| Interactive Components | None | Dropdowns, badges, buttons |
| Typography | Basic | Professional with system fonts |
| Color System | Fixed | Extensive palette |
| Accessibility | Basic | Enhanced with ARIA |
| Build Process | CSS minification | Modern CSS with purging |

## 🌟 Interactive Features

### Status Badges
```html
<span class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-medium bg-green-100 text-green-800">
  Active
</span>
```

### Dropdown Menus
```html
<div class="hs-dropdown relative inline-flex">
  <button class="hs-dropdown-toggle py-1.5 px-2 inline-flex items-center gap-x-2 text-sm font-medium rounded-lg border border-gray-200 bg-white text-gray-800 shadow-sm hover:bg-gray-50">
    Actions
  </button>
  <div class="hs-dropdown-menu transition-[opacity,margin] duration hs-dropdown-open:opacity-100 opacity-0 hidden min-w-[8rem] bg-white shadow-md rounded-lg p-2 mt-2">
    <a class="flex items-center gap-x-3.5 py-2 px-3 rounded-lg text-sm text-gray-800 hover:bg-gray-100" href="#">Edit</a>
    <a class="flex items-center gap-x-3.5 py-2 px-3 rounded-lg text-sm text-gray-800 hover:bg-gray-100" href="#">View</a>
  </div>
</div>
```

### User Profiles
```html
<div class="flex items-center">
  <div class="flex-shrink-0 h-10 w-10">
    <div class="h-10 w-10 rounded-full bg-blue-500 flex items-center justify-center text-white font-semibold">JS</div>
  </div>
  <div class="ml-4">
    <div class="text-sm font-medium text-gray-900">John Smith</div>
    <div class="text-sm text-gray-500">Designer</div>
  </div>
</div>
```

## 🎨 Customization

### Theme Colors
Modify `tailwind.config.js` to customize the color palette:

```javascript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: {
          500: '#your-brand-color',
          // ... other shades
        }
      }
    }
  }
}
```

### Responsive Breakpoints
```javascript
// Custom viewport breakpoint
new BasicTable(table, {
  breakpoint: 768
});

// Container-based breakpoint
new BasicTable(table, {
  containerBreakpoint: 485
});
```

### Custom Styling
Override styles in your CSS:

```css
@layer components {
  .bt tfoot th::before,
  .bt tfoot td::before,
  .bt tbody td::before {
    background-color: #your-color;
    /* ... custom styles */
  }
}
```

## 📱 Browser Support

- **Chrome** 90+ ✅
- **Firefox** 88+ ✅
- **Safari** 14+ ✅
- **Edge** 90+ ✅
- **iOS Safari** 14+ ✅
- **Android Chrome** 90+ ✅

**Legacy Support:** IE11+ with appropriate polyfills

## 🔗 Resources

- **Documentation:** [README-TAILWIND.md](./README-TAILWIND.md)
- **Changelog:** [CHANGELOG.md](./CHANGELOG.md)
- **jQuery Demo:** [demo/preline-demo.html](./demo/preline-demo.html)
- **Vanilla JS Demo:** [demo/preline-vanilla-demo.html](./demo/preline-vanilla-demo.html)
- **GitHub Repository:** [https://github.com/jerrylow/basictable](https://github.com/jerrylow/basictable)

## 🙏 Acknowledgments

- **Original Basic Table library** by Jerry Low
- **Tailwind CSS** team for the amazing utility-first framework
- **Preline UI** for beautiful, accessible components
- **Community** for feedback and feature requests

## 📞 Support

If you encounter any issues with the new Tailwind CSS integration:

1. Check the [migration guide](./README-TAILWIND.md)
2. Review the [demo pages](./demo/) for implementation examples
3. Open an issue on [GitHub](https://github.com/jerrylow/basictable/issues)

---

**Enjoy building beautiful, responsive tables with Basic Table v3.0.0!** 🎉