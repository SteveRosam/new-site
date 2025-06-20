# Styling Guide

Customize the look and feel of your documentation site with these styling options.

## Color Scheme

Our documentation uses a carefully selected color palette:

### Primary Colors

- Primary: `#3f51b5` (Indigo)
- Accent: `#448aff` (Blue)
- Background: `#ffffff` (White)
- Surface: `#f5f5f5` (Light Gray)
- Text: `#212121` (Dark Gray)

### Semantic Colors

- Success: `#4caf50` (Green)
- Warning: `#ff9800` (Amber)
- Error: `#f44336` (Red)
- Info: `#2196f3` (Blue)

## Typography

### Font Family

- **Primary Font**: Roboto
- **Code Font**: Roboto Mono

### Text Styles

```css
/* Headings */
h1 { font-size: 2.5rem; font-weight: 300; }
h2 { font-size: 2rem; font-weight: 400; }
h3 { font-size: 1.5rem; font-weight: 500; }

/* Body Text */
body {
  font-size: 1rem;
  line-height: 1.6;
  color: #212121;
}

/* Code Blocks */
code {
  font-family: 'Roboto Mono', monospace;
  font-size: 0.9em;
}
```

## Layout

### Grid System

```html
<div class="grid" markdown>

<!-- Content goes here -->

</div>
```

### Cards

```html
<div class="grid cards" markdown>

- :material-check: **Feature 1**

    ---
    Description of feature 1

- :material-star: **Feature 2**
    ---
    Description of feature 2

</div>
```

## Custom CSS

To add custom styles, create a `styles/extra.css` file in your `docs` directory:

```css
/* Custom styles */
:root > * {
  --md-primary-fg-color: #3f51b5;
  --md-accent-fg-color: #448aff;
}

/* Custom button style */
.md-typeset .md-button {
  border-radius: 4px;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* Custom code block style */
.highlight {
  border-radius: 4px;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}
```

## Dark Mode

Our documentation automatically supports dark mode. To customize dark mode styles:

```css
[data-md-color-scheme="slate"] {
  --md-default-bg-color: #1e1e1e;
  --md-default-fg-color--light: #e0e0e0;
  --md-code-bg-color: #2d2d2d;
}
```

## Best Practices

1. **Consistency**: Maintain consistent spacing and styling throughout
2. **Accessibility**: Ensure sufficient color contrast (minimum 4.5:1)
3. **Responsiveness**: Test on different screen sizes
4. **Performance**: Keep custom CSS minimal and optimized

## Next Steps

- [Learn about writing documentation](writing.md)
- [Review the API reference](../reference/commands.md)
- [Customize your site's configuration](../getting-started/configuration.md)
