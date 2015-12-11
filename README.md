# AWS Container Service (ECS) CLI utils

Pack of CLI commands useful for working with Amazon AWS Container Service.

## Installation

1. (Prereq) Install `awscli` (https://aws.amazon.com/cli/) and `jq` (https://stedolan.github.io/jq/)
2. Make sure you have `aws` configured with stored authentication
4. Download `*.sh` files from this repository
5. Add them to your `/usr/local/bin`
6. Add path to your ECS PEM file to `ECS_PEM_FILE` environment variable

## Commands

### `ecs-console`

Connect to running container of specific service

```bash
ecs-console cluster-name service-name
```

### `ecs-task-shell`

Start task and connect to its shell. Stops tasks after shell is exited.

```bash
ecs-task-shell cluster-name task-definition-name[:version]
```
