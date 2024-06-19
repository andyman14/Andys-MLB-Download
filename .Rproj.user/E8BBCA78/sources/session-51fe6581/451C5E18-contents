
## Clear R Workspace & Console
rm(list=ls(all=TRUE))
cat("\014")


#------------------Run this block of code--------------------------------------

# Function to check and install packages
check_and_install <- function(package){
    if (!require(package, character.only = TRUE)) {
        install.packages(package)
        library(package, character.only = TRUE)
    }
}

# List of packages to check and install if necessary
packages <- c("baseballr", "dplyr", "data.table",  "httr2", "tidyverse", "lubridate",
              "jsonlite", "ggplot2", "GGally", "purrr", "tibble")

# Apply the function to each package
lapply(packages, check_and_install)

## Paste your API key here
api_key <- "e0d0cebccd1f3b630b762f64b521867d"

#------------------------------------------------------------------------------


#############################################
# Start downloading live and historical MLB game scores, lines and prices
source("01_Download_MLB_OddsandScores.R")

