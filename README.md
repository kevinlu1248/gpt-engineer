# GPT Engineer

[![Discord Follow](https://dcbadge.vercel.app/api/server/8tcDQ89Ej2?style=flat)](https://discord.gg/8tcDQ89Ej2)
[![GitHub Repo stars](https://img.shields.io/github/stars/AntonOsika/gpt-engineer?style=social)](https://github.com/AntonOsika/gpt-engineer)
[![Twitter Follow](https://img.shields.io/twitter/follow/antonosika?style=social)](https://twitter.com/AntonOsika)
![Agent protocol](https://github.com/AntonOsika/gpt-engineer/actions/workflows/validate_agent_protocol.yml/badge.svg)


**Specify what you want it to build, the AI asks for clarification, and then builds it.**

GPT Engineer is made to be easy to adapt, extend, and make your agent learn how you want your code to look. It generates an entire codebase based on a prompt.

- [Demo](https://twitter.com/antonosika/status/1667641038104674306)

## Project philosophy

Our project philosophy is based on the following principles:

- **Simplicity**: We aim to make it simple for users to get value from our tool.
- **Flexibility**: Our tool is flexible and easy to adapt. Users can add their own "AI steps" (see `steps.py` for more information).
- **Incremental Building**: We strive to incrementally build towards a user experience that involves high-level prompting and the ability to give feedback to the AI that it will remember over time.
- **Fast Handovers**: We believe in fast handovers, back and forth, between AI and human.
- **Persistence**: All computation is "resumable" and persisted to the filesystem for simplicity and ease of use.

## Setup

Choose either **stable** or **development**.

For **stable** release:

- Open your terminal.
- Run the command `python -m pip install gpt-engineer`.

For **development**:

- Open your terminal.
- Run the command `git clone https://github.com/AntonOsika/gpt-engineer.git` to clone the repository.
- Navigate to the cloned repository by running `cd gpt-engineer`.
- Install the necessary dependencies by running `python -m pip install -e .`.
  - Alternatively, you can create a virtual environment by running `make install && source venv/bin/activate`.

**API Key**

Choose **one** of:
- Export env variable (you can add this to .bashrc so that you don't have to do it each time you start the terminal)
    - `export OPENAI_API_KEY=[your api key]`
- .env file:
    - Create a copy of `.env.template` named `.env`
    - Add your OPENAI_API_KEY in .env
- Custom model:
    - See [docs](https://gpt-engineer.readthedocs.io/en/latest/open_models.html), supports local model, azure, etc.

Check the [Windows README](./WINDOWS_README.md) for windows usage.

## Usage

There are two ways to work with GPT-engineer: new code mode (the default), and improve existing code mode (the `-i` option).

### Creating new code
To create new code:

1. Create an empty folder for your project anywhere on your computer.
2. Inside your new folder, create a file called `prompt` (no extension) and fill it with instructions. For example, you might write "Create a Python function that calculates the factorial of a number."
3. Run `gpt-engineer <project_dir>` with a relative path to your folder. For example, if you're in the gpt-engineer directory root and your new folder is in `projects/`, you would run `gpt-engineer projects/my-new-project`.

### Improving Existing Code
To improve existing code:

1. Locate a folder with code which you want to improve anywhere on your computer.
2. Inside this folder, create a file called `prompt` (no extension) and fill it with instructions for how you want to improve the code. For example, you might write "Refactor the function `calculate_factorial` to use recursion."
3. Run `gpt-engineer <project_dir> -i` with a relative path to your folder. For example, if you're in the gpt-engineer directory root and your folder is in `projects/`, you would run `gpt-engineer projects/my-old-project -i`.

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

- **AI Identity Customization**: You can specify the "identity" of the AI agent by editing the files in the `preprompts` folder. This allows you to customize the behavior and output of the AI.
- **Prompt Evolution**: Editing the `preprompts`, and evolving how you write the project prompt, is how you make the agent remember things between projects. This allows for a more personalized and consistent experience.
- **Communication History**: Each step in `steps.py` will have its communication history with GPT4 stored in the logs folder, and can be rerun with `scripts/rerun_edited_message_logs.py`. This allows for easy debugging and improvement of the AI's performance.
- **Open Source Model Support**: You can also run with open source models, like WizardCoder. See the [documentation](https://gpt-engineer.readthedocs.io/en/latest/open_models.html) for example instructions. This provides flexibility and allows you to use the model that best suits your needs.

## Contributing

We welcome contributions from the community! If you're interested in contributing, here's how you can get started:

- **Issues**: If you find a bug or want to suggest a new feature, please create an issue in our GitHub repository.
- **Pull Requests**: If you want to contribute code, please fork the repository, make your changes, and submit a pull request. We'll review it as soon as we can.
- **Code of Conduct**: We expect all contributors to follow our code of conduct. Please make sure to read it before contributing.

## Contact

If you have any questions or want to get in touch with the project maintainers, you can reach us at:

- Email: anton.osika@gmail.com
- Discord: [GPT Engineer Discord](https://discord.gg/8tcDQ89Ej2)


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
