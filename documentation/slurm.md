---
layout: default
title : SLURM
tagline: Basic Overview
order: 20
group: documentation
subnavgroup: documentation
---
{% include JB/setup %}

SLURM is highly scalable cluster management and job scheduling system for large and small Linux clusters. In HORUS, you can use Open OnDemand to access compute resources, run and monitor your work, and download your work result once it's done processing. We show here how you can submit a job to a specific SLURM partition. If you would like to read more about SLURM, visit the official <a href="https://slurm.schedmd.com/quickstart.html">SLURM Quick Start User Guide</a>

To be able to submit a SLURM job in HORUS, you would need to know and set some parameters for SLURM scheduler so that your job can get scheduled on the right processing queue. To demonstrate this, we'll create a test bash script and set the SLURM parameters in the script as bash comments but with speciffic syntax. 

<h2>Create a New Job</h2>

Log into the <a href="https://wsu-ondemand.osris.org">HORUS Open OnDemand</a>, and navigate to the Job Composer as shown below:

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/ood-jobs-menu.png" alt="OnDemand Jobs"/>

You should now see a job template where you can view the job details and submit script. Click on "Open Editor" to put your script.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/ood_submit_script.png" alt="Submit Script"/>

In the editor window, enter the following bash code and click 'Save'

	#!/bin/bash
	# JOB HEADERS HERE
	# This sets the partition we’re requesting. Other options are lm and gp
	#SBATCH -p lc
	hostname
	sleep 60
	echo "Hello World from a HORUS large Compute (lc) node"

Go back to the previous page, and click on 'submit' as shown here:

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/ood_job_submit.png" alt="SLURM Job Submit"/>

To view all active jobs you submitted, go to the Open OnDemand home page, and then click on Jobs -> Active Jobs. It would list something like this:

<img style="width: 100%" src="{{IMAGE_PATH}}/documentation/slurm/ood_active_jobs.png" alt="Active Jobs"/>


For more information on the SLURM options you can use in your script, please see the documentation for the <a href="https://slurm.schedmd.com/sbatch.html">sbatch</a> command.


# Building Software

HORUS also uses <a hreff="https://www.eessi.io/docs/">European Environment for Scientific Software Installations (EESSI)</a> and <a href="https://docs.easybuild.io">EasyBuild</a> to allow users to build the software they need, and then use what they built in their jobs without needing to be 'root'. Here is how you can build your software on HORUS using EasyBuild:

Log into <a href="https://wsu-ondemand.osris.org">HORUS Open OnDemand</a>, and create an interactive desktop session by clicking on ‘HORUS Desktop’

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/interactive_apps.png" alt="Interactive Apps"/>

Specify the resources you need, including GPU details if needed, and click on Launch.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_resources.png" alt="Desktop Resources"/>

HORUS will allocate the resources and update the status to Running when it’s ready. Once the desktop is ready, you’ll see what host it’s running on, and time remaining.

Adjust the compression and image quality as desired. For slower connections, choose high compression and low image quality.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_launch.png" alt="Launch HORUS Desktop"/>

Launch your HORUS Desktop, and then open a terminal window as shown.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_terminal.png" alt="Desktop Terminal"/>

In the terminal window:
 
- Load the EESSI environment for your bash session by running the following: `source /usr/local/bin/load_eessi_env` 
- To search for a specific software in EESSI, you can run `module spider <key-word>`. For example, `module spider gcc` or `module spider easybuild`.
	- If you find the software you need in EESSI, you can just load it and use it without having to go through the build process. The command to load the software: `module load <software-name>`
- To search for an app build files in EasyBuild, run `eb -S <app-key-word>`.
	- Select the software and version you need from EasyBuild and build it with the `eb` command like this: `eb <app-name.eb> --robot --prefix <path-to-your-eb-app-dir>` ( –prefix should point to a location in your home directory, and this directory location will be used to software you build).

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/load_eessi_and_eb2.png" alt="EasyBuild"/>


To use the software in your code:

If you're using a software from the EESSI software stack, all you need to do is loading the EESSI environment, and then the software. As an example, to use Perl, run the below two commands:

- `source /usr/local/bin/load_eessi_env`
- `module load Perl`

But if you would like to use software you built using EasyBuild, then you need to:

- Load EESSI and EasyBuild by running: `source /usr/local/bin/load_eessi_env` 
- Update module path by running: `module use <path-to-your-eb-app-dir>/modules/all`
- Optional: Check available modules by running `module avail`. (You don't need to run this in your code, but this would be useful when you're trying the steps manually in bash and would like to see what modules are available to load in your environment)
- Load the module you need, for example `module load Miniconda3/23.5.2-0` to laod Miniconda v23.5.2.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/load_apps_as_modules.png" alt="Load EB Modules"/>



