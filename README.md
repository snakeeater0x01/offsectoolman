# ![Screenshot 2023-08-05 at 8.41.32 PM](./Screenshot1.png)

**offsectoolman** is a tool manager designed to automate the setup of an offensive security lab. It allows you to install and manage various package managers and tools commonly used in offensive security tasks. The tool supports installation on Linux systems and provides a simple and efficient way to get your lab up and running quickly.

## Features

- **Package Managers Support:** Install, update, and remove tools using different package managers.
- **Tag Filtering:** Select tools based on tags for easier categorization and identification.
- **Type and Category Selection:** Choose tools based on their types and categories.
- **YAML Configuration:** Customize and add tools to the YAML configuration file.
- **Version Information:** Display the current version of OffSecToolMan.
- **Help Menu:** Access a detailed help message with the `-h` or `--help` option.

## Requirements

- Linux-based system
- Bash shell

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/offsectoolman.git
cd offsectoolman
```

2. Make the script executable:

```bash
chmod +x offsectoolman
```

## Running Directly from GitHub

You can run the `offsectoolman` script directly from GitHub without downloading or installing it on your system. Use the following one-liner command:

```
bash <(curl -sSL https://raw.githubusercontent.com/ousbaailyas/offsectoolman/master/offsectoolsman) [OPTIONS]
```
## Usage

```bash
./offsectoolman [-all] [-pm <package_managers>] [--tag <tags>] [--type <types>] [--category <categories>] [-i] [-ia] [-u] [-ua] [-r] [-ra] [-v] [-f <file>] [-h]
```

## Options

- **-all:** Select all available tools.
- **-pm, --managers:** Comma-separated list of package managers.
- **--tag:** Comma-separated list of tags.
- **--type:** Comma-separated list of types.
- **--category:** Comma-separated list of categories.
- **-l, --list:** List selected tools.
- **-i, --install:** Install selected tools.
- **-u, --update:** Update selected tools.
- **-r, --remove:** Remove selected tools.
- **-f, --file:** Specify the YAML configuration file.
- **-v, --version:** Print version.
- **-h, --help:** Print this help message.

## Adding Tools to YAML Configuration File

To add tools to the YAML configuration file, follow this structure:

```yaml

managers:
  # Tools based on Go package manager
  go:
    manager_action: "sudo apt install golang curl ca-certificates"
    actions:
      install: "go install -v"
      upgrade: "go get -u"
      remove: "go clean"

    tools:
      - name: pdtm
        source: github.com/projectdiscovery/pdtm/cmd/pdtm@latest
        description: "ProjectDiscovery's Open Source Tool Manager"
        properties:
          type: [CLI]
          category: [development]
          tag: [development, security, tool-manager]

      - name: smap
        source: github.com/s0md3v/smap/cmd/smap@latest
        description: "A fast network scanner designed for Internet-scale"
        properties:
          type: [CLI]
          category: [information-gathering]
          tag: [information-gathering, security, network, scanner]
....
```

## Version

To display the current version of OffSecToolMan, use the following command:

```bash
./offsectoolman -v
```

Feel free to explore the various options and customize your security toolset with OffSecToolMan!
