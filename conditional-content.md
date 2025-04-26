# Conditional Content

Use conditional tags to show content only in certain cases:

```text
{#severity == 'Critical'}
  This is a critical finding!
{/severity == 'Critical'}
```

This is very usefull, for example, when certain texts or colors in the document depend on the severity of the finding:

```
{#findings}
    {#cvss.baseSeverity == 'Critical'}
        Vulnerability {name} should be adressed immediately!
    {cvss.baseSeverity}
{/findings}
```

Check the [example document](example) to see these in action.
