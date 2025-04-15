# Available Data in Templates

## Template Data

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

## Pentest Data

- `{pentest.title}` - Pentest title
- `{pentest.startDate}` - Start date
- `{pentest.endDate}` - End date
- `{pentest.client}` - Client name
- `{pentest.type}` - Type of pentest
- `{pentest.category}` - Category
- `{pentest.scope}` - Scope text

## Findings/Vulnerabilities

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