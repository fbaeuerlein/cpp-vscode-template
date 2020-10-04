# cpp-vscode-template <!-- omit in toc -->

A workspace template for coding C/C++ with Visual Studio Code

- [Overview](#overview)
- [Requirements](#requirements)
- [Usage](#usage)
- [Features](#features)
  - [Docker](#docker)
  - [Devcontainer support](#devcontainer-support)
  - [Variants](#variants)
  - [Tasks](#tasks)
  - [Documentation](#documentation)
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

### Documentation

For documentation purposes doxygen, plantuml and some markdown supporting extensions are installed. Also the necessary packages are considered in the dockerfile.

#### Doxygen

To adapt doxygen to your project settings adapt the `Doxyfile` in the workspace root.

- Update `PROJECT_NAME` according to your project
