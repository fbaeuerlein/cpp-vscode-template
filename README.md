# cpp-vscode-template <!-- omit in toc -->

A workspace template for coding C/C++ with Visual Studio Code

- [Overview](#overview)
- [Requirements](#requirements)
- [Usage](#usage)
- [Features](#features)
  - [CMake](#cmake)
  - [Docker](#docker)
  - [Devcontainer support](#devcontainer-support)
  - [Variants](#variants)
  - [Tasks](#tasks)
  - [Testing](#testing)
  - [Documentation](#documentation)
    - [Live Server](#live-server)
    - [Doxygen](#doxygen)

## Overview

This is a project template to start working with Visual Studio Code on a fresh Linux and CMake based C/C++ project.

## Requirements

To start hacking right away, firstly you need to install the following packages

- Visual Studio Code: [https://code.visualstudio.com/](https://code.visualstudio.com/)
- Docker (if you want to develop within a container): [https://docs.docker.com/get-docker/](https://docs.docker.com/get-docker/)
- Remote Container Extension for Visual Studio Code: [https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Usage

Simply clone this repository and copy it's content without the `.git*` files to the folder you want to start your new project in.

## Features

The following development features are covered by this repository.

### CMake

Within the dockerfile the latest distribution related version of CMake will be installed.
If you prefer another version, adapt the minimum required version in `CMakeLists.txt` in the workspace root.

### Docker

A dockerfile with all necessary dependencies is contained. It could be used for local development with dev containers or a CI pipeline for automated building.

### Devcontainer support

Within `.devcontainer/devcontainer.json` you can see the dev container configuration. I added all my personal favourite extensions. They will be installed automatically to your container if you use the dev container feature.

### Variants

Supported build variants:

- Debug, Release
- No instrumentation, Coverage, Address Sanitizer, Thread Sanitizer

### Tasks

Currently there are several tasks that deal with coverage generation. See my [coverage documentation](https://github.com/fbaeuerlein/cpp-vscode-guide/blob/master/doc/Coverage.md) from another project.

### Testing

I'm used to googletest, so I added the latest release within the `test` directory. I also provided a test executable sample. If you prefer a different testing framework, simply replace it.
For test management the Test Explorer and C++ TestMate extensions are installed.

### Documentation

For documentation purposes doxygen, plantuml and some markdown supporting extensions are installed. Also the necessary packages are considered in the dockerfile.

#### Live Server

If you are developing within the dev containers, opening a browser from the tasks is not possible. So use the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension to display HTML files (e.g. from doxygen or coverage). It automatically reloads the pages on change. So you don't even to do a reload!

Adapt the port settings in `.vscode/settings.json` and `.devcontainer/devcontainer.json` to connect on localhost to the specified port with your browser.

#### Doxygen

To adapt doxygen to your project settings adapt the `Doxyfile` in the workspace root.

- Update `PROJECT_NAME` according to your project
- Set `PLANTUML_JAR_PATH` to the path where `plantuml.jar` is located (defaulted to `/usr/share/plantuml`)
