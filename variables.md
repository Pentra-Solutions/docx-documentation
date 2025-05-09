# Data Available via Tags

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
- `{pentest.client}` - Name of the client company
- `{pentest.type}` - Type of pentest, either Internal or External
- `{pentest.category}` - Pentest category, either Blackbox, Graybox or Whitebox
- `{pentest.scope}` - The full pentest scope

## Findings/Vulnerabilities Data

The `findings` array contains all vulnerabilities.
<br/>
**To edit these fields** directly, open a pentest and select the `Editor` tab from the sidebar. Alternatively, you can generate them with AI from the `Logger` tab.

- `{findings[i].name}` - Vulnerability name
- `{findings[i].tag}` - Tag (generated by Pentra)
- `{findings[i].description}` - Vuln description, editable as HTML text with images
- `{findings[i].severity}` - Custom severity text (or CVSS vector)
- `{findings[i].cvss}` - CVSS score object
- `{findings[i].poc}` - Proof of concept
- `{findings[i].countermeasures}` - Countermeasures/Remediation steps
- `{findings[i].references}` - References array

!> You do not actually have to write `findings[i]` before each tag, as it is done automatically. Check the [loops](loops) tab for more information.

## Custom Data

If the provided fields ar not enough, you can always add new fields from the Pentra web-app. New fields are specific for each template, and can be used in tags like this:

`{customFields.CustomFieldName}`
