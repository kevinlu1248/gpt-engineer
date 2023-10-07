# GPT Engineer

[![Discord Follow](https://dcbadge.vercel.app/api/server/8tcDQ89Ej2?style=flat)](https://discord.gg/8tcDQ89Ej2)
[![GitHub Repo stars](https://img.shields.io/github/stars/AntonOsika/gpt-engineer?style=social)](https://github.com/AntonOsika/gpt-engineer)
[![Twitter Follow](https://img.shields.io/twitter/follow/antonosika?style=social)](https://twitter.com/AntonOsika)
![Agent protocol](https://github.com/AntonOsika/gpt-engineer/actions/workflows/validate_agent_protocol.yml/badge.svg)

GPT Engineer is a tool that allows you to specify what you want it to build, the AI asks for clarification, and then builds it. It is designed to be easy to adapt, extend, and make your agent learn how you want your code to look. It generates an entire codebase based on a prompt. This tool is for developers who want to automate the process of code generation and improve their productivity.

## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)

## Introduction
GPT Engineer is made to be easy to adapt, extend, and make your agent learn how you want your code to look. It generates an entire codebase based on a prompt. This tool is for developers who want to automate the process of code generation and improve their productivity.

## Installation
Choose either **stable** or **development**.

For **stable** release:
- `python -m pip install gpt-engineer`

For **development**:
- `git clone https://github.com/AntonOsika/gpt-engineer.git`
- `cd gpt-engineer`
- `python -m pip install -e .`
  - (or: `make install && source venv/bin/activate` for a venv)

## Usage
There are two ways to work with GPT-engineer: new code mode (the default), and improve existing code mode (the `-i` option).

### Creating new code
- Create an empty folder for your project anywhere on your computer
- Create a file called `prompt` (no extension) inside your new folder and fill it with instructions
- Run `gpt-engineer <project_dir>` with a relative path to your folder
  - For example: `gpt-engineer projects/my-new-project` from the gpt-engineer directory root with your new folder in `projects/`

### Improving Existing Code
- Locate a folder with code which you want to improve anywhere on your computer
- Create a file called `prompt` (no extension) inside your new folder and fill it with instructions for how you want to improve the code
- Run `gpt-engineer <project_dir> -i` with a relative path to your folder
  - For example: `gpt-engineer projects/my-old-project` from the gpt-engineer directory root with your folder in `projects/`

## Examples
Check the generated files in `projects/my-new-project/workspace`

## Contributing
If you are interested in contributing to this, we would be interested in having you. If you want to see our broader ambitions, check out the [roadmap](https://github.com/AntonOsika/gpt-engineer/blob/main/ROADMAP.md), and join [discord](https://discord.gg/8tcDQ89Ej2) to get input on how you can [contribute](.github/CONTRIBUTING.md) to it. We are currently looking for more maintainers and community organizers. Email anton.osika@gmail.com if you are interested in an official role.

## License
By running gpt-engineer you agree to our [terms](https://github.com/AntonOsika/gpt-engineer/blob/main/TERMS_OF_USE.md).
