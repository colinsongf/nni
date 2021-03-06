# FAQ

This page is for frequent asked questions and answers.


### tmp folder fulled
nnictl will use tmp folder as a temporary folder to copy files under codeDir when executing experimentation creation. 
When met errors like below, try to clean up **tmp** folder first.
> OSError: [Errno 28] No space left on device

### Cannot get trials' metrics in OpenPAI mode
In OpenPAI training mode, we start a rest server which listens on 51189 port in nniManager to receive metrcis reported from trials running in OpenPAI cluster. If you didn't see any metrics from WebUI in OpenPAI mode, check your machine where nniManager runs on to make sure 51189 port is turned on in the firewall rule. 

### Segmentation Fault (core dumped) when installing
> make: *** [install-XXX] Segmentation fault (core dumped)

Please try the following solutions in turn:
* Update or reinstall you current python's pip like `python3 -m pip install -U pip`
* Install nni with `--no-cache-dir` flag like `python3 -m pip install nni --no-cache-dir`

### Job management error: getIPV4Address() failed because os.networkInterfaces().eth0 is undefined.
Your machine don't have eth0 device, please set nniManagerIp in your config file manually. [refer](https://github.com/Microsoft/nni/blob/master/docs/ExperimentConfig.md)

### Exceed the MaxDuration but didn't stop
When the duration of experiment reaches the maximum duration, nniManager will not create new trials, but the existing trials will continue unless user manually stop the experiment. 

### Could not stop an experiment using `nnictl stop`
If you upgrade your nni or you delete some config files of nni when there is an experiment running, this kind of issue may happen because the loss of config file. You could use `ps -ef | grep node` to find the pid of your experiment, and use `kill -9 {pid}` to kill it manually.

### Could not get `default metric` in webUI of virtual machines
Config the network mode to bridge mode or other mode that could make virtual machine's host accessible from external machine, and make sure the port of virtual machine is not forbidden by firewall. 

### Help us improve
Please inquiry the problem in https://github.com/Microsoft/nni/issues to see whether there are other people already reported the problem, create a new one if there are no existing issues been created.
