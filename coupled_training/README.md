# WRF + WRF-Hydro Coupled Training  <img src="https://ral.ucar.edu/sites/default/files/public/wrf_hydro_symbol_logo_2017_09_150pxby63px.png" width=100 align="right" />

# Overview
This is a container used for coupled WRF | WRF-Hydro training sessions and can be run locally.

This container includes the following:

* Ubuntu base image
* All system libraries required by WRF and WRF-Hydro
* Coupled WRF | WRF-Hydro and WPS built with the GNU compilers
* Geographical input data for the WPS geogrid utility
* Text editors - Vim and Nano
* Git version control system

## Requirements

The easiest and recommended way to run the coupled WRF | WRF-Hydro training lesson is via the wrfhydro/coupled_training Docker container, which has all software dependencies and data pre-installed.

* Docker >= v.17.12
* Web browser (Google Chrome recommended)

## Where to get help and/or post issues
If you have general questions about Docker, there are ample online resources including the excellent Docker documentation at https://docs.docker.com/.

If you have questions regarding the lessons please contact us here https://ral.ucar.edu/projects/wrf_hydro/contact.

The best place ask questions or post issues with these lessons is via the Issues page of the GitHub repository at https://github.com/NCAR/wrf_hydro_training/issues.

## How to run
Make sure you have Docker installed and that it can access your localhost ports. Most out-of-the-box
Docker installations accepting all defaults will have this configuration.

**NOTE: THE DEFAULT DOCKER CONFIGURATION IS FOR 2 CPUS, YOU MUST HAVE AT LEAST 2 CPUS AVAILABLE TO THE DOCKER DAEMON FOR THIS TRAINING**

**Step 1: Open a terminal or PowerShell session**

**Step 2: Pull the wrfhydro/coupled_training Docker container for the desired code version**

Each training container is specific to a release version of the WRF-Hydro source code, which can be found at https://github.com/NCAR/wrf_hydro_nwm_public/releases.
Issue the following command in your terminal to pull a specific version of the training
corresponding to your code release version. 

`docker pull wrfhydro/coupled_training:v5.1.2`

**Step 3: Start the coupled training Docker container**

Issue the following command in your terminal session to start the training Docker container.
`docker run --name wrf-hydro-coupled-training -p 8887:8888 -it wrfhydro/coupled_training:v5.1.2`

**Note: Port forwarding is setup with the -p 8887:8888 argument, which maps your localhost port to
the container port. If you already have something running on port 8887 on your localhost you will
need to change this number**

The container will start and perform a number of actions before starting the training.
* First, the container will pull a coupled test case.
* Second, the container will pull the coupled training lesson.
* Third, the container will launch a Jupyter Notebook server and echo the address to your terminal.

**Step 4: Open JupyterLab**

The lessons for this training are contained in the `~/wrf-hydro-training/lessons` folder. The
lessons are interactive and can execute code commands live. For more information on Jupyter
visit the project page at http://jupyter.org/.

