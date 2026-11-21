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
	# This sets the partition we’re requesting. The others are batch (the default), lm and lg: see the table below
	#SBATCH -p lc
	# Memory for the whole job on its node; see "Memory" below
	#SBATCH --mem=2G
	hostname
	sleep 60
	echo "Hello World from a HORUS large Compute (lc) node"

Go back to the previous page, and click on 'submit' as shown here:

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/ood_job_submit.png" alt="SLURM Job Submit"/>

To view all active jobs you submitted, go to the Open OnDemand home page, and then click on Jobs -> Active Jobs. It would list something like this:

<img style="width: 100%" src="{{IMAGE_PATH}}/documentation/slurm/ood_active_jobs.png" alt="Active Jobs"/>


<h2>Partitions</h2>

<table class="styled-table">
    <thead>
        <tr><th>Partition</th><th>Nodes</th><th>Each node</th><th>Default memory per CPU</th><th>Limits</th></tr>
    </thead>
    <tbody>
        <tr><td>batch (default)</td><td>6 Dell R6525 (um-lc01/02, msu-lc01/02, wsu-lc01/02)</td><td>256 CPUs, 500 GiB</td><td>4,000 MB (at most 4,050)</td><td>-</td></tr>
        <tr><td>lc</td><td>the same 6 nodes</td><td>256 CPUs, 500 GiB</td><td>2,000 MB</td><td>2 days 2 hours per job; at most 240 CPUs per node</td></tr>
        <tr><td>lm (large memory)</td><td>6 Dell R6525</td><td>96 CPUs, about 1 TiB</td><td>2,000 MB</td><td>-</td></tr>
        <tr><td>lg</td><td>7 Lenovo SR665 V3</td><td>384 CPUs, about 1.5 TiB, 894 GB local /scratch</td><td>3,000 MB</td><td>at most 192 CPUs per node; mostly used by OSG jobs</td></tr>
    </tbody>
</table>

A job in <code>lc</code> that asks for more than 2 days 2 hours, or for no time limit, stays pending with the reason <code>PartitionTimeLimit</code>.

<h2>Memory</h2>

Since November 2026 each job is held to the memory it requests:

- Ask for memory with `#SBATCH --mem=8G` (for the whole job on each node) or `#SBATCH --mem-per-cpu=4G`. Without either, the job gets the partition's default per CPU (table above).
- A job may use up to 10% more than it asked for. In that margin it is slowed down while the system reclaims memory.
- A job that goes beyond that is stopped, and its state is `OUT_OF_MEMORY`. Other jobs and the node are not affected.
- To see what a finished job used: `sacct -j <jobid> -o JobID,ReqMem,MaxRSS,State`. `MaxRSS` can include file cache, so it may be a little higher than the job really needed. Ask for somewhat more than the peak you see.

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

<img style="width: 85%" src="{{IMAGE_PATH}}/documentation/slurm/load_eessi_and_eb2.png" alt="EasyBuild"/>


To use the software in your code:

If you're using a software from the EESSI software stack, all you need to do is loading the EESSI environment, and then the software. As an example, to use Perl, run the below two commands:

- `source /usr/local/bin/load_eessi_env`
- `module load Perl`

But if you would like to use software you built using EasyBuild, then you need to:

- Load EESSI and EasyBuild by running: `source /usr/local/bin/load_eessi_env` 
- Update module path by running: `module use <path-to-your-eb-app-dir>/modules/all`
- Optional: Check available modules by running `module avail`. (You don't need to run this in your code, but this would be useful when you're trying the steps manually in bash and would like to see what modules are available to load in your environment)
- Load the module you need, for example `module load Miniconda3/23.5.2-0` to load Miniconda v23.5.2.

<img style="width: 50%" src="{{IMAGE_PATH}}/documentation/slurm/load_apps_as_modules.png" alt="Load EB Modules"/>



