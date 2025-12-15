# ccjsonvalidator

A robust JSON Validator written in Go.

This project is a solution to the ["Build Your Own JSON Parser"](https://codingchallenges.fyi/challenges/challenge-json-parser) coding challenge. It validates whether a given input is a valid JSON object according to standard syntax rules.

## 🚀 Features

-   **Syntax Validation**: Checks for correctly paired braces, brackets, and quotes.
-   **Type Support**: Validates standard JSON types (strings, numbers, booleans, null, arrays, and objects).
-   **Error Handling**: Returns appropriate exit codes (0 for valid, 1 for invalid) suitable for CI/CD pipelines or scripting.
-   **End-to-End Testing**: Includes a comprehensive suite of integration tests.

## 📋 Prerequisites

To build and run this project, you need:

-   [Go](https://go.dev/dl/) (version 1.18 or higher recommended)

## 🛠️ Installation

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/ahmedsameha1/ccjsonvalidator.git](https://github.com/ahmedsameha1/ccjsonvalidator.git)
    cd ccjsonvalidator
    ```

2.  **Download dependencies**
    ```bash
    go mod download
    ```

3.  **Build the project**
    ```bash
    go build -o ccjsonvalidator ./cmd/cli/ccjsonparser.go
    ```

## 💻 Usage

You can run the validator directly using the built binary or via `go run`. The tool accepts a file path as an argument.

### Using `go run`
```bash
go run cmd/cli/ccjsonparser.go path/to/file.json
```

### Using the binary
```bash
./ccjsonvalidator path/to/file.json
```
## Exit Codes

| Exit Code | Status | Description |
| :---: | :--- | :--- |
| **0** | `Valid` | The file contains valid JSON. |
| **1** | `Invalid` | The file contains invalid JSON or syntax errors. |


## 🧪 Testing

The project is structured with both unit tests and end-to-end integration tests.

### Run all tests
```bash
go test ./...
```

### Run end-to-end integration tests
```bash
go test ./endtoendtests
```

## 📂 Project Structure

```text
ccjsonvalidator/
├── cmd/               # Application entry point
├── internal/
│   └── app/           # Core validation logic and parser implementation
├── endtoendtests/     # Integration tests with sample JSON files
├── tests/             # JSON file for end-to-end tests
├── functions.go       # Helper utility functions
├── go.mod             # Go module definition
└── README.md          # Project documentation