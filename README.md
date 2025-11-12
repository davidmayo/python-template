# David Mayo Python template

This is an opinionated Python template for use with [Copier](https://copier.readthedocs.io/en/stable/). It is designed to create a Python package, using the `src/package_name/__init__.py` structure.

It doesn't have a lot of customization options. My name and email are hard-coded in here. It assumes `uv` and `git` are on your path.

This should work on Windows and Linux. IDK about Mac.

This is only designed for templating new projects. Copier does have some "update an existing project" functionality, but I don't attempt to deal with any of that here.

## One weird thing

This will create a folder in your project root called `untracked/`. This folder is included in the .gitignore, such that nothing in it (other than its own .gitignore and a README.md) will be tracked in git. I find this useful in my projects for various reasons, but you might not.

## Usage

To create a project structure, run `uv sync`, and do some git initialization, run this command:

```bash
uvx copier copy gh:davidmayo/python-template . --trust
```

Note that this will create a new folder inside of your PWD. So if you give a project name of `"my_project"`, the project will be created at `$PWD/my_project/`

> [!WARNING]
> Running that command `--trust` allows arbitrary code execution of scripts in this repo. You can see the scripts that will run by looking at [copier.yml](./copier.yml) `_tasks` section. You can see that these are pretty innocuous commands, but caveat emptor.

To just copy the files, but don't run any of the follow-up commands, run

```bash
uvx copier copy gh:davidmayo/python-template . --skip-tasks
```

## CHANGELOG

### 0.1.0 - 2025-11-11
First version. Sorta works.

### 0.1.1 - 2025-11-11
README fixes