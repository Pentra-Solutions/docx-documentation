# Available Data in Templates

## Template-Specific Data

This is data specific to your chosen template, regardless of the pentest used to populate it.
<br/>
**To edit these fields**, open any pentest and select the `Template` tab from the sidebar.

- `{template.templateName}` - Name of the template
- `{template.executiveSummary}` - HTML content with images
- `{template.confidentiality}` - Confidentiality text
- `{template.methodology}` - Methodology text
- `{template.recommendations}` - Recommendations text
- `{template.motto}` - Your company Motto (text)
- `{template.logo}` - Your company Logo (image)
- `{template.footerText}` - Footer text
- `{template.date}` - Report date
- `{template.date_start}` - Start date
- `{template.date_end}` - End date

## Pentest-Specific Data

This is metadata about the current pentest, sourced from the pentest creation form.
<br/>
**To edit these fields**, open the pentest and select `Metadata` (the settings Icon) from the sidebar.

- `{pentest.title}` - Pentest title
- `{pentest.startDate}` - Start date
- `{pentest.endDate}` - End date
- `{pentest.client}` - Client name
- `{pentest.type}` - Type of pentest
- `{pentest.category}` - Category
- `{pentest.scope}` - Scope text

## Findings/Vulnerabilities Data

The `findings` array contains all vulnerabilities.
<br/>
**To edit these fields** directly, open a pentest and select the `Editor` tab from the sidebar. Alternatively, you can generate them with AI from the `Logger` tab.

- `{findings[i].name}` - Finding name
- `{findings[i].tag}` - Tag
- `{findings[i].description}` - HTML with images
- `{findings[i].severity}` - Severity rating
- `{findings[i].cvss}` - CVSS score object
- `{findings[i].poc}` - Proof of concept
- `{findings[i].countermeasures}` - Countermeasures/remediation
- `{findings[i].references}` - References array
- `{findings[i].orderNumber}` - Order number 
