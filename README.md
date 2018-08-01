# Alpakka

Alpakka is a python project that extends pyang to automatically generate code skeletons from YANG statements. The primary goal is to generate code skeletons for the configuration of networks and network devices which are controlled by NETCONF or RESCONF.

## Getting Started

The following steps guide you through the installation process. Please be aware that the following instructions are only tested with the referenced versions of python and the required python libraries.

### Prerequisites

Python (version 3.5 or newer), pip and git are required to use this project.

### Installing

* The first step is to clone the two required repositories. The first repository is the *alpakka* project. It contains the wrapping engine and the required functionality to map YANG statements into the wrapped representation for the code generation step.

```
	git clone http://mgn-s-at-source.advaoptical.com/gitlab/anden/alpakka.git
```

* The second step is to clone the *wools* project. It adapts the wrapping engine of the *alpakka* project by applying specific handling for different programming languages and frameworks and implements the code generation process itself.

```
	git clone http://mgn-s-at-source.advaoptical.com/gitlab/anden/wools.git
```

* The next step is to install both projects and the required dependencies. It is recommended to install the *alpakka* project first and then the *wools* project. An example is given assuming that you cloned both repositories in your current folder. In case you want to work on the code of *alpakka* the `-e` flag can be used for the pip commands.

```
	cd alpakka
	pip install .
	cd ../wools
	pip install .
```

* After the installation of both projects is finished, it is recommended to verify that the correct version was installed. The following command lists all installed python packages:

```
	pip list
```

* The following packages are required in the listed versions all other packages could be installed in the latest versions.

	* python version: 3.5
	* pyang version: 1.7.3

## Running Alpakka

#### comandlinecall

The *alpakka* project could be called from the command line terminal by typing
```
	alpakka <options> <YANG source file>
```
#### possible options

The *alpakka* project provides the following command line options

* '--alpakka-output-path' (**required**)
	- output path for the generated classes
	- indicates the root directory of the java/maven project

* '-w; --wool' (**required**)
	- The Wool to use for knitting the code
	- indicates to wool, which is representing the different programming languages and frameworks

* '--wool-package-prefix'
	- package prefix to be prepended to the generated classes
	- could be for example the java name prefix like com.example

* '--akka-beans-only'
	- @Thomas was macht diese Option eigentlich?

* '-i; --interactive'
	- run alpakka in interactive mode by starting an IPython shell before template generation

