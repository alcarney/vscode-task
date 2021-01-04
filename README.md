# vscode-task.el

An attempt at writing some Elisp code that makes it easy to select and run
pre-defined [VSCode tasks][tasks.json] from within an Emacs session.

Builds on `project.el` for task discovery

## Usage

![demo](resources/demo.gif?raw=true)

The main entry point is a function `vscode-task-run`, you may want to bind it to
a key sequence

``` elisp
(global-set-key (kbd "C-c p t") 'vscode-task-run)
```

## Features

It currently only supports the simplest of task definitions.

``` json
{
  "tasks": [
    {
      "label": "Task Name",
      "type": "shell",
      "command": "some-command"
    }
  ]
}
```

## Limitations

This package cannot parse the full syntax of VSCode's `tasks.json` file as
VSCode accepts a less strict JSON syntax which can include comments and trailing
commas. In order for this package to read the file correctly these syntax
extensions must be removed.

[tasks.json]: https://code.visualstudio.com/docs/editor/tasks#_custom-tasks
