# Basic Template Example

```text
Company: {template.contactInformation.company}
Report Date: {template.date | convertDate: 'full'}
Client: {pentest.client}
Scope: {pentest.scope}

# Executive Summary
{@template.executiveSummary | convertMarkdown}

# Findings
{#findings}
## {orderNumber}. {name} ({severity})
CVSS Score: {cvss.baseMetricScore} ({cvss.baseSeverity})

### Description
{@description | convertMarkdown}

### Proof of Concept
{#poc}{@text | convertMarkdown}{/poc}
{#images}{%image}{images}
Image {index}{caption | captionCheck}{/images}{/poc}

### Countermeasures
{@countermeasures | convertHTML}

{/findings}
```
