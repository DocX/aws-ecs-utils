# AWS Container Service (ECS) CLI utils

Pack of useful CLI commands for working with Amazon AWS Container Service.

## Installation

1. (Prereq) Install `awscli` (https://aws.amazon.com/cli/) and `jq` (https://stedolan.github.io/jq/)
2. Make sure you have `aws` configured with stored authentication
4. Download `*.sh` files from this repository
5. Add them to your `/usr/local/bin`
6. Add path to your ECS PEM file to `ECS_PEM_FILE` environment variable

## Commands

### `ecs-console`

Connect to running container of specific service. 

```bash
ecs-console cluster-name service-name
```

This is useful to investigate inner state of processes inside container or run processes with available environment variables from task definition.

Warning: Be aware that you are inside container that runs the main process already. Starting heavy processes may cause the whole container will run out of memory and be killed.


### `ecs-task-shell`

Start new ECS task with overridden CMD to `sleep 30m` and connect to its shell. Stops tasks after shell is exited.

```bash
ecs-task-shell cluster-name task-definition-name[:version]
```

This is useful to run your app framework console (like `rails console`) within environment of your ECS service or task without affecting containers running services.

