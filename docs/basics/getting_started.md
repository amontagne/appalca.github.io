# Getting started

## Installation
Appa Build and Appa Run are available on PyPI.
Appa Build requires Python 3.9.X, where Appa Run can run on higher versions of Python.
As Appa Run is required by Appa Build, you can install both by using:
```
pip install appabuild
```

If you only need Appa Run, you can use:
```
pip install apparun
```

We recommend using virtualenv to limit the risks of package dependencies conflicts, that are likely to happen with Appa Build, as Brightway requires specific version of numpy to run.

### Installation with source code
If you intend to modify the source code, or change some package versions in requirements.txt, you can use:
```
git clone https://github.com/appalca/appabuild
pip install -r requirements.txt
```

## Usage
Appa Build and Appa Run most basic interface are their command line interfaces (CLIs).
Next CLI commands will allow to check if both packages are properly installed by to respectively build a sample impact model and run it.

### Appa Build
To test you Appa Build installation, you can set the project's directory with ```BRIGHTWAY2_DIR``` environment variable.
```
export BRIGHTWAY2_DIR=brightway2_project/
```

Documentation about the CLI can be obtained by running the following command:
```
appabuild --help
```

Here is an example of Appa Build CLI call to build the demo impact model:
```
appabuild lca build samples/conf/appalca_conf.yaml samples/conf/nvidia_ai_gpu_chip_lca_conf.yaml
```

Both arguments are covered in [Appa Build basics](appa_build_basics.md) section.

### Appa Run
You will need an environment variable to specify where are the impact models located.
```
export APPARUN_IMPACT_MODELS_DIR=samples/impact_models/
```

Documentation about the CLI can be obtained by running the following command:
```
apparun --help
```

Here is an example of Appa Run CLI call to use the demo impact model:
```
apparun compute nvidia_ai_gpu_chip samples/conf/parameters.yaml --output-file-path outputs/scores.yaml
```