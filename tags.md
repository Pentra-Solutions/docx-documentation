# Tags

?> **Tags** are enclosed in curly braces: `{` and `}`. For example: `{name}`, `{findings}`, etc..

## Types of Tags

- **Simple tags**: `{tag}` - Insert text
- **Loop tags**: `{#array}...{/array}` - Repeat content for each item in an array
- **Conditional tags**: `{#condition}...{/condition}` - Show content only if condition is true
- **HTML content**: `{@htmlField | convertHTML}` - Convert HTML to Word format
- **Images**: `{%imageField}` - Insert images
- **Filters**: `{input | filter}` - Transform data (e.g., `{date | convertDate: 'full'}`) 