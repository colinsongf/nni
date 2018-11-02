# Neural Network Intelligence

[![MIT licensed](https://img.shields.io/badge/license-MIT-yellow.svg)](https://github.com/Microsoft/nni/blob/master/LICENSE)
[![Build Status](https://msrasrg.visualstudio.com/NNIOpenSource/_apis/build/status/Microsoft.nni)](https://msrasrg.visualstudio.com/NNIOpenSource/_build/latest?definitionId=6)
[![Issues](https://img.shields.io/github/issues-raw/Microsoft/nni.svg)](https://github.com/Microsoft/nni/issues?q=is%3Aissue+is%3Aopen)
[![Bugs](https://img.shields.io/github/issues/Microsoft/nni/bug.svg)](https://github.com/Microsoft/nni/issues?q=is%3Aissue+is%3Aopen+label%3Abug)
[![Pull Requests](https://img.shields.io/github/issues-pr-raw/Microsoft/nni.svg)](https://github.com/Microsoft/nni/pulls?q=is%3Apr+is%3Aopen)
[![Version](https://img.shields.io/github/release/Microsoft/nni.svg)](https://github.com/Microsoft/nni/releases)

NNI (Neural Network Intelligence) is a toolkit to help users run automated machine learning (AutoML) experiments. 
The tool dispatches and runs trial jobs generated by tuning algorithms to search the best neural architecture and/or hyper-parameters in different environments like local machine, remote servers and cloud.

<p align="center">
<img src="./docs/img/nni_arch_overview.png" alt="drawing" width="800"/>
</p>

## **Who should consider using NNI**
* Those who want to try different AutoML algorithms in their training code (model) at their local machine.
* Those who want to run AutoML trial jobs in different environments to speed up search (e.g. remote servers and cloud).
* Researchers and data scientists who want to implement their own AutoML algorithms and compare it with other algorithms.
* ML Platform owners who want to support AutoML in their platform.

## **Install & Verify**

**Install through pip** 	
* We only support Linux in current stage, Ubuntu 16.04 or higher are tested and supported. Simply run the following `pip install` in an environment that has `python >= 3.5`.	
```bash	
    python3 -m pip install --user nni
```

**Install through source code**
* We only support Linux (Ubuntu 16.04 or higher) in our current stage. 
* Run the following commands in an environment that has `python >= 3.5`, `git` and `wget`.
```bash	
    git clone -b v0.3.0 https://github.com/Microsoft/nni.git	
    cd nni	
    source install.sh	
```

**Verify install**	
* The following example is an experiment built on TensorFlow. Make sure you have **TensorFlow installed** before running it.	
* Download the examples via clone the source code.	
```bash	
    cd ~	
    git clone -b v0.3.0 https://github.com/Microsoft/nni.git
```
* Run the mnist example.
```bash
    nnictl create --config ~/nni/examples/trials/mnist/config.yml
```

* Wait for the message `INFO: Successfully started experiment!` in the command line. This message indicates that your experiment has been successfully started. You can explore the experiment using the `Web UI url`.
```
INFO: Starting restful server...
INFO: Successfully started Restful server!
INFO: Setting local config...
INFO: Successfully set local config!
INFO: Starting experiment...
INFO: Successfully started experiment!
-----------------------------------------------------------------------
The experiment id is egchD4qy
The Web UI urls are: http://223.255.255.1:8080   http://127.0.0.1:8080
-----------------------------------------------------------------------

You can use these commands to get more information about the experiment
-----------------------------------------------------------------------
         commands                       description
1. nnictl experiment show        show the information of experiments
2. nnictl trial ls               list all of trial jobs
3. nnictl log stderr             show stderr log content
4. nnictl log stdout             show stdout log content
5. nnictl stop                   stop an experiment
6. nnictl trial kill             kill a trial job by id
7. nnictl --help                 get help information about nnictl
-----------------------------------------------------------------------

```

## **Documentation**
* [Overview](docs/Overview.md)
* [Get started](docs/GetStarted.md)
## **How to**
* [Installation](docs/InstallNNI_Ubuntu.md)
* [Use command line tool nnictl](docs/NNICTLDOC.md)
* [Use NNIBoard](docs/WebUI.md)
* [Define search space](docs/SearchSpaceSpec.md)
* [Use NNI sdk] - *coming soon*
* [Config an experiment](docs/ExperimentConfig.md)
* [Use annotation]- *coming soon*
* [Debug](docs/HowToDebug.md)
## **Tutorials**
* [How to run an experiment on local (with multiple GPUs)?](docs/tutorial_1_CR_exp_local_api.md)
* [How to run an experiment on multiple machines?](docs/tutorial_2_RemoteMachineMode.md)
* [How to run an experiment on OpenPAI?](docs/PAIMode.md)
* [Try different tuners and assessors] - *coming soon*
* [How to run an experiment on K8S services?] - *coming soon*
* [Implement a customized tuner] - *coming soon*
* [Implement a customized assessor] - *coming soon*
* [Implement a custmoized weight sharing algorithm] - *coming soon*
* [How to integrate NNI with your own custmoized training service] - *coming soon*
### **Best practice**
* [Compare different AutoML algorithms] - *coming soon*
* [Serve NNI as a capability of a ML Platform] - *coming soon*

## **Contribute**
This project welcomes contributions and suggestions, we use [GitHub issues](https://github.com/Microsoft/nni/issues) for tracking requests and bugs.

Issues with the **good first issue** label are simple and easy-to-start ones that we recommend new contributors to start with.

To set up environment for NNI development, refer to the instruction: [Set up NNI developer environment](docs/SetupNNIDeveloperEnvironment.md)

Before start coding, review and get familiar with the NNI Code Contribution Guideline: [Contributing](docs/CONTRIBUTING.md)

We are in construction of the instruction for [How to Debug](docs/HowToDebug.md), you are also welcome to contribute questions or suggestions on this area.

## **License** 
The entire codebase is under [MIT license](https://github.com/Microsoft/nni/blob/master/LICENSE)

