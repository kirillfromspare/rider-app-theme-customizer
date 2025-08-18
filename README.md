# Theme Customizer

A web-based tool for customizing app themes with real-time color palette generation.

## Features

- **Interactive Color Picker**: Rainbow gradient slider for precise color selection
- **Real-time Theme Generation**: Automatically generates light and dark theme palettes
- **Reset Functionality**: Quick return to default color (#0362FF)
- **Responsive Design**: Works on desktop and mobile devices

## Usage

1. Drag the white handle along the color gradient to select your primary color
2. Watch as both light and dark theme palettes update in real-time
3. Click "Reset to Default" to return to the original blue color
4. Use "Save Changes" to export your theme (feature can be extended)

## Live Demo

Visit the live demo: [https://kirillfromspare.github.io/rider-app-theme-customizer](https://kirillfromspare.github.io/rider-app-theme-customizer)

## Color Palette Generation

The tool generates 6 semantic colors for each theme:

### Light Theme
- **AccentPrimary**: Your selected color
- **AccentLowContrast**: Lighter variation for subtle accents
- **BackgroundPrimary**: Very light background
- **BackgroundSecondary**: Even lighter secondary background
- **ContentPrimary**: High contrast text color
- **ContentSecondary**: Medium contrast secondary text

### Dark Theme
- **AccentPrimary**: Brighter version of your selected color
- **AccentLowContrast**: Darker variation for subtle accents
- **BackgroundPrimary**: Very dark background
- **BackgroundSecondary**: Slightly lighter secondary background
- **ContentPrimary**: High contrast light text
- **ContentSecondary**: Medium contrast secondary text

## Technical Details

- Pure HTML, CSS, and JavaScript (no dependencies)
- HSL color space manipulation for consistent color relationships
- Responsive design with CSS Grid and Flexbox
- Smooth animations and interactions

## License

MIT License - feel free to use and modify for your projects.
