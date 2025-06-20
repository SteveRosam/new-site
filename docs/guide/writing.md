# Writing Documentation

Learn how to write clear, consistent, and effective documentation for your project.

## Basic Syntax

Our documentation uses Markdown with some extensions. Here are the basics:

### Headers

```markdown
# H1
## H2
### H3
```

### Text Formatting

```markdown
*italic* or _italic_
**bold** or __bold__
`inline code`
~~strikethrough~~
```

### Lists

```markdown
- Item 1
- Item 2
  - Nested item
  - Another nested item

1. First item
2. Second item
3. Third item
```

### Links and Images

```markdown
[Link text](https://example.com)
![Alt text](/path/to/image.jpg)
```

## Code Blocks

Use fenced code blocks with syntax highlighting:

````markdown
```python
def hello_world():
    print("Hello, World!")
```
````

## Admonitions

!!! note
    This is a note.

!!! warning "Important"
    This is a warning with a custom title.

## Tabs

=== "Python"
    ```python
    print("Hello from Python!")
    ```

=== "JavaScript"
    ```javascript
    console.log("Hello from JavaScript!");
    ```

## Best Practices

1. **Be concise** - Get to the point quickly
2. **Use active voice** - "Click the button" not "The button should be clicked"
3. **Be consistent** - Use the same terminology throughout
4. **Use examples** - Show, don't just tell
5. **Include context** - Explain why, not just how

## Next Steps

- [Learn about styling your documentation](styling.md)
- [Review the API reference](../reference/commands.md)
- [Customize your site's configuration](../getting-started/configuration.md)
