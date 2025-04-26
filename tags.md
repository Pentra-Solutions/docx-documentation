# Tags

?> **Tags** are enclosed in curly braces: `{` and `}`. For example: `{name}`, `{findings}`, etc..

## Types of Tags

1. **Simple tags**: `{tag}` - Insert text<br/>Check the [Available Variables](variables) for data that can be accessed via simple tags.

2. **Loop tags**: `{#array}...{/array}` - Repeat content for each item in an array<br/>Most commonly used for listing the findings in the template:
```
{#findings}
  Finding: {name}
{/findings}
```
Check the [loops](loops) page for more information.

3. **Conditional tags**: `{#condition}...{/condition}` - Show content only if condition is true<br/>
For example, you could show a different message for each vulnerability severity.
```
{#severity == 'Critical'}
  This is a critical finding!
{/severity == 'Critical'}
```
Check the [conditional content](conditional-content) page for more information.

4. **Filters**: `{input | filter}` - Change data format<br/>
For example, you can change text to uppercase:
```
{text | upper}       // Uppercase
```
For a list of all available filters, check the [filters](filters) page.

5. **HTML content**: `{@htmlField | convertHTML}` - Convert HTML to Word format<br/>
Docx cannot properly display Markdown or HTML text, so special filters are used to first convert this data into XML. 
Check the [conversions](conversions) page for more information.


6. **Images**: `{%imageField}` - Insert images<br/>
For example, you could insert your logo like this:
```
{%template.logo}
```
