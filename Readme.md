# StayOrGo

StayOrGo is a CLI tool that analyzes Go and Ruby dependencies to evaluate their popularity and maintenance status. This tool generates scores to help you decide whether to "Stay" with or "Go" from your dependencies. Results can be output in Markdown, CSV, or TSV formats.

## Features

- Scans Go (`go.mod`) and Ruby (`Gemfile`) dependency files
- Evaluates each library's popularity and maintenance status
- Outputs results in Markdown, CSV, or TSV formats

## Installation

To install this tool, you need a Go environment. Use the following command to install:

```bash
go install github.com/konyu/StayOrGo@latest
```

## Usage

To use StayOrGo, run the following command:

```bash
StayOrGo [flags]
```


### Flags

- `-i, --input`: Specify the file to read.
- `-f, --format`: Specify the output format (`csv`, `tsv`, `markdown`).
- `-g, --github-token`: Specify the GitHub token for authentication.
- `-v, --verbose`: Enable verbose output.
- `-c, --config`: Specify a configuration file to modify evaluation parameters.

## Examples

Example of evaluating Go dependencies in Markdown format:

```bash
StayOrGo go -g YOUR_GITHUB_TOKEN
```

Example of evaluating Ruby dependencies in CSV format:

```bash
StayOrGo ruby -i ./path/to/your/Gemfile -f csv --github-token YOUR_GITHUB_TOKEN
```

### Using GITHUB_TOKEN Environment Variable

If the `GITHUB_TOKEN` is set as an environment variable, the `-g` option is not required. You can run the command as follows:

```bash
export GITHUB_TOKEN=your_github_token
StayOrGo go
```

### Custom Parameter File with -c Option

You can specify a custom parameter file using the `-c` option. The configuration file should be in YAML format. Here is an example configuration:

```yaml
watchers: 1
stars: 2
forks: 3
open_pull_requests: 4
open_issues: 5
last_commit_date: -6
archived: -99999
```

To use this configuration file, run the command as follows:

```bash
your_command_here -c path/to/your/params.yml
```
Adding these examples will help users understand how to use environment variables and custom configuration files effectively.



## Development

If you want to contribute to this project, please follow these steps:

1. Fork the repository.
2. Create a new branch.
3. Commit your changes.
4. Submit a pull request.

## License

This project is licensed under the MIT License.

## Contributors

- [konyu](https://github.com/konyu)

## Reporting Issues

If you encounter any issues, please report them on [GitHub Issues](https://github.com/uzumaki-inc/StayOrGo/issues).