# Quick-start

## Tags

### Tag Syntax

Tags are enclosed in curly braces: `{` and `}`. For example: `{name}`, `{findings}`, etc.

### Types of Tags

- **Simple tags**: `{tag}` - Insert text
- **Loop tags**: `{#array}...{/array}` - Repeat content for each item in an array
- **Conditional tags**: `{#condition}...{/condition}` - Show content only if condition is true
- **HTML content**: `{@htmlField | convertHTML}` - Convert HTML to Word format
- **Images**: `{%imageField}` - Insert images
- **Filters**: `{input | filter}` - Transform data (e.g., `{date | convertDate: 'full'}`)

## Available Data in Templates

Your template can access the following data structure:

### Template Data

- `{template.templateName}` - Name of the template
- `{template.executiveSummary}` - HTML content with images
- `{template.confidentiality}` - Confidentiality text
- `{template.methodology}` - Methodology text
- `{template.recommendations}` - Recommendations text
- `{template.motto}` - Motto text
- `{template.logo}` - Logo image
- `{template.footerText}` - Footer text
- `{template.date}` - Report date
- `{template.date_start}` - Start date
- `{template.date_end}` - End date

### Pentest Data

- `{pentest.title}` - Pentest title
- `{pentest.startDate}` - Start date
- `{pentest.endDate}` - End date
- `{pentest.client}` - Client name
- `{pentest.type}` - Type of pentest
- `{pentest.category}` - Category
- `{pentest.scope}` - Scope text

### Findings/Vulnerabilities

The `findings` array contains all vulnerabilities:

- `{findings[i].name}` - Finding name
- `{findings[i].tag}` - Tag
- `{findings[i].description}` - HTML with images
- `{findings[i].severity}` - Severity rating
- `{findings[i].cvss}` - CVSS score object
- `{findings[i].poc}` - Proof of concept
- `{findings[i].countermeasures}` - Countermeasures/remediation
- `{findings[i].references}` - References array
- `{findings[i].orderNumber}` - Order number

## Basic Template Example

```text
Company: {template.contactInformation.company}
Report Date: {template.date | convertDate: 'full'}
Client: {pentest.client}
Scope: {pentest.scope}

# Executive Summary
{@template.executiveSummary | convertHTML}

# Findings
{#findings}
## {orderNumber}. {name} ({severity})
CVSS Score: {cvss.baseMetricScore} ({cvss.baseSeverity})

### Description
{@description | convertHTML}

### Proof of Concept
{-w:p poc}{@text | convertHTML}
{-w:p images}{%image}
Image {index}{caption | captionCheck}{/images}{/poc}

### Countermeasures
{@countermeasures | convertHTML}

{/findings}
```

## Using Loops

To iterate over arrays like `findings`, use loop tags:

```text
{#findings}
  Finding: {name}
{/findings}
```

For nested loops:

```text
{#findings}
  {#references}
    Reference: {url}
  {/references}
{/findings}
```

## Handling HTML Content

HTML content (like descriptions and proofs of concept) must be converted using the `convertHTML` filter:

```text
{@description | convertHTML}
```

For HTML content with images:

```text
{description}
  {@text | convertHTML}
  {images}
    {%image}
    Image {index} - {caption}
  {/images}
{/description}
```

## Conditional Content

Use conditional tags to show content only in certain cases:

```text
{#severity == 'Critical'}
  This is a critical finding!
{/severity == 'Critical'}
```

## Advanced Filters

The microservice provides several useful filters:

### Date Formatting

```text
{date | convertDate: 'full'}  // Monday, January 01, 2023
{date | convertDate: 'short'} // 01/01/2023
{date | convertDateLocale: 'en-US':'full'} // Monday, January 1, 2023
```

### Date Range

```text
{date_start | fromTo: date_end:'en-US' | capfirst}
// Output varies automatically:
// - Same day → On 28/11/2022
// - Same month → From 28 to 30/11/2022
// - Same year → From 28/11 to 02/12/2022
// - Different years → From 28/11/2022 to 06/01/2023
```

### Grouping and Sorting

```text
{#findings | groupBy: 'severity'}
Severity: {key}
{#value}
  - {name}
{/value}
{/findings | groupBy: 'severity'}
```

```text
{#findings | sort: 'orderNumber'}
  {name}
{/findings | sort: 'orderNumber'}
```

### Text Manipulation

```text
{text | upper}       // Uppercase
{text | lower}       // Lowercase
{text | capfirst}    // Capitalize first letter
{text | initials}    // Get initials (e.g., "John Doe" → "J.D.")
```

### Linking (not working yet)

```text
{email | mailto}              // Create mailto link
{text | linkTo: 'https://example.com'} // Create hyperlink
```

## Best Practices for Templates

1. **Use proper Word styles**: Define styles in your Word template for consistent formatting.
2. **Test with sample data**: Create a test document with realistic data before finalizing.
3. **Handle empty arrays**: Use conditional tags to handle cases where arrays might be empty.
4. **Check image sizing**: Large images are automatically resized but you may want to control the size.
5. **Organize sections**: Use Word's section breaks and headers/footers for better organization.

## Special Word Template Requirements

For bullet and numbered lists to work correctly, make sure your template defines the following styles:

- **HTMLTextStyle**: For regular paragraphs
- **Heading1-6**: For headings
- **CodeChar**: For inline code
- **Code**: For code blocks

For bullet and numbered lists, you'll need to ensure the numbering.xml file in your .docx template has the correct definitions.
