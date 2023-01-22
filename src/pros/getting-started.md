# Getting Started

## Installation
As always, the [official documentation](https://pros.cs.purdue.edu/v5/getting-started/installation.html) is a pretty good place to look.

### VSCode
This is the recommended way to install pros. Simply go to the extensions page, and click install. This is platform agnostic.

### Linux
You can also install pros as a cli via the official python package.
```sh
# You will also need to install the arm toolchain with your package manager of choice
pip install pros-cli
```

### MacOS
You can also install pros as a cli via homebrew.
```sh
brew tap osx-cross/arm && brew install arm-gcc-bin # Installs the toolchain
brew install pros-cli
```

While the VSCode extension provides a gui to manage your project, we will only provide instructions for the CLI. This is because the gui uses the cli under the hood, and its better to know what it's actually doing. In addition, the cli gives more descriptive error messages when building, making it easier to debug. 

If you've installed pros as a package, simply open any terminal to get to the cli. If you're using the VSCode extension, click the "Integrated Terminal"
You can verify that pros is working using:
```sh
pros --version
```
> Note: If you're using the VSCode extension, the pros cli will only work in the integrated terminal.


## Your First Project
You can create a new pros project using:
```sh
pros conductor new-project /path/to/your/project
# If your terminal is currently in the folder you want to create the project in, you can use:
pros conductor new-project $(pwd)
```
> Tip: pros subcommands can be abreviated to their shortest unique letters, starting from the front. This command can be written as:
```sh
pros c n $(pwd)
```

if you get an error that looks like this:
```
Creating cold package with libc,libm,libpros,okapilib [ERRORS]
sh: line 1: arm-none-eabi-g++: command not found
make: *** [common.mk:229: bin/cold.package.elf] Error 127
ERROR - pros.cli.build:make - Failed to make project: Exit Code 2
Error: Failed to build
Sentry is attempting to send 1 pending error messages
Waiting up to 2 seconds
Press Ctrl-C to quit
```
its because you didn't install the toolchain.
