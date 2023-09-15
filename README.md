# About 

This repo contains a demo R package, written to help the initial process of mapping domains of interest (latent concepts) used in research, onto variables found in SAIL databank. As in, if a researcher wants to access datasets within SAIL databank, how do they know which variables will be represent the concepts they care about for their research question? There is a lot of meta data already publically available on the [Health Data Research Gateway](https://web.www.healthdatagateway.org/search?search=&datasetSort=latest&tab=Datasets) and the connected [Metadata Catalogue](https://modelcatalogue.cs.ox.ac.uk/hdruk_live/). This demo package uses this meta data.

⚠️ More discussion is needed with researchers to work out how to make this package useful. It is currently just a demo and has only been tested on a limited number of metadata files. 

## Install 

Download/clone this repository to your computer.

Install required packages: `devtools`, `gridExtra`, `grid`, `insight`, `rjson`

Then in the R console run:

`library(devtools)`

`load_all("/path-to-repo/browse-SAIL/browseSAIL")`

`library(browseSAIL)`

## Example run through 
Run `?domain_mapping` in the R console to find the documentation.

Follow the example in the documentation. You don't need to provide any input data!

Remember to reference the Plots tab in R. The domains will appear in the Plot tab and give you the necessary context for the categorisations. 
## The log file output

Running the function will output a log file with your decisions. An example log file output is shown below. The name of the log file will contain the date and time stamp. The log file will contain initials of the person making the catergorisations, as well as metadata about the dataset. For each Data Element (variable) in the DataAsset/Class, the log file will contain a 'Domain_code' which labels this variable as mapping onto one or more of the domains of interest. Notice that some have been auto categorised - double check them for accuracy. More than one domain is allowed to map onto each variable. 

The idea would be that this log file could be loaded up, compared across users, and used as an input in later analysis steps when working out which variables can be used to represent which domains. 

**A** shows the log file. 

**B** shows the demo domain list that was used. 

<img width="1827" alt="logfile-example" src="https://github.com/aim-rsf/browse-SAIL/assets/50215726/8d765caf-4e6e-4cfe-aff8-fbbee90b1344">

## Contributing changes 

You can contribute changes via submitting an Issue to request a change, or create a PR with your direct changes. 

To create the .rda files in the data directory of the package:
`usethis::use_data(dataname)`

To view the package data:
`data(package='browseSAIL')`

To load the package data:
`data(dataname)`

To build the documentation files:
`library(roxygen2)`
`roxygenise()`
