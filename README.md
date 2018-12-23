# Microdegree Tempate

This repository contains scaffold-code to create micro-tau microdegrees. 

## Create a microdegree from scratch

[Ubuntu] is MicroTau's OS of choice for developing and maintaining microdregrees. Windows devs might consider using the [Windows Subsystem for Linux]. This instructions assume you are following this recommendation. 

[Ubuntu]: https://www.ubuntu.com/ 
[Windows Subsystem for Linux]: https://docs.microsoft.com/en-us/windows/wsl/about

Create the working directory for the microdegree and define the properties in a `microdegree.props` file. Consider an example microdegree named `microdegree-example`. Create the working dir:

```commandline
$ mkdir microdegree-example
$ cd microdegree-example
```

Now create a `microdegree.props` file with the following content:
```text
#!/usr/bin/env bash

export MICRODEGREE_NAME="Microdegree Example"
export MICRODEGREE_DESCRIPTION="This an example microdegree"
export MICRODEGREE_GITHUB_REPO="microdegree-example"
export MICRODEGREE_PACKAGE_NAME="example"
```

Some considerations:
* `MICRODEGREE_NAME` variable is used as a title in the microsite. Consider setting a name with less than 4 words.
* `MICRODEGREE_DESCRIPTION` variable will be shown as a header. Thus, consider using a short description. 
* `MICRODEGREE_GITHUB_REPO` must exactly match the name of the gitub repository. This is used to publish this microdegree into github pages.
* `MICRODEGREE_PACKAGE_NAME` is used for scala related source files.


With this in place, you can bootstrap the microdegree:

1. Load the environment variables.
    * `source microdegree.props`
2. Install bootstrap dependencies.
    * `sudo apt install curl wget`
3. Run the bootstrap script:
    * `curl -sSL https://raw.githubusercontent.com/micro-tau/microdegree-template/master/create-microdregree.sh | sh`

Note that this script creates all the files needed to run the microdegree site. For more configuration options, see the official [microsite] documentation.

[microsite]: https://github.com/47deg/sbt-microsites

To run the microdegree in local mode follow these steps:

1. Install the microdegree dependencies:
    * `source ./setup-scripts/ubuntu.sh`
    * **Note** that you might want to copy-paste the `GEM_HOME` env variable and add to path `$GEM_HOME/bin` into your commandline config file (e.g., `.bashrc`, `.zshrc`) for future usage of jekyll.
2. Run the microsite in local mode:
    * `./publish.sh --local`

## Developing a microdegree

To be defined.


