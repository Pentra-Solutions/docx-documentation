# Basic Template Example

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
