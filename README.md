# GPT Engineer

[![Discord Follow](https://dcbadge.vercel.app/api/server/8tcDQ89Ej2?style=flat)](https://discord.gg/8tcDQ89Ej2)
[![GitHub Repo stars](https://img.shields.io/github/stars/AntonOsika/gpt-engineer?style=social)](https://github.com/AntonOsika/gpt-engineer)
[![Twitter Follow](https://img.shields.io/twitter/follow/antonosika?style=social)](https://twitter.com/AntonOsika)
![Agent protocol](https://github.com/AntonOsika/gpt-engineer/actions/workflows/validate_agent_protocol.yml/badge.svg)

**GPT Engineer is an AI tool that helps you build code. You specify what you want, the AI asks for clarification if needed, and then it builds it.**

GPT Engineer is designed to be easy to adapt and extend. It allows you to train your AI agent to generate code in the style you prefer. It can generate an entire codebase based on a prompt.

- [Demo](https://twitter.com/antonosika/status/1667641038104674306)

## Table of Contents
- [Project Philosophy](#project-philosophy)
- [Setup](#setup)
  - [Installation](#installation)
  - [API Key Setup](#api-key-setup)
  - [Running the Project](#running-the-project)
- [Usage](#usage)
  - [Creating New Code](#creating-new-code)
  - [Improving Existing Code](#improving-existing-code)
- [Results](#results)
- [Workflow](#workflow)

## Project Philosophy

Our project philosophy is centered around the following principles:

- **Simplicity**: We aim to make it easy for users to derive value from GPT Engineer. All computations are "resumable" and persisted to the filesystem for simplicity.
- **Flexibility**: GPT Engineer is designed to be flexible and easy to extend with your own "AI steps". These steps, defined in `steps.py`, are the building blocks of the AI's learning process.
- **Incremental Building**: We believe in gradually improving the user experience through high-level prompting and feedback mechanisms that the AI can learn from over time.
- **Fast Handovers**: We strive for quick and seamless transitions between the AI and the human user.

## Setup

### Installation

Choose either **stable** or **development**.

For **stable** release:

- `python -m pip install gpt-engineer`

For **development**:
- `git clone https://github.com/AntonOsika/gpt-engineer.git`
- `cd gpt-engineer`
- `python -m pip install -e .`
  - (or: `make install && source venv/bin/activate` for a venv)

### API Key Setup

Choose **one** of the following methods to set up your API key:

- Export env variable (you can add this to .bashrc so that you don't have to do it each time you start the terminal)
    - `export OPENAI_API_KEY=[your api key]`
- .env file:
    - Create a copy of `.env.template` named `.env`
    - Add your OPENAI_API_KEY in .env
- Custom model:
    - See [docs](https://gpt-engineer.readthedocs.io/en/latest/open_models.html), supports local model, azure, etc.

Check the [Windows README](./WINDOWS_README.md) for windows usage.

### Running the Project

There are two ways to work with GPT-engineer: new code mode (the default), and improve existing code mode (the `-i` option).

#### Creating New Code
- Create an empty folder for your project anywhere on your computer
- Create a file called `prompt` (no extension) inside your new folder and fill it with instructions
- Run `gpt-engineer <project_dir>` with a relative path to your folder
  - For example: `gpt-engineer projects/my-new-project` from the gpt-engineer directory root with your new folder in `projects/`

#### Improving Existing Code
- Locate a folder with code which you want to improve anywhere on your computer
- Create a file called `prompt` (no extension) inside your new folder and fill it with instructions for how you want to improve the code
- Run `gpt-engineer <project_dir> -i` with a relative path to your folder
  - For example: `gpt-engineer projects/my-old-project` from the gpt-engineer directory root with your folder in `projects/`

By running gpt-engineer you agree to our [terms](https://github.com/AntonOsika/gpt-engineer/blob/main/TERMS_OF_USE.md).

## Results

After running GPT Engineer, you can check the generated files in `projects/my-new-project/workspace`.

## Workflow

You can see all available options by running `gpt-engineer --help`.

For example:
- To improve any existing project, use the flag: `-i`
- To give feedback to/improve a gpt-engineer generated project, use: `--steps use_feedback`

**Alternatives**

You can check [Docker instructions](docker/README.md) to use Docker, or simply
do everything in your browser:

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/AntonOsika/gpt-engineer/codespaces)

## Features

GPT Engineer comes with a host of features that make it a powerful tool for code generation:

- **AI Identity**: You can specify the "identity" of the AI agent by editing the files in the `preprompts` folder. This allows you to customize the behavior and output of the AI.
- **Project Prompts**: By editing the `preprompts` and evolving how you write the project prompt, you can make the agent remember things between projects. This allows for a more personalized and consistent experience.
- **Step Logs**: Each step in `steps.py` will have its communication history with GPT4 stored in the logs folder. This allows you to review and understand the AI's learning process. You can rerun these logs with `scripts/rerun_edited_message_logs.py`.
- **Open Source Models**: GPT Engineer supports open source models, like WizardCoder. See the [documentation](https://gpt-engineer.readthedocs.io/en/latest/open_models.html) for example instructions.

## Vision

The GPT Engineer community is building an **open platform for developers to experiment with and build their personal code-generation toolbox**.

We welcome contributions from anyone interested in this vision. If you want to see our broader ambitions, check out the [roadmap](https://github.com/AntonOsika/gpt-engineer/blob/main/ROADMAP.md), and join our [discord](https://discord.gg/8tcDQ89Ej2) to get input on how you can [contribute](.github/CONTRIBUTING.md) to it.

We are currently looking for more maintainers and community organizers. If you are interested in an official role, please email anton.osika@gmail.com.


## Example

https://github.com/AntonOsika/gpt-engineer/assets/4467025/6e362e45-4a94-4b0d-973d-393a31d92d9b
˛
