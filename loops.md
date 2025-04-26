# Using Loops

To iterate over arrays like `findings`, use loop tags:

```text
{#findings}
  Finding: {name}
{/findings}
```

Inside the loop, fields should not be prefixed by anything, since they will automatically use the information from each element individually. For example, you would write `{name}`, NOT `{findings[i].name`.

### Nested Loops
Loops can also be nested:

```text
{#findings}
  {#references}
    Reference: {url}
  {/references}
{/findings}
```

Check the [example document](example) to see these in action.
