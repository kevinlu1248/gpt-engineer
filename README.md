# GPT Engineer

GPT Engineer is an AI-powered tool that helps you generate code based on your specifications. Simply specify what you want it to build, and the AI will ask for clarification if needed, and then build it. It's designed to be easy to adapt and extend, allowing you to train your AI agent to generate code in the style you prefer.

## Table of Contents
- [Project Philosophy](#project-philosophy)
- [Setup](#setup)
- [Usage](#usage)
- [Features](#features)
- [Vision](#vision)
- [Example](#example)

## Project Philosophy

GPT Engineer is built with the following principles in mind:

- Simplicity: It's easy to get value from the tool.
- Flexibility: You can easily add your own "AI steps". See `steps.py`.
- Incremental Improvement: The tool is designed to improve over time, learning from your feedback.
- Fast Handovers: The tool allows for quick back-and-forth interactions between the AI and the human user.
- Persistence: All computation is "resumable" and persisted to the filesystem.

## Setup

You can choose either the **stable** or **development** version of GPT Engineer.

For the **stable** release, run the following command:

```bash
python -m pip install gpt-engineer
```

For the **development** version, clone the repository and install the package:

```bash
git clone https://github.com/AntonOsika/gpt-engineer.git
cd gpt-engineer
python -m pip install -e .
```

You can also use a virtual environment:

```bash
make install && source venv/bin/activate
```

## Usage

There are two ways to use GPT Engineer: new code mode (the default), and improve existing code mode (the `-i` option).

### Creating New Code

1. Create an empty folder for your project anywhere on your computer.
2. Create a file called `prompt` (no extension) inside your new folder and fill it with instructions.
3. Run `gpt-engineer <project_dir>` with a relative path to your folder.

For example:

```bash
gpt-engineer projects/my-new-project
```

### Improving Existing Code

1. Locate a folder with code which you want to improve anywhere on your computer.
2. Create a file called `prompt` (no extension) inside your new folder and fill it with instructions for how you want to improve the code.
3. Run `gpt-engineer <project_dir> -i` with a relative path to your folder.

For example:

```bash
gpt-engineer projects/my-old-project -i
```

By running GPT Engineer, you agree to our [terms of use](https://github.com/AntonOsika/gpt-engineer/blob/main/TERMS_OF_USE.md).

## Features

You can specify the "identity" of the AI agent by editing the files in the `preprompts` folder. This allows you to customize the behavior of the AI and make it remember things between projects.

Each step in `steps.py` will have its communication history with GPT4 stored in the logs folder, and can be rerun with `scripts/rerun_edited_message_logs.py`.

You can also run GPT Engineer with open source models, like WizardCoder. See the [documentation](https://gpt-engineer.readthedocs.io/en/latest/open_models.html) for example instructions.

## Vision

The GPT Engineer community is building an open platform for developers to tinker with and build their personal code-generation toolbox. If you're interested in contributing, we'd love to have you. Check out our [roadmap](https://github.com/AntonOsika/gpt-engineer/blob/main/ROADMAP.md) and join our [Discord](https://discord.gg/8tcDQ89Ej2) to learn how you can contribute.

We're currently looking for more maintainers and community organizers. If you're interested in an official role, email anton.osika@gmail.com.

## Example

Check out this [example](https://github.com/AntonOsika/gpt-engineer/assets/4467025/6e362e45-4a94-4b0d-973d-393a31d92d9b) of what GPT Engineer can do.
