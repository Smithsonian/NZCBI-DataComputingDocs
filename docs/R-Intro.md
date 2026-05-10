# Guide 2: Introduction to R

!!! tip "A Compilation of Resources"
    This guide is a compilation of material developed by various Smithsonian researchers. Many thanks to all for sharing their code and knowledge in courses being taught at the Smithsonian-Mason School of Conservation (SMSC). Also included is material from workflows developed by the National Center for Ecological Analysis and Synthesis (NCEAS) of the University of California - Santa Barbara. We encourage you to investigate the courses being taught at [SMSC](https://smconservation.gmu.edu/) and the resources available at [NCEAS](https://www.nceas.ucsb.edu/learning-hub).

## Introduction
[R](https://cran.r-project.org/) is a powerful statistical programming language that is used broadly by researchers around the world. [R](https://cran.r-project.org/) is free, open source, and platform independent. With all the libraries that are available (and those that are in rapid development), it is quickly becoming a one-stop shop for analyses in ecological statistics. Most academic statisticians now use [R](https://cran.r-project.org/), which has allowed for greater sharing of code to implement a variety of recommended methodologies. One of the very first things we ask when hiring someone is “Can you describe your [R](https://cran.r-project.org/) or statistical programming experience?” It is now critical to have this background to be competitive for scientific (and many other) positions.

Among the reasons to use [R](https://cran.r-project.org/) include:

1. Free and open source!
2. Runs on a variety of platforms including Windows, Unix and MacOS.
3. An unparalleled platform for programming new statistical methods in an easy and straightforward manner.
4. Contains advanced statistical routines not yet available in other software.
5. New add-on “packages” are being created and updated constantly.
6. State-of-the-art graphics capabilities.

[R](https://cran.r-project.org/) does have a steep learning curve that can often be intimidating to new users, particularly those without prior coding experience. While this can be very frustrating in the initial stages, learning [R](https://cran.r-project.org/) is like learning a language where proficiency requires practice and continual use of the program.

Our advice is to push yourself to use this tool in everything you do. At first, [R](https://cran.r-project.org/) will not be the easiest or quickest option. With persistence, however, you will see the benefit of [R](https://cran.r-project.org/) and continue to find new ways to use it in your work.

## Installing [R](https://cran.r-project.org/) and [R-Studio](https://posit.co/download/rstudio-desktop)

[R](https://cran.r-project.org/) is available for Linux, MacOS X, and Windows (95 or later) platforms. Software can be downloaded from one of the Comprehensive R Archive Network (CRAN) mirror sites. It’s best to choose the [R](https://cran.r-project.org/) mirror that is closest to your location. Once installed, [R](https://cran.r-project.org/) will open a console where you run code. You can also work on a script file (preferred), where you can write and (importantly) save your work. Other windows will show up on demand, such as the plot tab.

[R-Studio](https://posit.co/download/rstudio-desktop) is an enterprise-ready professional software tool that integrates with [R](https://cran.r-project.org/). This integrated development environment (IDE) has some nice features beyond the normal R interface.
![R](assets/R.png)

## [R-Studio](https://posit.co/download/rstudio-desktop) IDE

[R-Studio](https://posit.co/download/rstudio-desktop) has four separate panels to organize your workflow and project. The entire interface is customizable, including fonts and colors of the text and background (see Customizing [R-Studio](https://posit.co/download/rstudio-desktop)). The four panels are:

- Source (code) Editor (upper left)
- Console (lower left) where your code is executed
- Environment/History (upper right)
- Files/Plots/Packages/Help (lower left)

## Getting Help

One of the most useful and important commands in [R](https://cran.r-project.org/) is ?. All [R](https://cran.r-project.org/) functions should have an associated help file. At the command prompt (signified by > in your Console window), type ? followed by any command and you will be prompted with a help tab for that command (e.g., ?mean or help(mean)). Note, you can also search through the help tab directly by searching functions on the search bar.

The internet also contains a vast quantity of useful information. There are blogs, mailing lists, and various websites (e.g., https://stackoverflow.com/) dedicated to providing information about [R](https://cran.r-project.org/), its packages, and potential error messages that you may encounter (among other things). The trick is usually determining the key terms to limit your search. 

Note that it’s important to read the error messages that [R](https://cran.r-project.org/) provides. These help understand when you have typed something that the computer doesn’t understand. Google them (copy-and-paste) to figure out what they mean.
![Error](assets/Error.png "Artwork by [Allison Horst](https://allisonhorst.com/allison-horst)")

