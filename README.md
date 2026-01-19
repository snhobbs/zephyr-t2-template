# zephyr-t2-template
Zephyr RTOS T2 Topology Template

This is a template for a T2 zephyr project. The application is located in the root of the repo. 

Read more about topologies [here](https://docs.zephyrproject.org/latest/develop/west/workspaces.html).

## Installation & Setup 
Install the toolchain or use a container.

```sh
mkdir workspace & cd workspace
clone https://github.com/snhobbs/zephyr-t2-template
sh zephyr-t2-template/setup.sh
west update
```

This places the dependencies, including zephyr, in the workspace in directory `deps`. This keeps the workspace from getting cluttered, leaving most of the visual space for consequential locations like the projects. This path needs to agree with `path-prefix: deps` in `west.yml`.


The setup script sets the manifest file path automatically but if the directory name of the project is changed after the setup is run then the setup script will need to be re-run.

## Building 
Once setup we build from the workspace:

```sh 
west build zephyr-t2-template
```

