# labtwo4201

## What's inside?

In this repo, there is this README, a R markdown notebook, and a html of the notebook's results. This README will contain instructions on how to run this notebook. The R markdown 

## Set up

Open up R Studio and make sure these two packages in the console if you do not have them

```r
install.packages("readr")
install.packages("dplyr")
```

Also, if you do not have my repo on your own device, then cloning it might be helpful. In terminal: 

```bash
git clone https://github.com/mwaricoy/labtwo4201
```

## Commands

In the R console run this command:

```r
rmarkdown::render("pubhlabtwo.Rmd")
```

This will knit my R markdown in your system and it should produce a html file.

If there's an error first time, make sure you are in the right repo folder (labtwo4201) using this code in R console and try again:

```r
setwd("~/labtwo4201")
rmarkdown::render("pubhlabtwo.Rmd")
```

To open the html you can manually knit the markdown again so it pops up automatically, or you can click the pubhlabtwo.html file in the files tab and click from the dropdown: "View in Web Browser."

This html should give you the first 20 column names of the RNA dataset, the average gene expression across the sample data set, and a histogram of average gene expression level versus average FPKM.
