# zephyr-t2-template
Zephyr RTOS T2 Topology Template. A **T2 (star) topology** is a workspace where a single application owns the west manifest and defines the workspace configuration.

Read more about topologies [here](https://docs.zephyrproject.org/latest/develop/west/workspaces.html).


The `setup.sh` script initializes the west workspace, sets the manifest path,
and configures west to place all dependencies under `deps/`. The workspace will look like:

``` 

.
├── .west
│   └── config
├── app
│   ├── .git
│   ├── .gitignore
│   ├── CMakeLists.txt
│   ├── LICENSE
│   ├── README.md
│   ├── prj.conf
│   ├── setup.sh
│   ├── src
│   │   ├── dynamic_cmd.c
│   │   ├── login_cmd.c
│   │   ├── main.c
│   │   ├── test_module.c
│   │   └── uart_reinit.c
│   └── west.yml
├── deps
└── build
```

## Installation & Setup 
Install the toolchain or use a container.

```sh
mkdir workspace && cd workspace
git clone https://github.com/snhobbs/zephyr-t2-template
sh zephyr-t2-template/setup.sh
west update
```

This places the dependencies, including zephyr, in the workspace in directory `deps`. This keeps the workspace from getting cluttered, leaving most of the visual space for consequential locations like the projects. This path needs to agree with `path-prefix: deps` in `west.yml`.


If the project directory is renamed after setup, setup.sh must be re-run so west can update the manifest path.

## Building 
Once setup is complete, build from the workspace root.
Note that the application name can be anything, here we assume it's named `app`.

```sh 
west build app
```

