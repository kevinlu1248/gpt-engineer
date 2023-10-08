# GPT Engineer

[![Discord Follow](https://dcbadge.vercel.app/api/server/8tcDQ89Ej2?style=flat)](https://discord.gg/8tcDQ89Ej2)
[![GitHub Repo stars](https://img.shields.io/github/stars/AntonOsika/gpt-engineer?style=social)](https://github.com/AntonOsika/gpt-engineer)
[![Twitter Follow](https://img.shields.io/twitter/follow/antonosika?style=social)](https://twitter.com/AntonOsika)
![Agent protocol](https://github.com/AntonOsika/gpt-engineer/actions/workflows/validate_agent_protocol.yml/badge.svg)


**Specify what you want it to build, the AI asks for clarification, and then builds it.**

GPT Engineer is made to be easy to adapt, extend, and make your agent learn how you want your code to look. It generates an entire codebase based on a prompt.

- [Demo](https://twitter.com/antonosika/status/1667641038104674306)

## Project philosophy

- Simple to get value
- Flexible and easy to add new own "AI steps". See `steps.py`.
- Incrementally build towards a user experience of:
  1. high level prompting
  2. giving feedback to the AI that it will remember over time
- Fast handovers, back and forth, between AI and human
- Simplicity, all computation is "resumable" and persisted to the filesystem

## Table of Contents
1. [Setup](#setup)
2. [API Key Configuration](#api-key-configuration)
3. [Usage](#usage)
4. [Features](#features)
5. [Vision](#vision)
6. [Example](#example)

## Setup

There are two ways to install GPT Engineer: using the stable release or the development version.

### Stable Release

To install the stable release, run the following command in your terminal:

```bash
python -m pip install gpt-engineer
```

This command uses pip, Python's package installer, to download and install GPT Engineer from the Python Package Index (PyPI).

### Development Version

If you want to use the development version of GPT Engineer, you need to clone the repository and install the package from the source code. Run the following commands in your terminal:

```bash
git clone https://github.com/AntonOsika/gpt-engineer.git
cd gpt-engineer
python -m pip install -e .
```

The `pip install -e .` command installs the package in editable mode. This means that changes to the source code will be reflected in the installed package without needing to reinstall it.

Alternatively, you can use a virtual environment to isolate the dependencies of GPT Engineer from your global Python environment. To do this, run the following commands instead:

```bash
make install
source venv/bin/activate
```

## API Key Configuration

GPT Engineer uses the OpenAI API to generate code. To use the API, you need an API key, which is a unique identifier that authenticates requests associated with your project.

There are three ways to configure your API key in GPT Engineer:

### Environment Variable

You can export your API key as an environment variable. This means that the key will be available in your terminal session and can be accessed by GPT Engineer. To do this, run the following command in your terminal, replacing `[your api key]` with your actual API key:

```bash
export OPENAI_API_KEY=[your api key]
```

You can add this command to your .bashrc file to automatically set the environment variable every time you start a new terminal session.

### .env File

You can also store your API key in a .env file. To do this, create a copy of the `.env.template` file in the root directory of the project and name it `.env`. Then, open the .env file and replace `[your api key]` with your actual API key:

```bash
OPENAI_API_KEY=[your api key]
```

### Custom Model

If you have a custom model, you can configure GPT Engineer to use it instead of the OpenAI API. See the [documentation](https://gpt-engineer.readthedocs.io/en/latest/open_models.html) for instructions on how to do this. This method supports local models, Azure models, and others.

Check the [Windows README](./WINDOWS_README.md) for windows usage.

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

By running gpt-engineer you agree to our [terms](https://github.com/AntonOsika/gpt-engineer/blob/main/TERMS_OF_USE.md).

**Results**

Check the generated files in `projects/my-new-project/workspace`

**Workflow**

`gpt-engineer --help` lets you see all available options.

For example:
- To improve any existing project, use the flag: `-i`
- To give feedback to/improve a gpt-engineer generated project, use: `--steps use_feedback`

**Alternatives**

You can check [Docker instructions](docker/README.md) to use Docker, or simply
do everything in your browser:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/AntonOsika/gpt-engineer/codespaces)

## Features

You can specify the "identity" of the AI agent by editing the files in the `preprompts` folder.

Editing the `preprompts`, and evolving how you write the project prompt, is how you make the agent remember things between projects.

Each step in `steps.py` will have its communication history with GPT4 stored in the logs folder, and can be rerun with `scripts/rerun_edited_message_logs.py`.

You can also run with open source models, like WizardCoder. See the [documentation](https://gpt-engineer.readthedocs.io/en/latest/open_models.html) for example instructions.


## Vision
The gpt-engineer community is building the **open platform for devs to tinker with and build their personal code-generation toolbox**.

If you are interested in contributing to this, we would be interested in having you.

If you want to see our broader ambitions, check out the [roadmap](https://github.com/AntonOsika/gpt-engineer/blob/main/ROADMAP.md), and join
[discord](https://discord.gg/8tcDQ89Ej2)
to get input on how you can [contribute](.github/CONTRIBUTING.md) to it.

We are currently looking for more maintainers and community organizers. Email anton.osika@gmail.com if you are interested in an official role.


## Example

https://github.com/AntonOsika/gpt-engineer/assets/4467025/6e362e45-4a94-4b0d-973d-393a31d92d9b
˛
