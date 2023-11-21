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


# Building Software

HORUS also uses <a href="https://docs.easybuild.io">EasyBuild</a> to allow users to build the software they need, and then use that in their jobs without needing to be 'root'. To build your software on HORUS using EasyBuild, follow the below steps:

- Log into <a href="https://wsu-ondemand.osris.org">HORUS Open OnDemand</a>, and create an interactive desktop session by clicking on ‘HORUS Desktop’

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/interactive_apps.png" alt="Interactive Apps"/>

- Specify the resources you need, including GPU details if needed, and click on Launch.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_resources.png" alt="Desktop Resources"/>

HORUS will allocate the resources and update the status to Running when it’s ready.

Once the desktop is ready, you’ll see what host it’s running on, and time remaining.

- Adjust the compression and image quality as desired. For slower connections, choose high compression and low image quality.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_launch.png" alt="Launch HORUS Desktop"/>

- Launch your HORUS Desktop, and then open a terminal window as shown.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/desktop_terminal.png" alt="Desktop Terminal"/>

In the terminal:
 
- Load the EasyBuild Environment by running the command `load_eb_env_vars`
- Search for the app build files you need. e.g. `eb -S miniconda`
- Select  the software and version you need and build it with the `eb` command as shown ( –prefix should point to a location in your home directory).

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/load_eb_env.png" alt="EasyBuild"/>

To use software:

- Update module path by running `module use <path-to-apps-modules>`
- Check available modules by running `module avail`
- Load the module you need as shown.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/load_apps_as_modules.png" alt="Load EB Modules"/>

For more information on the SLURM options you can use in your script, please see the documentation for the <a href="https://slurm.schedmd.com/sbatch.html">sbatch</a> command.


