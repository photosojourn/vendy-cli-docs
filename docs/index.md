# Welcome to Vendy

<!-- markdownlint-disable-next-line -->
<center>![Vendy Logo](img/favicon.ico "Vendy")</center>

Vendy is a cli tool designed to make the deployment of scaffolding code in any language easier. Built using CookieCutter the idea is to create a tool which can quickly bootstrap projects not just for Python, but other language based tools such as Terraform or Ansible. The tool was built with two aims, increase speed of engineers when starting projects, and improve alignment with code standards by make use of templates effortless.

## Installation

Installtion is best done using [pipx](https://pipx.pypa.io)

` pipx install vendy-cli `

## Getting started

After installation the first step is to add template repoistory to your configuration using the `add` command:

```Bash
vendy add example-template git@github.com:user/example-template.git
```

This command has to key inputs, the first is the name you want to give the template. The second is a valid Git URL (either SSH or HTTP). Note that Vendy assumes auth is already configured with via keys or in your git client configuration.

Now with the template in place we can deploy it:

```Bash
vendy deploy example-template
```

Next you will be prompted for values (e.g project name) based on the templates configuration.

## Commands

* `version`   Show the currently installed version
* `list`      List install templates.(also 'ls')
* `add`       Add a new template
* `remove`    Remove a template. (also 'rm')
* `deploy`    Deploy a new instance of a given template

## Configuration

The configuration of templates and file are held in a YAML file called `.vendy/config.yaml` and can be updated either via the `add` or `remove` cli commands or in your editor of choice.

## Template creation

At the moment Vendy used [CookieCutter](https://github.com/cookiecutter/cookiecutter) for templating and repoistory layout. Documentation on how to create a CookieCutter from scratch can be found [here](https://cookiecutter.readthedocs.io/en/stable/tutorials/tutorial2.html)