# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [3.1.0] - 2025-01-24

### Changed
- **BREAKING:** Removed equal sign separator option (`inlineSeparator: 'equal'`) to simplify API
- Simplified separator logic to only support colon (`:`) and none separators
- Updated default colon separator alignment to match consistent 6rem min-width
- Removed `margin-bottom: 0.25rem` from base label selectors for cleaner spacing

### Fixed
- Fixed double separator bug where nested `.bt-content` spans caused duplicate separators
- Updated CSS selectors to use direct child combinator (`>`) to prevent nested element styling

### Removed
- Equal sign separator styling (`bt-inline-equal` class and related CSS)
- Equal separator JavaScript logic and class application
- Equal separator documentation and demo examples

### Migration Guide
If you were using `inlineSeparator: 'equal'`, you have two options:
1. Use `inlineSeparator: 'colon'` (default) for "Field: Value" format
2. Use `inlineSeparator: 'none'` for "Field Value" format

## [3.0.0] - 2025-01-20

### Added
- Complete rewrite to vanilla JavaScript (removed jQuery dependency)
- Preline UI-compliant design system
- Modern card-style responsive design for mobile devices
- Inline card style with separator options (colon, equal, none)
- Multiple card style variants: default, compact, shadow, inline
- Dark mode support with CSS media queries
- Improved accessibility with semantic HTML structure
- Enhanced demo page with modern styling

### Changed
- **BREAKING:** Removed jQuery dependency - now pure vanilla JS
- **BREAKING:** Updated API structure and options
- **BREAKING:** Changed CSS class naming convention
- Modernized build process with terser and uglifycss
- Updated responsive breakpoint handling
- Improved table wrapper and scrolling behavior

### Removed
- **BREAKING:** jQuery dependency
- Legacy CSS and JavaScript patterns
- Old API methods and options

## [2.1.0] - 2024-XX-XX

### Added
- Additional responsive table features

## [2.0.4] - 2024-XX-XX

### Fixed
- Dependency management improvements
- Moved development dependencies to devDependencies

---

## Migration from v2.x to v3.x

BasicTable v3.0.0 introduces breaking changes due to the removal of jQuery dependency and API modernization:

### Key Changes:
1. **No jQuery Required**: Pure vanilla JavaScript implementation
2. **New API**: Updated constructor and options structure
3. **CSS Classes**: New Preline UI-compliant class naming
4. **Modern Features**: Card-style responsive design, dark mode, inline layouts

### Before (v2.x):
```javascript
$('.table').basictable();
```

### After (v3.x):
```javascript
new basictable('.table', {
  tableWrap: true,
  cardStyle: 'default'
});
```

Please refer to the [README.md](README.md) for complete documentation and examples.