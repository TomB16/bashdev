# bashdev

`bashdev` is a set of BASH libraries designed to support robust and maintainable shell scripting. It provides structured argument parsing, helper functions, and debugging features commonly needed in modular BASH projects.

This library was created to power other work, such as videokit-kde and audiokit-kde, and is intended to be reusable across similar projects.

If you wish to use this library, look at the bashdev-*-test files for usage examples.


## Features

- 🔧 **CLI Argument Parsing** via `bashdev-param`
- 🧩 **Modular Function Sourcing**
- 🔍 **Built-in Debug Output Support**
- 🧪 **Minimal Dependencies** (pure BASH)

## Components

### `bashdev-param`

A small, declarative CLI parser that supports:

- Short and long options (e.g., `-v` and `--verbose`)
- Flags and string parameters
- Descriptions for help generation

**Example:**

```bash
source bashdev-param

param::add -n "verbose" -s v -l verbose -t flag -d "Enable verbose mode"
param::add -n "file"    -s f -l file    -t string -d "Path to input file"

param::parse "$@"

[[ $(param::get verbose) == "true" ]] && echo "Verbose mode enabled"
echo "File: $(param::get file)"

bashdev-lib (optional)

A shared function library (if included) that contains:

    Logging utilities

    Safe file manipulation

    Validation helpers

Usage

    Source bashdev-param in your script.

    Define parameters using param::add.

    Parse with param::parse "$@".

    Retrieve values with param::get.

Requirements

    BASH 4.0 or later (associative array support)

    No external dependencies

License

This project is licensed under the GPLv3.

(c) 2025 Tom Brown
