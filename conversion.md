# Converting HTML/Markwon to XML (docx format)

## Converting HTML to XML

HTML content (like proofs of concept) can be converted using the `convertHTML` filter:

```text
{@poc | convertHTML}
```

For HTML content with images:

```text
{poc}
  {@text | convertHTML}
  {images}
    {%image}
    Image {index} - {caption}
  {/images}
{/poc}
```

## Converting Markdown to XML

Markdown content can be converted using the `convertMarkdown` filter:

```text
{@description | convertMarkdown}
```

For Markdown content with images:

```text
{description}
  {@text | convertMarkdown}
  {images}
    {%image}
    Image {index} - {caption}
  {/images}
{/description}
```

?> We recomend using the makdown filter because it includes the html one too so it converts both markdown and HTML.
