# Guide 4: Running R-Studio from Hydra

!!! tip "For the Most Up to Date Information"
    This information provided here is adapted from a Smithsonian guide from the Office of Data and Innovation entitled ["Using the RStudio Server"](https://confluence.si.edu/spaces/HPC/pages/385975502/Using+the+RStudio+Server). Please refer to the source documentation for full instructions.
	
Hydra offers a dedicated [R Studio](https://posit.co/download/rstudio-desktop) Server for interactive running of [R](https://cran.r-project.org/)-based workflows using a familiar GUI.

Users can leverage this server to test, debug, and develop [R](https://cran.r-project.org/) based workflows using the interactive R Studio GUI (currently running R 4.5.2). By logging in with your Hydra account credentials, you will have access to the storage under /data, /scratch and /store.

## Getting Started

## Software specifications

The instance is running:

- R 4.5.2
- RStudio Server 2024.12.0+467

The version of [R](https://cran.r-project.org/) and [R Studio](https://posit.co/download/rstudio-desktop) Server is the same for all users. 

## Hardware specifications

The dedicated R Studio Server node has:

- 192 CPU cores
- 1.5 TB of memory

Be mindful that the [R Studio](https://posit.co/download/rstudio-desktop) Server is a shared resource. Please terminate idle R Sessions to free up memory for other users.

##


	
	