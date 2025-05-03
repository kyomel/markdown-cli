# Markdown Preview Tool

A command-line tool written in Go that converts Markdown files to HTML and automatically previews them in your default web browser.

## Features

- Convert Markdown files to clean, sanitized HTML
- Automatic preview in your default web browser
- Cross-platform support (Linux, Windows, macOS)
- Safe HTML generation using bluemonday sanitizer
- Auto-preview mode with file watching capability
- Command-line flags for flexible usage

## Installation

```bash
# Clone the repository
git clone https://github.com/user/program.git

# Navigate to the project directory
cd program

# Build the binary
go build -o mdp
```

### Dependencies

The program uses the following external packages:

- `github.com/microcosm-cc/bluemonday` - For HTML sanitization
- `github.com/russross/blackfriday/v2` - For Markdown to HTML conversion

## Testing

To run the tests:

```bash
go test -v
```

## Usage

### Basic Usage

```bash
# Preview a markdown file
./mdp -file=your_markdown_file.md

# Preview without opening browser (just generate HTML)
./mdp -file=your_markdown_file.md -s
```

### Command-line Flags

- `-file`: Specify the input Markdown file (required)
- `-s`: Skip auto-preview in browser

### Auto-Preview Mode

The tool includes an auto-preview feature that watches for changes in your Markdown file and automatically updates the preview. To use this feature:

1. Make the auto-preview script executable:

   ```bash
   chmod +x autopreview.sh
   ```

2. Run the auto-preview script with your markdown file:
   ```bash
   ./autopreview.sh your_markdown_file.md
   ```

The script will check for changes every 5 seconds and update the preview automatically.

### How it Works

1. The program reads the input Markdown file
2. Converts the Markdown to HTML using blackfriday
3. Sanitizes the HTML output using bluemonday for security
4. Creates a temporary HTML file with proper HTML structure
5. Opens the generated HTML in your default web browser (unless -s flag is used)
6. Cleans up the temporary file after preview

The generated HTML includes proper DOCTYPE and HTML structure for optimal rendering.
