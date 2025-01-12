# autodoe

**DISCLAIMER: This project is under development and might not be fully functional.**

*autodoe* helps you generate, process and analyze experimental plans based on Design of Experiments. 

It generates experimental plans, maps the plan to your given factor values, creates a well ordered folder structure, processes given input scripts and analyzes the experiments output.
That might help you when you want to perform parameter analyses or create statistical significant data for machine learning based on an experiment or a simulation.

## Prerequisites
Before you begin, ensure you have met the following requirements:
* You have a Unix machine (Mac/Linux). Currently only tested with Ubuntu20.04
* You have python3.8 or newer and pip is installed
* You have a command line interface or script based experiment / simulation


## Installing autodoe
You can clone the git repo and run the program in a virtual environment:
```
git clone https://github.com/csRon/autodoe.git
cd autodoe
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
Test you installation by running the first example `helloDoE` by running
```
python3 autodoe.py ./examples/helloDoE
```
You should see some output of simulations running.

## Getting started
It is recommended to take a look at the given examples and its *readme*'s and the documentation for more detailed explanations. 
Some theoretical knowledge of Design of Experiments would also be advantageous.

Nevertheless the basic setup of autodoe remains the same. 


### Setting up your experiment environment
A working folder must be created with the following content (in some exceptional cases input can be different):
* `config.conf`: file contains your settings for the DoE Analysis
* `factors.csv`: file contains the factors you want to analyze with min and max values
* `templates`: folder contains all necessary input for your experiment of simulation

For the beginning just copy an existing exmample folder (e.g. helloDoE) to your preferred location and modify the files based on your needs. 

### Starting autodoe
Just run the following command directly inside the autodoe folder
```
python3 autodoe.py /path/to/your/working/folder
```
All output will also be in your selected working folder.

### Results
All output will be in your selected working folder. The results will be 2 files + 2 folders:
* `factorPlan.csv`: file contains the raw experimental plan with values between min and max of the factor value
* `rawPlan.csv`: file contains the raw experimental plan with values between 0 and 1
* `simulationFolder`: folder contains raw experiment / simulation results for each run of your experimental plan
* `results`: folder contains the combined results of all experiment / simulation runs as csv-file.


## Credits
The experimental plan creation is based on `pyDOE2` which is based on `pyDOE` created by: 
* Copyright (c) 2014, Abraham D. Lee (`pyDOE`)
* Copyright (c) 2018, Rickard Sjögren & Daniel Svensson (`pyDOE2`)

## License
autodoe is licensed under the MIT license.