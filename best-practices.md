# Best Practices for Templates

1. **Use proper Word styles**: Define styles in your Word template for consistent formatting.
2. **Test with sample data**: Create a test document with realistic data before finalizing.
3. **Handle empty arrays**: Use conditional tags to handle cases where arrays might be empty.
4. **Check image sizing**: Large images are automatically resized but you may want to control the size.
5. **Organize sections**: Use Word's section breaks and headers/footers for better organization.

## Special Word Template Requirements

For bullet and numbered lists to work correctly, make sure your template defines the following styles:

- **HTMLTextStyle**: For regular paragraphs
- **Heading1-6**: For headings
- **CodeChar**: For inline code
- **Code**: For code blocks

For bullet and numbered lists, you'll need to ensure the numbering.xml file in your .docx template has the correct definitions. 