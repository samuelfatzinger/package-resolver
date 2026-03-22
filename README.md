# package-resolver

## Overview

The package-resolver tool downloads a package and all of its dependencies without installing it. It supports retrieving specific versions across platforms and ecosystems using Docker. The tool runs package downloads inside Docker containers matching the target environment.

## Supported Platforms

Package types include:

- Linux distribution packages (deb, rpm, apk, etc.)
- Programming language packages (Python, Node, etc.)

Currently supported: Ubuntu, CentOS, and Alpine (latest versions only).

Future versions may support selecting specific distribution versions.

## Requirements

**Docker is required:** [Install Docker](https://docs.docker.com/get-docker/)

## Installation

Install using pip:

```bash
$ python -m pip install all-package-resolver
```

## Usage

```bash
$ download-package [OPTIONS] COMMAND [ARGS]...
```

### Options

Available command-line options:

```
-v, --verbose                     Show logs
-o, --output-dir <output-dir>     Output directory
-c, --no-cleanup                  No cleanup
-h, --help                        Show usage information
```

### Commands

```
os   <distro> <package>                  Download a package for a specific OS distribution
lang <language> <lang-version> <package> Download a package for a specific language
```

## Examples

```bash
$ download-package os ubuntu vim
$ download-package -v lang python 3.10 boto3
$ download-package --output-dir="/dst/folder" lang python 3.6 boto3

# For multiple packages
$ download-package lang python 3.6 "boto3 requests"

$ download-package --help
```
