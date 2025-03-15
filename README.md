# HTML Div Analyzer

A Python tool for analyzing and detecting potential issues in HTML `<div>` elements on websites.

## Overview

HTML Div Analyzer is a utility that scans web pages and identifies common issues with `<div>` elements such as empty tags, accessibility problems, inline styling, and excessive nesting. The tool generates an interactive HTML report that color-codes issues by severity and provides recommendations for improvement.

## Features

- Scrapes and analyzes websites for problematic `<div>` elements
- Detects 5 common types of issues:
  - Empty `<div>` tags
  - Accessibility issues (missing role/aria attributes)
  - Inline styles
  - Missing class/id attributes
  - Excessive nesting
- Color-coded severity indicators
- Generates an interactive HTML report
- Automatically opens reports in your default browser

## Requirements

- Python 3.8+
- BeautifulSoup4
- Requests

## Installation

1. Clone the repository
   ```
   git clone https://github.com/yourusername/html-div-analyzer.git
   cd html-div-analyzer
   ```

2. Create a virtual environment (optional but recommended)
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required packages
   ```
   pip install -r requirements.txt
   ```

## Usage

### Basic Usage

```python
from div_analyzer import analyze_website

# Analyze a website
analyze_website("https://example.com")
```

The tool will:
1. Fetch the webpage content
2. Analyze all `<div>` elements for issues
3. Generate an HTML report named after the website's domain
4. Automatically open the report in your default web browser

### As a Command Line Tool

You can also use the tool from the command line:

```
python div_analyzer.py https://example.com
```

## Issue Types and Severity

The analyzer detects the following issues, each with its own severity color:

| Issue | Severity | Description |
|-------|----------|-------------|
| Empty `<div>` tags | Red | `<div>` elements without any content |
| Accessibility issues | Orange | Elements that may need role/aria attributes |
| Inline styles | Blue | `<div>` elements with style attributes |
| Missing class/id | Green | Elements without class or id attributes |
| Excessive nesting | Purple | Deeply nested `<div>` elements (depth > 3) |

## Sample Report

The generated HTML report includes:
- The analyzed website URL
- List of problematic `<div>` elements
- Issues detected for each element
- Severity of each issue
- Suggestions for improvement

## Functions

### `fetch_page(url)`
Retrieves the HTML content of the specified URL.

### `classify_div_issues(div)`
Analyzes a `<div>` element and identifies potential issues.

### `validate_html_divs(html_content)`
Processes all `<div>` elements in the HTML content and collects issues.

### `save_report_as_html(report, url)`
Generates an HTML report and saves it to a file named after the website's domain.

### `analyze_website(url)`
Main function that performs the complete analysis workflow.

## Extending the Tool

You can extend the analyzer by:
1. Adding new issue detection rules in the `classify_div_issues` function
2. Modifying the HTML report template in `save_report_as_html`
3. Creating custom severity levels

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Future Improvements

- Add support for analyzing other HTML elements (`<span>`, `<section>`, etc.)
- Implement more accessibility checks
- Add options for custom rulesets
- Create a web interface for the tool
- Generate downloadable PDF reports
- Add batch processing for multiple URLs
