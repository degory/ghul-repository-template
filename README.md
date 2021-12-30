# ghūl repository template

[![CI/CD](https://img.shields.io/github/workflow/status/degory/ghul-repository-template/CICD)](https://github.com/degory/ghul-repository-template/actions?query=workflow%3ACICD)
[![Release](https://img.shields.io/github/v/release/degory/ghul-repository-template?label=release)](https://github.com/degory/ghul-repository-template/releases)
[![Release Date](https://img.shields.io/github/release-date/degory/ghul-repository-template)](https://github.com/degory/ghul-repository-template/releases) 
[![Issues](https://img.shields.io/github/issues/degory/ghul-repository-template)](https://github.com/degory/ghul-repository-template/issues) 
[![License](https://img.shields.io/github/license/degory/ghul-repository-template)](https://github.com/degory/ghul-repository-template/blob/main/LICENSE)
[![ghūl](https://img.shields.io/badge/gh%C5%ABl-100%25!-information)](https://ghul.io)


This is a GitHub template repository for quick-starting a [ghūl language](https://ghul.io)  project:

- The target is a .NET 6.0 application
- The standard [ghūl development container image](https://hub.docker.com/r/ghul/devcontainer) is pre-configured
- The project is pre-configured for rich language support and build tasks in Visual Studio Code
- Continuous integration is supported via a basic build and test pipeline running on GitHub Actions

## Prerequisites

You'll need a development environment with the [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0) installed.

## Recommended

[Visual Studio Code](https://code.visualstudio.com/) plus the [ghūl language Visual Studio Code extension](https://marketplace.visualstudio.com/items?itemName=degory.ghul) will give you rich language support, including:
  - syntax highlighting
  - error highlighting as you type
  - code snippets
  - symbol information on hover
  - intelligent code completion
  - function signature help
  - find uses
  - go to/peek definition
  - go to symbol in file
  - go to symbol in workspace
  - go to implementations
  - rename symbol across workspace
 
## Creating your ghūl project repository from the template

Click the ['Use this template'](https://github.com/degory/ghul-repository-template/generate) button.

## Opening your new ghūl project repo

The quickest way to get started is to open your repo in a GitHub [Codespace](https://github.com/features/codespaces)

Another quick and easy option, if you have Docker on your development machine, is to use the Visual Studio Code [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension.

Alternatively, clone the repo to a workspace on a host that supports the [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)

## Building your ghūl application

Assuming you're using Visual Studio Code, the default build task is auto-configured and you can build the application with either:
- `<Ctrl>` + `<Shift>` + `B`, or
- `<Ctrl>` + `<Shift>` + `P`, choose `Run Task`, then choose the build task from the list

Or you can build from the the command line using standard .NET SDK commands

```
$ dotnet build
```

## Running your application

The build output is a simple .NET console application (`example-project`). The application can be run via the pre-configured VSCode test task: 
- `Ctrl` + `Shift` + `P`, choose `Run Task`, choose the run task from the list

Or it can be run from the command line with:
```
$ dotnet run
```

## CI/CD pipeline

The template includes a basic CI/CD pipeline built with GitHub actions (see `.github/workflows/cicd.yml`)

On every pull request the pipeline will:
- Bump the version number and tags the repo
- Build the feature branch
- Run a couple of simple example tests
- Package the project
- Optionally push the package to GitHub with a beta version number

For pushes to main, the pipeline will also:
- Optionally push the the package to GitHub and NuGet.org
- Create a new release with a changelog based on the the commit log

## Extending your application

- The sample application executable is named `example-project`. You can change this by renaming `example-project.ghulproj`
- Add additional `.ghul` source files to the `src/` folder
- Reference additional NuGet packages via 'dotnet package add ...'

## Nice to have
ghūl code looks best in the [Fira Code](https://github.com/tonsky/FiraCode) font. Fira Code combined with the `ss07` ligatures setting in `settings.json` gives the preferred rendering of ghūl operators/