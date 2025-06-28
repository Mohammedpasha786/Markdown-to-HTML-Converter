# Markdown-to-HTML-Converter


A simple, efficient command-line tool that converts Markdown files to clean, well-formatted HTML with built-in CSS styling.

## Features

- **Complete Markdown Support**: Headers, emphasis (bold/italic), lists, links, code blocks, blockquotes, and horizontal rules
- **Clean HTML Output**: Generates semantic HTML with professional CSS styling
- **Command-line Interface**: Easy to use with flexible options
- **Cross-platform**: Works on Windows, macOS, and Linux
- **No Dependencies**: Pure Python implementation - no external libraries required
- **Error Handling**: Comprehensive error checking and user-friendly messages

## Installation

### Prerequisites
- Python 3.6 or higher

### Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/md2html-converter.git
   cd md2html-converter
   ```

2. Make the script executable (Unix/macOS):
   ```bash
   chmod +x md2html.py
   ```

## Usage

### Basic Usage
```bash
python md2html.py input.md
```
This converts `input.md` to `input.html` in the same directory.

### Specify Output File
```bash
python md2html.py input.md -o output.html
```

### Set Custom Title
```bash
python md2html.py input.md --title "My Document"
```

### Command-line Options
- `input`: Input Markdown file path (required)
- `-o, --output`: Output HTML file path (optional, defaults to input filename with .html extension)
- `-t, --title`: HTML document title (optional, defaults to filename without extension)
- `--version`: Show version information
- `-h, --help`: Show help message

### Examples

```bash
# Convert README.md to README.html
python md2html.py README.md

# Convert with custom output file and title
python md2html.py docs/guide.md -o website/guide.html --title "User Guide"

# Convert multiple files using shell commands
for file in *.md; do python md2html.py "$file"; done
```

## Supported Markdown Syntax

### Headers
```markdown
# H1 Header
## H2 Header
### H3 Header
#### H4 Header
##### H5 Header
###### H6 Header
```

### Text Formatting
```markdown
**Bold text** or __Bold text__
*Italic text* or _Italic text_
***Bold and italic***
```

### Lists
```markdown
# Unordered lists
- Item 1
- Item 2
- Item 3

# Ordered lists
1. First item
2. Second item
3. Third item
```

### Links
```markdown
[Link text](https://example.com)
https://example.com (auto-linked)
```

### Code
```markdown
Inline `code` with backticks

```
Code block with triple backticks
```

```python
# Code block with language specification
def hello():
    print("Hello, World!")
```
```

### Blockquotes
```markdown
> This is a blockquote
> It can span multiple lines
```

### Horizontal Rules
```markdown
---
***
```

## Output Features

The generated HTML includes:

- **Responsive Design**: Mobile-friendly viewport and layout
- **Professional Styling**: Clean, GitHub-inspired CSS
- **Semantic HTML**: Proper HTML5 structure
- **Syntax Highlighting Ready**: Code blocks are properly formatted
- **Print Friendly**: Optimized for both screen and print
- **Accessibility**: Proper heading hierarchy and semantic markup

## File Structure

```
md2html-converter/
├── md2html.py          # Main converter script
├── sample.md           # Example Markdown file
├── sample.html         # Example HTML output
├── README.md           # This file
└── requirements.txt    # Python dependencies (empty - no external deps)
```

## Testing

Test the converter with the included sample file:

```bash
python md2html.py sample.md
```

This will generate `sample.html` which you can open in any web browser to see the converted output.

## Error Handling

The tool handles common errors gracefully:

- **File not found**: Clear error message if input file doesn't exist
- **Permission errors**: Informative message if files can't be read/written
- **Invalid input**: Helpful error messages for incorrect usage
- **Encoding issues**: UTF-8 encoding support for international characters

## Customization

### Modifying CSS Styles

The CSS styles are embedded in the `html_template` within the `MarkdownToHtmlConverter` class. To customize the appearance:

1. Edit the CSS in the `html_template` string
2. Modify colors, fonts, spacing, or layout as needed
3. The styling follows a GitHub-inspired design that's easily customizable

### Adding New Markdown Features

To add support for additional Markdown syntax:

1. Create a new conversion method in the `MarkdownToHtmlConverter` class
2. Add the method call to the conversion pipeline in `convert_markdown_to_html()`
3. Test with sample input to ensure proper formatting

## Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and test thoroughly
4. Commit your changes: `git commit -am 'Add feature'`
5. Push to the branch: `git push origin feature-name`
6. Submit a pull request
## Changelog

### Version 1.0.0
- Initial release
- Support for all standard Markdown syntax
- Clean HTML output with embedded CSS
- Command-line interface with flexible options
- Comprehensive error handling
- Cross-platform compatibility

## Known Issues

- Nested lists require manual indentation in the output
- Tables are not yet supported (planned for future release)
- Line breaks within paragraphs need double spaces (standard Markdown behavior)

## Future Enhancements

- [ ] Table support
- [ ] Custom CSS file option
- [ ] Batch processing mode
- [ ] Configuration file support
- [ ] Plugin system for extensions
- [ ] Live preview mode
- [ ] Markdown extensions (footnotes, task lists, etc.)
