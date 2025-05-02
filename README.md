# Example Markdown File

This is an example Markdown file to test the preview tool

## Features:

- Support for links [Educative](https://www.educative.io/)
- Support for other features
- Direct README.md processing with `-readme` flag

## How to install:

```bash
go get github.com/user/program

# Build the binary
go build -o mdp
```

## Testing

To run the tests:

```bash
go test -v
```

## How to run:

1. Make sure you have Go installed on your system.
2. Clone the repository:
   ```
   git clone https://github.com/user/program.git
   ```
3. Navigate to the project directory:
   ```
   cd program
   ```
4. Run the program using one of these methods:

   ```bash
   # Using go run
   go run main.go -file=your_markdown_file.md

   # Using the built binary
   ./mdp -file README.md

   # Process README.md in current directory
   go run main.go -readme
   # or
   ./mdp -readme

   # Process README.md without preview
   go run main.go -readme -s
   # or
   ./mdp -readme -s
   ```

5. The HTML output will be generated in a temporary directory and opened in your default browser (unless -s flag is used).
