# Filters
You can use filters to change the format of the text used to populate your template. Below is a list of all the options available:

## Text Manipulation

```text
{text | upper}       // Uppercase
{text | lower}       // Lowercase
{text | capfirst}    // Capitalize first letter
{text | initials}    // Get initials (e.g., "John Doe" → "J.D.")
```

## Date Formatting

```text
{date | convertDate: 'full'}  // Monday, January 01, 2023
{date | convertDate: 'short'} // 01/01/2023
{date | convertDateLocale: 'en-US':'full'} // Monday, January 1, 2023
```

## Date Range

```text
{date_start | fromTo: date_end:'en-US' | capfirst}
// Output varies automatically:
// - Same day → On 28/11/2022
// - Same month → From 28 to 30/11/2022
// - Same year → From 28/11 to 02/12/2022
// - Different years → From 28/11/2022 to 06/01/2023
```

## Grouping and Sorting

```text
{#findings | groupBy: 'severity'}
Severity: {key}
{#value}
  - {name}
{/value}
{/findings | groupBy: 'severity'}
```

```text
{#findings | sort: 'orderNumber'}
  {name}
{/findings | sort: 'orderNumber'}
```


## Linking (in development)

```text
{email | mailto}              // Create mailto link
{text | linkTo: 'https://example.com'} // Create hyperlink
```
