## Taskwarrior Commands

Taskwarrior lets you manage tasks from the command line. 

You can segment tasks per project (personal, work etc). 

## Commands

Tasks are managed with the `task` command.

### List tasks

```console
task list
```
Tasks are assigned an `id` which can be used when managing that task.

### Add tasks

```console
task add "do the washing"
```
Tasks will be set to the current context

### Complete task

```console
task done 12
```

### Set context

```console
task context work
```

### Add priority

```console
task add "build CLI tool" priority:H
```

### Update task priority

```console
task modify 12 priority:H
```
