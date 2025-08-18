# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

Theme Customizer is a web-based tool for customizing app themes with real-time color palette generation. It's a static web application built with pure HTML, CSS, and JavaScript (no dependencies or build system).

## Architecture

### File Structure
- `index.html` - Single-page application containing all HTML, CSS, and JavaScript
- `README.md` - Project documentation

### Core Components
The application is structured as a single `ThemeCustomizer` class that manages:

1. **Color Picker Interface**: Interactive gradient slider with draggable handle
2. **Color Conversion System**: HSL/Hex color space manipulation for consistent relationships
3. **Theme Generation Engine**: Algorithmic generation of 6 semantic colors for light/dark themes
4. **Real-time UI Updates**: Dynamic DOM manipulation to show color changes instantly

### Color Palette System
For any base color, generates 6 semantic colors:
- **AccentPrimary**: Base/primary accent color
- **AccentLowContrast**: Subtle accent variation
- **BackgroundPrimary**: Main background color  
- **BackgroundSecondary**: Secondary background
- **ContentPrimary**: High contrast text
- **ContentSecondary**: Medium contrast text

### Key Algorithms
- **Color interpolation**: Linear interpolation across predefined gradient stops
- **HSL manipulation**: Lightness/saturation adjustments for theme variants
- **Position mapping**: Maps slider position to color values

## Development Commands

### Running the Application
```bash
# Using Python (recommended)
python3 -m http.server 8000

# Using Node.js (if http-server is installed globally)
npx http-server -p 8000

# Then open http://localhost:8000 in browser
```

### Testing the Application
```bash
# Open in browser for manual testing
open index.html

# Or serve locally and test responsive design
python3 -m http.server 8000 && open http://localhost:8000
```

## Code Architecture Details

### Event Handling System
- **Mouse Events**: Drag and click handling for color picker interaction
- **Real-time Updates**: Immediate theme generation on color changes
- **State Management**: Current color tracking with reset functionality

### Responsive Design
- CSS Grid and Flexbox layout system
- Mobile-first responsive breakpoints
- Touch-friendly interface elements

### Color Science Implementation
The color generation uses HSL color space for predictable color relationships:
- Maintains hue consistency across theme variants
- Adjusts saturation and lightness for accessibility
- Ensures proper contrast ratios for text readability

## Common Development Tasks

### Modifying Color Algorithms
The color generation logic is in the `generatePalette()` method. Key considerations:
- HSL values are bounded to prevent invalid colors
- Light theme uses higher lightness values (90%+) for backgrounds
- Dark theme uses lower lightness values (15% and below) for backgrounds

### Adding New Color Stops
Gradient stops are defined in `getColorFromGradientPosition()`:
- Each stop has position (0-1) and RGB values
- Linear interpolation between adjacent stops
- Handles edge cases at gradient boundaries

### Extending Theme Support
To add new theme variants:
1. Extend the palette object in `generatePalette()`
2. Add corresponding DOM elements and IDs
3. Update the `updateThemes()` method to apply new colors

## Browser Compatibility
- Modern browsers supporting ES6 classes and arrow functions
- CSS Grid and Flexbox support required
- No polyfills or transpilation needed for target browsers
