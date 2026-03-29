# Script Executor — Python File Automation Tool

A Python automation tool built as a university project for the Linux Lab course at Birzeit University. It reads a script file containing file management commands, executes them, and writes the results to either a CSV or log file, all configured through a JSON file.

## How It Was Made

Written in Python using an object-oriented design with two classes. `commandExecuter` implements each supported file operation using Python's `os` module. `scriptExecuter` reads the script file, dispatches each command to `commandExecuter`, tracks results, and handles output. Configuration is loaded from a JSON file. CLI arguments are handled with `argparse` and all debug output goes through Python's `logging` module.

## Features

- Executes a script of file management commands read from a text file
- Supported commands: `Mv_last`, `Categorize`, `Count`, `Delete`, `Rename`, `List`, `Sort`
- `Categorize` splits files into subdirectories based on a configurable size threshold
- `Sort` supports sorting by name, size, or date
- Output results written as CSV or log file, with pass/fail status per command
- Older output files are automatically deleted when the log file limit is exceeded
- Full debug logging to `commandDebugger.log` for every command executed

## Configuration

The app reads from `configuration.json`:

```json
{
  "Threshold_size": "10KB",
  "Max_commands": 5,
  "Max_log_files": 7,
  "Same_dir": false,
  "Output": "csv"
}
```
