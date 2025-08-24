# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.0.0] - 2024-01-24

### Added
- **Tailwind CSS v4 Integration** - Complete support for modern utility-first CSS framework
- **Preline UI Components** - Beautiful, accessible UI components with dropdown menus, badges, and avatars
- **Enhanced Responsive Design** - Improved mobile experience with card-style layouts
- **Vanilla JS Demo with Modern Styling** - New comprehensive demo showcasing Preline UI without jQuery
- **Interactive Components** - Clickable status badges, dropdown actions, and responsive elements
- **Modern Build Process** - New npm scripts for Tailwind CSS compilation
- **Comprehensive Documentation** - README-TAILWIND.md with complete integration guide

### Enhanced
- **Mobile Layout** - Card-style responsive design with better readability and spacing
- **Typography** - Consistent font weights, sizes, and spacing using Tailwind utilities
- **Color System** - Modern color palette with proper contrast ratios
- **Component Structure** - Better semantic HTML with ARIA attributes
- **Performance** - Optimized CSS with automatic purging and smaller bundle sizes

### Files Added
- `tailwind.config.js` - Tailwind CSS configuration with Preline UI plugin
- `postcss.config.js` - PostCSS configuration for CSS processing
- `src/css/basictable-tailwind.css` - Tailwind-based responsive table styles
- `dist/css/basictable-tailwind.css` - Compiled development CSS
- `dist/css/basictable-tailwind.min.css` - Minified production CSS
- `demo/preline-demo.html` - jQuery demo with Preline UI components
- `demo/preline-vanilla-demo.html` - Vanilla JS demo with Preline UI components
- `README-TAILWIND.md` - Complete documentation for Tailwind CSS integration
- `CHANGELOG.md` - This changelog file

### Scripts Added
- `build-tailwind` - Build development Tailwind CSS
- `build-tailwind-min` - Build minified production Tailwind CSS
- `build-tailwind-watch` - Watch for changes during development

### Dependencies Added
- `tailwindcss@^4.1.12` - Utility-first CSS framework
- `@tailwindcss/forms@^0.5.7` - Form styling plugin
- `@tailwindcss/cli@^4.1.12` - Tailwind CSS CLI tool
- `preline@^2.5.0` - Modern UI component library
- `postcss@^8.4.32` - CSS transformation tool
- `autoprefixer@^10.4.16` - CSS vendor prefixing

### Features
- **Responsive Breakpoints** - Customizable viewport and container-based breakpoints
- **Interactive Elements** - Status toggles, dropdown menus, and action buttons
- **Modern Styling** - Clean, professional appearance with consistent spacing
- **Accessibility** - Proper ARIA labels and semantic markup
- **Theme Support** - Easily customizable color schemes and typography
- **Component Library** - Reusable UI patterns and components

### Technical Improvements
- **CSS Architecture** - Component-based styling with Tailwind utilities
- **Build Optimization** - Automatic CSS purging for smaller bundle sizes
- **Modern JavaScript** - ES6+ features in Vanilla JS implementation
- **Better Performance** - Reduced dependency footprint without jQuery requirement
- **Maintainable Code** - Utility-first approach for easier customization

### Backwards Compatibility
- **Original API Preserved** - All existing JavaScript API methods remain unchanged
- **Legacy CSS Support** - Original `basictable.css` files remain available
- **Migration Path** - Clear documentation for upgrading to Tailwind CSS version
- **Demo Preservation** - Original demo pages remain functional

### Browser Support
- **Modern Browsers** - Full support for Chrome, Firefox, Safari, Edge
- **Mobile Browsers** - Enhanced touch support and responsive behavior
- **CSS Grid & Flexbox** - Utilizes modern layout methods for better performance
- **Progressive Enhancement** - Graceful degradation for older browsers

### Documentation
- **Installation Guide** - Step-by-step setup instructions
- **Usage Examples** - Both jQuery and Vanilla JS implementations
- **Customization Guide** - How to modify colors, spacing, and components
- **Migration Guide** - Moving from original CSS to Tailwind CSS
- **API Reference** - Complete documentation of all options and methods

## [2.0.5] - Previous Release

### Fixed
- Various bug fixes and improvements
- Updated build process with Terser
- Improved documentation

### Changed
- Distribution files moved to `/dist/` directory
- Minification now uses Terser instead of UglifyJS
- Beautified non-minified versions for better readability

## [2.0.0] - Previous Major Release

### Added
- Vanilla JavaScript version alongside jQuery version
- Improved responsive behavior
- Better browser compatibility

### Changed
- Major refactoring of core functionality
- Improved API consistency between jQuery and Vanilla JS versions

---

## Migration Guide from 2.x to 3.0

### For Existing Users (Original CSS)
Your existing implementation will continue to work without changes. The original CSS and JavaScript files remain available.

### To Upgrade to Tailwind CSS + Preline UI

1. **Install new dependencies:**
   ```bash
   npm install
   ```

2. **Build Tailwind CSS:**
   ```bash
   npm run build-tailwind-min
   ```

3. **Update your HTML:**
   ```html
   <!-- Replace -->
   <link rel="stylesheet" href="basictable.min.css" />
   
   <!-- With -->
   <link rel="stylesheet" href="basictable-tailwind.min.css" />
   ```

4. **Add Preline UI classes to your tables:**
   ```html
   <table class="min-w-full divide-y divide-gray-200">
     <thead class="bg-gray-50">
       <!-- ... -->
     </thead>
     <tbody class="bg-white divide-y divide-gray-200">
       <!-- ... -->
     </tbody>
   </table>
   ```

5. **Initialize Preline UI (if using interactive components):**
   ```javascript
   // After Basic Table initialization
   if (typeof HSStaticMethods !== 'undefined') {
     HSStaticMethods.autoInit();
   }
   ```

For complete migration instructions, see [README-TAILWIND.md](./README-TAILWIND.md).

---

## Contributors

- Original Basic Table library by Jerry Low
- Tailwind CSS + Preline UI integration enhancement

## License

MIT License - see [LICENSE](./LICENSE) file for details.