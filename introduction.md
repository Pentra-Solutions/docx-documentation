# Introduction

?> **Overview** This guide explains how to create Word document templates that work with our app. The app lets you to create professional reports by defining templates with placeholders that will be filled with your data.

## Template Basics

Templates are Microsoft Word documents (.docx) with special tags that get replaced with dynamic content. The template engine uses [docxtemplater](https://docxtemplater.com/) to process these tags and generate the final document.

## Common Issues and Solutions

### Missing Data

If a tag doesn't show up in the output document, the data field is likely missing or undefined.

### HTML Formatting Issues

Make sure the HTML is properly formed and use the `convertHTML` filter.

?> **Need Help?** For additional assistance with template creation, refer to: [Docxtemplater Documentation](https://docxtemplater.com/docs/).
