# Basic Table + Tailwind CSS + Preline UI Integration

This document describes how to use Basic Table with modern Tailwind CSS styling and Preline UI components.

## What's New

The Basic Table library has been enhanced with:
- **Tailwind CSS v4 support** - Modern utility-first CSS framework
- **Preline UI integration** - Beautiful, accessible UI components
- **Enhanced responsive design** - Improved mobile experience with card-like layouts
- **Modern styling** - Clean, professional appearance with proper spacing and typography

## Quick Start

### Installation

1. **Install dependencies:**
```bash
npm install
```

2. **Build the Tailwind CSS:**
```bash
npm run build-tailwind-min
```

3. **Include the files in your HTML:**
```html
<!-- Tailwind CSS with Basic Table styles -->
<link rel="stylesheet" type="text/css" href="dist/css/basictable-tailwind.min.css" />

<!-- jQuery -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<!-- Basic Table jQuery Plugin -->
<script type="text/javascript" src="dist/js/jquery.basictable.min.js"></script>
<!-- Preline UI -->
<script src="node_modules/preline/preline.js"></script>
```

### Basic Usage

```html
<table class="preline-table min-w-full divide-y divide-gray-200">
  <thead class="bg-gray-50">
    <tr>
      <th scope="col" class="px-6 py-3 text-start text-xs font-medium text-gray-500 uppercase tracking-wider">Name</th>
      <th scope="col" class="px-6 py-3 text-start text-xs font-medium text-gray-500 uppercase tracking-wider">Email</th>
      <th scope="col" class="px-6 py-3 text-start text-xs font-medium text-gray-500 uppercase tracking-wider">Role</th>
    </tr>
  </thead>
  <tbody class="bg-white divide-y divide-gray-200">
    <tr class="hover:bg-gray-50">
      <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">John Doe</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">john@example.com</td>
      <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Admin</td>
    </tr>
  </tbody>
</table>
```

```javascript
$(document).ready(function() {
  $('.preline-table').basictable();
  
  // Initialize Preline UI components
  if (typeof HSStaticMethods !== 'undefined') {
    HSStaticMethods.autoInit();
  }
});
```

## Features

### Responsive Design
- **Card-style layout** on mobile devices
- **Enhanced readability** with proper spacing and typography
- **Label display** showing column headers in mobile view
- **Smooth transitions** between desktop and mobile layouts

### Preline UI Components
- **Dropdown menus** for table actions
- **Status badges** with color coding
- **User avatars** and profile information
- **Modern buttons** and form elements
- **Consistent spacing** and typography

### Tailwind CSS Benefits
- **Utility-first approach** for easy customization
- **Responsive utilities** built-in
- **Consistent design system** with color palette
- **Small bundle size** with purging unused styles
- **Modern CSS features** like CSS Grid and Flexbox

## Configuration

### Tailwind Configuration

The project includes a `tailwind.config.js` file with Preline UI integration:

```javascript
module.exports = {
  content: [
    "./src/**/*.{html,js}",
    "./demo/**/*.{html,js}",
    "./dist/**/*.{html,js}",
    './node_modules/preline/preline.js',
  ],
  theme: {
    extend: {
      colors: {
        primary: {
          50: '#f0f9ff',
          100: '#e0f2fe',
          // ... custom color palette
        }
      }
    },
  },
  plugins: [
    require('@tailwindcss/forms'),
    require('preline/plugin'),
  ],
}
```

### Build Scripts

Available npm scripts:

```bash
# Build development CSS
npm run build-tailwind

# Build minified CSS for production
npm run build-tailwind-min

# Watch for changes during development
npm run build-tailwind-watch

# Build everything (JS + CSS)
npm run compile
```

## Advanced Usage

### Custom Breakpoints

```javascript
$('#my-table').basictable({
  breakpoint: 768  // Custom breakpoint in pixels
});
```

### Container-based Responsive

```javascript
$('#my-table').basictable({
  containerBreakpoint: 485  // Based on container width instead of viewport
});
```

### With Preline UI Dropdowns

```html
<td class="px-6 py-4 whitespace-nowrap text-end text-sm font-medium">
  <div class="hs-dropdown relative inline-flex">
    <button type="button" class="hs-dropdown-toggle py-1.5 px-2 inline-flex items-center gap-x-2 text-sm font-medium rounded-lg border border-gray-200 bg-white text-gray-800 shadow-sm hover:bg-gray-50">
      Actions
      <svg class="hs-dropdown-open:rotate-180 w-4 h-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <path d="m6 9 6 6 6-6"/>
      </svg>
    </button>
    <div class="hs-dropdown-menu transition-[opacity,margin] duration hs-dropdown-open:opacity-100 opacity-0 hidden min-w-[8rem] bg-white shadow-md rounded-lg p-2 mt-2">
      <a class="flex items-center gap-x-3.5 py-2 px-3 rounded-lg text-sm text-gray-800 hover:bg-gray-100" href="#">Edit</a>
      <a class="flex items-center gap-x-3.5 py-2 px-3 rounded-lg text-sm text-gray-800 hover:bg-gray-100" href="#">View</a>
      <a class="flex items-center gap-x-3.5 py-2 px-3 rounded-lg text-sm text-red-600 hover:bg-gray-100" href="#">Delete</a>
    </div>
  </div>
</td>
```

## Customization

### Custom Styling

You can customize the appearance by modifying the CSS in `src/css/basictable-tailwind.css`:

```css
@layer components {
  /* Customize label styling */
  .bt tfoot th::before,
  .bt tfoot td::before,
  .bt tbody td::before {
    background-color: #3b82f6; /* Custom blue background */
    color: white;
    /* ... other custom styles */
  }
}
```

### Color Themes

Modify the Tailwind config to use your brand colors:

```javascript
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
```

## Browser Support

- Modern browsers with CSS Grid and Flexbox support
- Mobile browsers with touch support
- IE11+ (with appropriate polyfills)

## Demo

Check out the comprehensive demo at:
- **Preline UI Demo**: `demo/preline-demo.html`
- **Original jQuery Demo**: `demo/jquery.html`
- **Vanilla JS Demo**: `demo/vanilla-js.html`

## Migration from Original CSS

If you're migrating from the original `basictable.css`:

1. Replace the CSS file reference:
   ```html
   <!-- Before -->
   <link rel="stylesheet" type="text/css" href="basictable.min.css" />
   
   <!-- After -->
   <link rel="stylesheet" type="text/css" href="basictable-tailwind.min.css" />
   ```

2. Update your table markup to use Preline UI classes:
   ```html
   <!-- Add modern styling classes -->
   <table class="min-w-full divide-y divide-gray-200">
     <thead class="bg-gray-50">
       <!-- ... -->
     </thead>
     <tbody class="bg-white divide-y divide-gray-200">
       <!-- ... -->
     </tbody>
   </table>
   ```

3. Initialize Preline UI components:
   ```javascript
   // Add after Basic Table initialization
   if (typeof HSStaticMethods !== 'undefined') {
     HSStaticMethods.autoInit();
   }
   ```

## Contributing

To contribute to the Tailwind CSS integration:

1. Modify styles in `src/css/basictable-tailwind.css`
2. Run `npm run build-tailwind` to compile
3. Test with the demo pages
4. Submit a pull request

## License

Same as the original Basic Table library - MIT License.