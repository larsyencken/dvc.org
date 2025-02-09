## queue kill

Kill actively running [DVC experiment] tasks (see `dvc queue start`).

[dvc experiments]: /doc/user-guide/experiment-management/experiments-overview

## Synopsis

```usage
usage: dvc queue kill [-h] [-q | -v] [<task> ...]

positional arguments:
  <task>         Tasks in queue to kill.
```

## Description

Forcefully stops execution of the specified (running) experiment tasks.

<admon type="warn">

Note that killed experiments will be considered failed runs and will not be
re-added to the queue for future execution.

</admon>

This command does not stop the `dvc queue start` worker(s). After the specified
task has been killed, a worker will move on to process the next experiment task
in the queue.

To kill all running experiments and also stop processing the queue, use
`dvc queue stop --kill`.

## Options

- `-h`, `--help` - prints the usage/help message, and exit.

- `-q`, `--quiet` - do not write anything to standard output.

- `-v`, `--verbose` - displays detailed tracing information.
