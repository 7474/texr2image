# Source Modules

This directory contains the core logic extracted from `index.html` for testability.

## Modules

### markdownProcessor.js
Contains functions for processing and normalizing Markdown text:
- `normalizeMultibyteEmphasis(text)`: Normalizes emphasis markers for multibyte characters

### viewportManager.js
Contains functions for managing viewport dimensions:
- `getViewportDimensions(selectedSize)`: Parses and validates viewport size strings

### breakpointCalculator.js
Contains functions for calculating optimal break points when splitting content across multiple images:
- `findOptimalBreakPoints(container, targetHeight, totalHeight)`: Finds optimal break points to avoid splitting elements
- Constants: `MIN_CONTENT_RATIO`, `MAX_CONTENT_RATIO`

## Usage

These modules are designed to work both in Node.js (for testing with Jest) and in the browser (loaded via script tags in `index.html`).

### In Browser
```html
<script src="src/markdownProcessor.js"></script>
<script src="src/viewportManager.js"></script>
<script src="src/breakpointCalculator.js"></script>
```

### In Node.js/Jest
```javascript
const { normalizeMultibyteEmphasis } = require('./src/markdownProcessor');
const { getViewportDimensions } = require('./src/viewportManager');
const { findOptimalBreakPoints } = require('./src/breakpointCalculator');
```

## Testing

Run unit tests:
```bash
npm test
```

Run with coverage:
```bash
npm run test:coverage
```

Watch mode for development:
```bash
npm run test:watch
```
