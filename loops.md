# Using Loops

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
