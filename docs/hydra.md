!!! info "The most up to date information regarding Hydra can be found at [computing.si.edu/hydra](https://computing.si.edu/hydra/)"
    This page is a short NZCBI introduction. The Hydra user documentation covers logging in, running jobs, storage, software and data transfer in full.

Hydra is the Smithsonian's high-performance computing (HPC) cluster. It is a shared set of compute nodes for analyses that are too large or too slow for a laptop. NZCBI researchers use it for genome assembly, phylogenetics, image analysis, simulations and bioacoustic processing.

Work on Hydra is done from a terminal on a login node. Data goes on the cluster's storage, and analyses are submitted as jobs to a scheduler, which runs them on the compute nodes. Hydra is reachable only from the Smithsonian network, the SI VPN, or [telework.si.edu](https://telework.si.edu).

## Request an account

Accounts are requested through the [HPC Account Request](https://smithsonianprod.servicenowservices.com/si?id=sc_cat_item&sys_id=962e05331b96e05078932f41f54bcb3b) in the SI Service Portal. The welcome email gives the username and a link to set the password. Every new user must watch the [Introduction to Hydra](https://computing.si.edu/hydra/getting-started/training/) video before running a job.

## RStudio Server

Many NZCBI researchers work in R through Hydra's RStudio Server at [galaxy.si.edu/R4](https://galaxy.si.edu/R4). It runs RStudio in a web browser on a large shared node, with Hydra's filesystems available. Nothing needs to be installed and no job needs to be submitted. Sign in with a Hydra username and password. Quit the session from the **Session** menu when finished, because an idle session holds memory other users need.

See [Guide 5: Running R-Studio from Hydra](RStudio-Hydra.md) and the [RStudio server](https://computing.si.edu/hydra/interactive/rstudio/) page of the Hydra documentation.

## Storage

Each user has space on three filesystems. Quotas are in the hundreds of gigabytes on `/home` and in the terabytes on `/scratch` and `/data`.

| Filesystem | Use it for |
|---|---|
| `/home` | scripts, job files and configuration |
| `/scratch` | input data and working files for jobs; the fastest filesystem |
| `/data` | final results and small important files |

!!! danger "Files on `/scratch` older than 180 days are deleted"
    `/scratch` has no backup. Move results to `/data` or off Hydra when an analysis is finished. None of Hydra's storage is meant for long-term archiving.

`quota+` on a login node shows current usage. The quotas themselves are on the [Filesystems](https://computing.si.edu/hydra/storage/filesystems/) page.

## Moving data with Globus

Globus is the best way to move large datasets. Sign in at [app.globus.org](https://app.globus.org) with an SI account and open the Hydra collection `SI_hydra_scratch`. Globus runs the transfer in the background, retries after network failures and sends an email when it finishes. For a few small files, `scp` or `rsync` from a terminal is quicker.

See [Globus at the Smithsonian](https://smithsonian.github.io/globus-docs/) and the [Data transfer](https://computing.si.edu/hydra/data-transfer/) pages of the Hydra documentation.

## Where to start in the Hydra documentation

The [Hydra documentation](https://computing.si.edu/hydra/) is searchable, and the whole site can be downloaded as a [PDF](https://computing.si.edu/hydra/hydra-documentation.pdf), which is regenerated every time the documentation changes. Good places to start:

- [Quick start](https://computing.si.edu/hydra/getting-started/quick-start/) for a first job
- [Logging in and passwords](https://computing.si.edu/hydra/getting-started/login/)
- [Storage](https://computing.si.edu/hydra/storage/) for where to keep data
- [Software](https://computing.si.edu/hydra/software/) for finding and loading programs
- [Data transfer](https://computing.si.edu/hydra/data-transfer/) for moving files on and off the cluster

## Using the PDF with Copilot

A PDF of the site can be used with Copilot to produce convenient advice. Attach the PDF to a Copilot chat and ask a question about a specific task. Because the answer draws on the attached documentation, it uses Hydra's own queues, modules and commands rather than generic HPC advice. Check commands and options against the documentation before running them.

A sample prompt:

```text
I have an analysis script that takes about 10 hours and needs 16 GB of memory.
Using the attached Hydra documentation, write a job file for it and explain each line.
```

## Who to contact

| For | Contact |
|---|---|
| Hydra account issues, such as passwords and locked accounts | [SI-HPC-Admin@si.edu](mailto:SI-HPC-Admin@si.edu) |
| Software, jobs and storage | [SI-HPC@si.edu](mailto:SI-HPC@si.edu) |
| NZCBI-specific computing questions | [stabachj@si.edu](mailto:stabachj@si.edu) |

<div style="height: 4rem"></div>
