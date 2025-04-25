# Quick-start Guide

?> Welcome to the documentation for the DOCX templating system. This guide will help you understand how to create and use templates for generating Word documents.

To get started, download our [example document](examples), or edit an existing document.

## Overview
A template is supposed to be **pentest-agnostic**, meaning that regardless of the actual vulnerability content or the client of the pentest, the overall structure of the document remains unchanged. 

This is why our templates keep everything from fonts, to element layout the same, while populating specific sections of the document with pentest data. This is done by using **tags**. 

Using tags, the user can also specify **loops** and **conditions** to dynamically update the document regardless of how many findings the pentest has. Examples for each of these can be found in their specific sections.

## Using a template
To populate a template, choose the pentest and then select **Template** from the sidebar. Then, click **Select Template > Upload Template** at the top of the screen. 

Choose a DOCX template that has been edited beforehand and open it in the interface. The page will automatically source it to generate the report.

Finally, you can change how your template is populated from the options on the right. For example, you can upload a custom logo.

?> Sometimes a refresh is required in order to display the correct options for the uploaded template

## Contents

- [Tags](tags) - Understanding tag syntax and types
- [Available Variables](variables) - Data that can be accesed inside a template
- [Loops](loops) - Working with arrays and iterating over data
- [Conditional Content](conditional-content) - Showing content based on conditions
- [HTML Content](html-content) - Converting HTML to Word format
- [Filters](filters) - Transforming data with various filters
- [Best Practices](best-practices) - Tips and requirements for templates

!> **Getting Help** If you have any questions or run into issues, please contact the development team.
