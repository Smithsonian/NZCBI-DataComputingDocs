# Guide 4: Running R-Studio from Hydra

!!! tip "For the Most Up to Date Information"
    The information provided here is adapted from the Smithsonian guide on ["Using the RStudio Server"](https://confluence.si.edu/spaces/HPC/pages/385975502/Using+the+RStudio+Server). Please refer to the source documentation for full instructions.
	
Hydra offers a dedicated [R Studio](https://posit.co/download/rstudio-desktop) Server for interactive running of [R](https://cran.r-project.org/)-based workflows using a familiar GUI.

Users can leverage this server to test, debug, and develop [R](https://cran.r-project.org/) based workflows using the interactive R Studio GUI (currently running R 4.5.2). By logging in with your Hydra account credentials, you will have access to the storage under /data, /scratch and /store.

## Getting Started

The [R Studio](https://posit.co/download/rstudio-desktop) environment is accessible directly via a browser, at https://galaxy.si.edu/R4.

Just like the other components of Hydra, this server is only accessible from computers connected to Smithsonian networks (i.e., VPN, telework.si.edu, or on-site networks), not on the public internet. Instructions for remote access are provided below in [Remote Access](#remote-access).

1. Open https://galaxy.si.edu/R4 in a browser on a computer that has access to Hydra.
2. Log in with your Hydra username (all lowercase) and password.

![login Image](/docs/images/Login.png)

3. A web-based interface to a [R Studio](https://posit.co/download/rstudio-desktop) session running on the server opens. The interface is nearly identical to what you would use on your workstation.
You can install packages, runs scripts, create [R](https://cran.r-project.org/) projectsin the same way as you would on your workstation. 

4. The "Files" tab shows Hydra's storage systems. You have access to Hydra's /home, /scratch, /data, and /store directories. You can use the [R Studio](https://posit.co/download/rstudio-desktop) Server interface to transfer files or use other file transfer tools. 

![Files](/docs/images/Files.png)

6. All computations are performed on the dedicated server. If you close the browser window, your R session continues so objects in memory are preserved and computations will continue. 

## Software specifications

The instance is running:

- R 4.5.2
- RStudio Server 2024.12.0+467

The version of [R](https://cran.r-project.org/) and [R Studio](https://posit.co/download/rstudio-desktop) Server is the same for all users. 

## Hardware specifications

The dedicated R Studio Server node has:

- 192 CPU cores
- 1.5 TB of memory

Be mindful that the [R Studio](https://posit.co/download/rstudio-desktop) Server is a shared resource. Please terminate idle [R](https://cran.r-project.org/) Sessions to free up memory for other users.

## Remote access

The [R Studio](https://posit.co/download/rstudio-desktop) Server can be accessed directly from your browser if your computer has a VPN enabled to provide access to Hydra.

The Smithsonian Telework website, [https//telework.si.edu](https://telework.si.edu), can be used to access Hydra without a VPN.

1. Log into:
[https//telework.si.edu](https://telework.si.edu)

2. In the text box in the top left of the window, under the Smithsonian logo, labeled "Enter an internal resource" enter:
[https://galaxy.si.edu/R4](https://galaxy.si.edu/R4)
and then press the enter/return key.

![Remote](/docs/images/Galaxy.png)

3. The [R Studio](https://posit.co/download/rstudio-desktop) Server login page will open in the same way as if you were onsite.


	
	