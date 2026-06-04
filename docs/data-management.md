## Overview

Ecological research produces heterogeneous data including field observations, sensor outputs, genomic sequencing data, imagery, and spatial data. Effective data management ensures integrity, accessibility, and reusability across the project lifecycle. While each project and data type will have specific needs, below are general data management strategies that can and should be applied across any data project.

!!! tip "When is data management best done?"
    Data management is best done throughout the ENTIRE life cycle of a project! Don't wait until the end of the project to start managing your data! Data management is an ongoing process that should be a part of project planning from the very beginning!

## Primary infrastructure

Currently, the Smithsonian-wide supported locations to have and store data are:

* **Hydra** is the [Smithsonian's high-performance computing](https://confluence.si.edu/spaces/HPC/pages/163152211/High+Performance+Computing) (HPC) cluster, which is where most large-scale analyses are conducted and data stored from the data generation, analysis, through publication stages. Large datasets such as genomic sequencing, large-scale modeling, or bioacoustic data etc. are stored and analyzed on hydra.

* **OneDrive** is a cloud-based file storage service through Microsoft that each Smithsonian email gets access to. Many researchers use OneDrive to back up their workstation computer or share files with collaborators.

* **DataONE** hosts the [Smithsonian Research Data Repository](https://smithsonian.dataone.org/), an online research data repository to facilitate open and discoverable reuse of Smithsonian research data products. The Smithsonian Tropical Research Institute (STRI) is the primary current user of the Smithsonian Research Data Repository, see the [Smithsonian Tropical Data Portal](https://smithsonian.dataone.org/portals/tropical) to explore STRI data.

!!! note "External hard drives are NOT primary infrastructure"
    While external hard drives are often used for backing up data, they are not a safe long-term data storing option. Hard drives can be easily broken, stolen, or misplaced and must be replaced at least every 5 years to mitigate sudden catastrophic hard drive failure. While there can be specific circumstances where hard drives must be used to store Smithsonian research data for _short_ periods of time, research projects should plan carefully before conducting a study to ensure data is **never** a lone copy on a single hard drive, as this can lead to data loss.

## Data Organization

Organized data allows for quickly finding what you need, sorting it, and having easy interpretability for use in analyses and sharing with collaborators!

### Naming Conventions

When organizing your data, it is best to use systematic naming for your files, directories, sample names etc. You want the names to be consistent, but unique, and to have some inherent logic to them. Importantly, avoid using special characters and spaces in your names.

!!! note "Delimiters"
    For sortability, use a consistent delimiter between the various parts of your names. A delimiter is a character or sequence of characters that specify the boundary between data. The most common delimiter we see in everyday life is the space between each word in a sentence. However, while spaces are great to denote each word in regular text, spaces should NOT be used in programming or naming data, files or directories. For example, when working in the command line (like on hydra), spaces are usually interpreted as separators for different arguments in a command. For example, if you wanted to change directories using the `cd` command to a directory named `my directory` containing a space, `cd my directory` will be interpreted as "go to the directory `my`" and then `directory` will be leftover as an invalid separate argument. To get around this, paths containing spaces will often be surrounded by quotes (e.g. `"my directory"`) or the space would need to be "escaped" using a backslash (e.g. `my\ directory`). This is tedious and can easily lead to errors when trying to correctly escape all the spaces. It is best to never use spaces while naming any files, directories, or sample names. We recommend using an underscore as your go-to delimiter for directories, files, and sample names! This is commonly referred to as "snake case" (i.e. `snake_case`).

For quickly sorting and identifying project directories and files, consider incorporating the following elements:

* **Project name/acronym** - Select a project name or acronym that you use for all files or as the main directory for your project.

* **Experiment** - If your project has multiple types of experiments or types of instruments used, you can incorporate an experiment ID or instrument used to generate the data within a directory.

* **Site/Location** - Commonly used for field data when taken at multiple sites. Using a site abbreviation or code that is of consistent length aids in sortability. If your sites have an inherent order (e.g. transect data across a province), consider assigning numbers to your sites to add the natural context of which site is next to the other in your transect.

* **Researcher Initials** - Helpful for designating who took the data, whether from the field or in the lab, and facilitates whom to contact about the generation of the data. Keep the number of initials consistent, if possible, to always use 2 or 3.

* **Date** - The date the data was collected. Since dates can be notated multiple ways, make sure you select and stick to the same data format throughout a project (e.g. YYYYMMDD, YYYY-MM-DD, or YYYY_MM_DD). Also note that formatting dates as numeric YEAR, MONTH, DAY (e.g. 20260301 for March 1st, 2026) facilitates natural sortability on a computer, rather than using string abbreviation (e.g. Mar for March) which will often default to ordering by alphabetical order.

Sample names should similarly be unique, informative, and sortable. Again, make sure to not use any special characters or spaces in your sample names. For example, you could have a sample name like GRSP_MD_344_2009 which is a 4 part sample name: GRSP is the species (this is the 4-letter code for Grasshopper Sparrow), MD is a two letter location code for where the sample is from (in this case MD is the 2-letter state code for Maryland), 344 is the unique individual identifier number (this was bird # 344 from its respective project; however, this could be replaced with a unique USFWS band number as well which is often used for birds), and lastly 2009 is the year the sample was taken (we recommend always using the 4 numeral year instead of only 2 for easier shorting in downstream applications).

Whatever you choose for your sample names, make sure they are unique and consistent. Also make sure to add a key on how to read your sample names to your project README (more on READMEs below!) similar to our example in this section. Some researchers prefer using much shorter names for their samples (like GRSP3), which is acceptable as long as you have a key to link that shorthand sample name to the rest of that sample's metadata. In the long-form example, there are more integrated pieces of information in the sample name that can never be "lost" since it is part of the name (What: Grasshopper Sparrow, Where: Maryland, Who: Individual 344, When: 2009). This can make sorting the data easier and more straightforward to parse. Whatever you choose, document it in a file kept with your data in your project directory.

### Recommended Directory and File Structure

Any given research project will generate many files (and some will generate thousands of files!). As such, you don't want to dump all your project files into a single directory, but instead logically organize your file system so that you can easily find whichever project or data file you are looking for.

For example, you may need to check one of your previous analyses after getting reviewer comments on a manuscript; however, your project directory on hydra looks like the following:

```
my_project_directory/
├── analysis1.job
├── analysis1.log
├── final_final_results.txt
├── final_results.txt
├── final_results2.txt
├── processeddata1.txt
├── processeddata2.txt
├── processeddata3.txt
├── rawdata1.fq
├── rawdata2.fq
├── rawdata3.fq
├── sample_list.tsv
├── test1.log
├── test1.tsv
├── test2.log
├── test2.tsv
...
```

It may be difficult to find the exact file or analysis you want. While this toy example is much smaller and still easy to scan through by eye, if a directory has over 4,000 files all in the same directory with little or no structure, it can be very difficult to find the data files you need quickly. Further, you risk files being lost or labeled in a way that they are no longer usable (e.g. you have 3 files all labeled "final" and now the actual final dataset appearing in your manuscript is no longer clear-cut).

While the exact file structure that will work best for each project will differ slightly, the following is a suggested simplified structure:

```
my_project_directory/
├── data/
│   ├── raw_data/           # raw, unmodified data
│   ├── processed_data/     # intermediate, processed data before final biologial analyses
│   └── results/            # outputs from your analyses
│       ├── analysis1/      # Keep each analysis in a separate directory
│       └── analysis2/
├── jobs/                   # .job submission scripts
├── logs/                   # log files from completed jobs
└── metadata/               # project information, master sample lists, documentation etc.
```

## Metadata and Documentation

!!! tip "The Bus Test"
    You want to make sure the data in your lab/organization can pass "the bus test." This means that, if the lead researcher for a given project is hit by a bus _right now_, would that data be documented well enough for someone else in the research team to pick up where that unfortunate researcher left off?

Describing your data and the associated context in which it was collected is "metadata" or "data about data". Your project metadata must include all relevant information required to keep the dataset viable and reusable long into the future. Keep in mind what information another researcher might need to pick up the data where you left off (aka. the bus test), or reproduce the study in the future. You will need both domain specific metadata (such as the specific instrument used to run an experiment or camera equipment research photos were taken on) but also general information such as who generated the data, who is the contact person maintaining the data, and extremely importantly, the meanings of all codes/abbreviations used in the data, units of measurement, versions of software packages used, etc. You will notice that most of this information is required for methods sections in publications anyway; however, many authors wait until the project is essentially done to document these details. Some projects encounter catastrophic accidents or just don't get to the publication stage for a variety of reasons, and therefore, the generated dataset can become unusable if documentation was left until the last minute and never completed. Documenting project data from the start of a project will not only prevent data from being orphaned and unusable, but will also aid in drafting method sections for future publications!

!!! note "Some NZCBI specific metadata examples"
    If you have shorthand field or lab IDs for a sample, you will need to document a key associating each name for a given sample to the rest of its data and/or other sample names. If you have data from an animal from a Zoo's living collection, document that animal's name and/or studbook ID. Similarly, if you have a genetic sample from a museum specimen, make sure to also document what the museum identification number is and which museum it is from. It is also important to document which permits were used for the import/export of a project's samples and what funds paid for the project, as if this information is dissociated from a dataset it can cause legal problems in the future if the data is reused in a way that wasn't agreed upon by all permitting and funding groups.

### README

A README is a text file that describes other files in a project or directory that has been typically used in software development and distribution. The README file contains information about the other files in a project directory or serves as and archive for computer software and is a form of documentation. README files are plain text files and are often saved as README, README.txt, or README.md. The .md file extension indicates that README, while still a plain text document, was written with Markdown formatting for easy HTML and/or PDF conversions of your README file. GNU coding standards encourage the use of README files as a "general overview" of a software package.

A helpful strategy for documenting project metadata as you go about a research project is to keep a README file in your main project directory where you are storing and/or analyzing your data. We would recommend keeping a main project README with all the pertinent project documentation, but subdirectories can also have their own READMEs to help document what is in a particular directory.

The following are some examples and explanations on what to include in your project README:

* **Project**: Project name - Keep your project name consistent so it is searchable and discoverable.

* **Publication status** - Published or unpublished data.

* **Project Description** - 2-3 sentence description of the project. Include what (e.g. taxa), where (e.g. location of sampling), how (e.g. protocol/type of sequencing etc.), and goal of project (e.g. to assess genetic diversity, effect of bottlenecks, inbreeding, translocations etc.).

* **People** - Names and contact information of person who generated data, the PI overseeing project, any other relevant people who may need to be contacted about data. Make sure to also include non-SI emails for visiting or short-term scholars who will not have access to their SI email indefinitely!

* **Dates** - Put relevant years for your project: e.g. year samples were collected, years samples were sequenced, etc.

* **Associated Documents** -If there are any associated documents for your dataset, put them here. Citations to published works are best, if possible. Note if the dataset was used in a dissertation or a preprint or manuscript draft and who to contact about those unpublished or not publically available documents.

* **Funding** - The original funding source could easily be forgotten as data ages, and thus will be lost for future publications. Note the funding sources for the sampling, sequencing, and/or materials here.

* **Permits** -Especially for unpublished data, any IACUC or ACUC permit numbers or collecting permits associated with the sampling/dataset should be listed here so they are not dissociated from the sequencing data.

* **Data Description** - Describe the actual data, how it was generated and where it is located. Put the path to exactly where the data is living on hydra, for example, or which person has the data in their OneDrive. Make sure to denote raw data and relevant processed or filtered data files, if applicable. Note how many files are expected, and what types of files they are (are they raw sequencing files in fastq format? Are they audio files in .wav format?)

* **Location of Further Metadata** - list where comprehensive sample lists are etc.

* **Data Generation** - Put information such as what species the samples are, if the samples are derived from blood, fecal, buccal swabs etc. Specify if there were museum specimens used, and where and when they are from (which museum? From what years?) If DNA was collected from another, published project, notate that here. Ideally put summary of sample sizes here (e.g. what were the total number of individuals sequenced? Number per site? Number of ancient versus modern samples?). Instruments, machines, cameras used to generate the data, sequencing facilities that performed sequencing etc.

* **Processed Data** - Put the location and describe the file types of important processed data files such as genome alignment (BAM) files, genotyped and filtered VCF/BCF files, pruned and processed camera track photos etc. This will vary dramatically between projects so add processed files as deemed fit per project. Put the software used to generate the files and always put the software version!.

* **Associated databases and repositories** - If there are databases or repositories associated with the dataset, add links/DOIS. For example: GitHub repositories, Genbank accession numbers, Figshare, Dryad etc.

Be sure to note anything in your README that you feel should stay associated with your dataset. More or less subsections than described above will suit a specific project, these are a starting guideline. At the very least the basic "who, what, when, where, and why" of a project should be included in a simple project README and kept with your data. However, the more metadata you can keep with your dataset the better! Data management is best done AS YOU GO so fill in your README during your project, and ideally before you move on to your next one!

## Backup strategy

The general rule for backing up data is to have at least 3 copies of your data. In addition, these triplicate copies should be housed in separate systems. For example, if you have 3 copies of your raw data all on your workstation computer, but a power outage fries your computer, then all your data copies will be lost! Ensure that you have three copies of your raw data that are not in the same physical OR virtual system. For example, there could be one copy of a project's raw data on hydra in network attached storage, one copy on the lead researcher's workstation computer, and one copy in the PI's OneDrive folder. This ensures that if something happened to one or even two copies of the data, a third copy can still be easily accessed.

!!! note "Separate your working copy from your backup"
    Always keep an entirely untouched copy of your raw data that you absolutely do not alter in any way. Only manipulate (analyze, sort, refine etc) a _copy_ of your raw data. Keep the copy of your untouched raw data in a **different** directory than where you are performing computations and analyses. This will prevent you from accidentally altering, overwriting, or deleting your raw data. If all else fails, you always want to be able to go back to your original raw data. Analyses can be rerun, but one-of-a-kind research data cannot necessarily be easily recovered!

## Public Data Repositories

Depending on the type of data you are generating, there are numerous publically available repositories to host your data. For example, for genomic sequencing data most journals/funding bodies require that sequencing data be made publically available. The National Center for Biotechnology Information [(NCBI)](https://www.ncbi.nlm.nih.gov/) hosts biomedical and genomic information for public access. Sequence Read Archive (SRA) and GenBank are the NCBI databases that host the sequencing data. Another example of an ecological data repository, is [Movebank](https://datarepository.movebank.org/home) for movement data.

There are also non-specialized public repositories such as [Figshare](https://confluence.si.edu/spaces/FFI/pages/72879403/Figshare+for+Institutions) or [Dryad](https://datadryad.org/) which will generate a Digital Object Identifier (DOI) for your dataset, which can be used in citations. While many researchers wait to upload their data to a public repository until required for publication, uploading your raw data as soon as possible (if you are able) creates an additional safe copy of your data in case of catastrophic accidents (and can count as the third copy of your data!).

Whichever repository you choose, having your data publically available will help your data conform to the [FAIR](https://force11.org/info/the-fair-data-principles/) data principles (i.e. Findable, Accessible, Interoperable, and Reusable), a goal for all researchers at NZCBI!

## Additional Information

For more information on data management at the Smithsonian or help to develop a data management plan, please see: <https://library.si.edu/research/manage-research-data>
