# Conversions
These special filters are used for converting HTML/Markdown fields to XML (the preferred docx format), so that they can be **rendered properly**.

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

?> We recomend using the markdown filter, since it can parse both Markdown and HTML at the same time.
