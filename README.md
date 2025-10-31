# 🎨 Advanced Sass Demo

> A comprehensive demonstration of modern Sass features using the 7-1 architecture pattern

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://jack-pettersson.github.io/Sass-Demo/)
[![Sass](https://img.shields.io/badge/Sass-1.80-CC6699?logo=sass)](https://sass-lang.com/)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

## 📺 Demo

**View the live demo here:** [https://jack-pettersson.github.io/Sass-Demo/](https://jack-pettersson.github.io/Sass-Demo/)

This project demonstrates advanced Sass (SCSS) features and best practices for building scalable, maintainable stylesheets.

## ✨ Features Showcased

### **Architecture & Organization**
- ✅ **7-1 Architecture Pattern** - Industry-standard folder structure
- ✅ **Modern Module System** - Using `@use` and `@forward` (not `@import`)
- ✅ **Component-Based Design** - Reusable, modular components

### **Sass Features**
- ✅ **Variables & Maps** - Color palettes, spacing scales, breakpoints
- ✅ **Custom Functions** - `px-to-rem()`, `get-color()`, `spacing()`, etc.
- ✅ **Powerful Mixins** - Flexbox helpers, button variants, responsive breakpoints
- ✅ **Placeholder Selectors** - `@extend` for DRY code without bloat
- ✅ **Control Directives** - `@each`, `@if`, `@for` for dynamic generation
- ✅ **Built-in Modules** - `sass:math`, `sass:color`, `sass:map`
- ✅ **Modern Syntax** - Using `color.adjust()` instead of deprecated `darken()`/`lighten()`
- ✅ **Nesting** - Organized, readable styles with proper nesting
- ✅ **Partials** - Modular file organization with `_` prefix

### **UI Components**
- 🔘 **Buttons** - Multiple variants, sizes, and states
- 🃏 **Cards** - Flexible card layouts with various styles
- 📝 **Forms** - Styled inputs with validation states
- 🎨 **Alerts** - Info, success, warning, and error styles
- 🏷️ **Badges** - Inline labels and tags
- ⏳ **Loading Spinners** - Animated loading indicators

### **Advanced Features**
- 🌓 **Dark Mode Support** - Theme toggle with localStorage
- 📱 **Responsive Design** - Mobile-first with breakpoint mixins
- ♿ **Accessibility** - Focus states, ARIA labels, semantic HTML
- 🎭 **Animations** - Smooth transitions and keyframe animations
- 🛠️ **Utility Classes** - Spacing, flexbox, and layout helpers

## 📁 Project Structure

```
Sass-Demo/
│
├── src/
│   ├── abstracts/          # Variables, functions, mixins, placeholders
│   │   ├── _variables.scss # Color maps, spacing, breakpoints
│   │   ├── _functions.scss # Custom Sass functions
│   │   ├── _mixins.scss    # Reusable style patterns
│   │   └── _placeholders.scss # @extend selectors
│   │
│   ├── base/               # Foundation styles
│   │   ├── _reset.scss     # CSS reset/normalize
│   │   └── _typography.scss # Typography styles
│   │
│   ├── components/         # Reusable UI components
│   │   ├── _buttons.scss   # Button styles
│   │   ├── _cards.scss     # Card components
│   │   └── _forms.scss     # Form elements
│   │
│   ├── layout/             # Layout components
│   │   ├── _header.scss    # Header styles
│   │   ├── _navigation.scss # Navigation menu
│   │   └── _container.scss # Container & utilities
│   │
│   ├── styles.scss         # Main file that imports all partials
│   └── styles.css          # Compiled CSS output
│
├── index.html              # Demo page with all components
├── package.json            # NPM scripts and dependencies
├── .gitignore             # Git ignore rules
└── README.md              # This file
```

## 🚀 Getting Started

### Prerequisites

- **Node.js** (v14 or higher) - [Download](https://nodejs.org/)
- **npm** or **yarn** - Comes with Node.js

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Jack-Pettersson/Sass-Demo.git
   cd Sass-Demo
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Compile Sass**
   ```bash
   npm run sass
   ```

4. **Open in browser**
   ```bash
   # Simply open index.html in your browser
   # Or use a local server like Live Server (VS Code extension)
   ```

## 📜 NPM Scripts

```bash
# Compile Sass once
npm run sass

# Watch for changes and auto-compile
npm run sass:watch
npm start                    # Alias for sass:watch

# Development mode with source maps
npm run dev

# Build for production (compressed, no source maps)
npm run build
```

## 💡 Usage Examples

### Using Variables and Functions
```scss
@use 'abstracts/variables' as *;
@use 'abstracts/functions' as *;

.my-element {
  color: $primary-color;           // Using variables
  padding: spacing(lg);            // Using functions
  font-size: font-size(xl);
  margin: rem(24px);               // Convert px to rem
}
```

### Using Mixins
```scss
@use 'abstracts/mixins' as *;

.my-button {
  @include button-variant($primary-color);
  
  @include respond-to(md) {
    width: 100%;
  }
}

.centered-content {
  @include flex-center;
}
```

### Using Placeholder Selectors
```scss
@use 'abstracts/placeholders' as *;

.my-image {
  @extend %img-responsive;
}

.hidden-text {
  @extend %sr-only;
}
```

### Iterating with @each
```scss
$colors: (
  primary: #3498db,
  secondary: #2ecc71,
  accent: #e74c3c
);

@each $name, $color in $colors {
  .btn-#{$name} {
    background: $color;
  }
}
```

## 🎓 Learning Resources

This demo showcases concepts from:

- [Sass Official Documentation](https://sass-lang.com/documentation)
- [7-1 Architecture Pattern](https://sass-guidelin.es/#architecture)
- [Modern Module System (@use)](https://sass-lang.com/documentation/at-rules/use)
- [Sass Guidelines](https://sass-guidelin.es/)

## 🐛 Troubleshooting

### Sass Not Compiling?
```bash
# Make sure Sass is installed
npm install

# Check Sass version
npx sass --version

# Try compiling manually
npx sass src/styles.scss src/styles.css
```

### Styles Not Updating?
```bash
# Use watch mode for auto-compilation
npm run sass:watch

# Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)
```

### Import Errors?
- Ensure you're using `@use` instead of `@import`
- Check file paths are relative to the importing file
- Verify partial files start with `_` underscore

### Module Not Found?
```bash
# Reinstall dependencies
rm -rf node_modules package-lock.json
npm install
```

## 🎯 Key Takeaways

1. **7-1 Pattern** - Organized, scalable architecture
2. **Variables in Maps** - Better organization than individual variables
3. **Mixins for Patterns** - Reusable styles with parameters
4. **Functions for Logic** - Calculations and utilities
5. **@use over @import** - Modern, namespace-aware modules
6. **Component Thinking** - Build reusable UI pieces
7. **Mobile-First** - Start small, scale up with breakpoints
8. **Accessibility** - Focus states and semantic HTML

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/Jack-Pettersson/Sass-Demo/issues).

## 👤 Author

**Jack Pettersson**
- GitHub: [@Jack-Pettersson](https://github.com/Jack-Pettersson)

---

**Happy Styling with Sass! 🎨**
