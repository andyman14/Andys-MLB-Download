---
title: "Andys MLB Download"
author: "Andy Ouellette"
email: "willandy14@gmail.com"
date: "6/21/2024"
---

## *READ ME*

Information

This R script is designed to download historical MLB game scores and sportsbook closing lines and prices. The main data sources are the baseballR package and the Odds API. The script can be run with a free API key obtained from the Odds API website. If you plan to use the script more frequently, you will need to obtain a paid API license.

The script is configured to start executing from the beginning of the 2024 MLB season until the current date for all downloads. It downloads today's betting lines and prices for head-to-head (H2H), spreads, and totals. By default, it uses DraftKings and Pinnacle sportsbooks. Prices are downloaded in American format and converted to Decimal for convenience and further calculations.

The script also downloads historical prices that reflect the closing line and can be modified to download prices for specific time intervals before game time. Historical game scores return game rows with home and away team scores, winning percentages, and other game identifiers.

The sportsbook vigorish (vig) percentage is calculated for Pinnacle on H2H, spreads, and totals, and is saved into variables avg_vig_%. The final dataframe, final_combined_df_wide, should have three rows for each game: one for H2H, spreads, and totals, each with the respective line information.

The script writes the dataframes to CSV files. If you want to run this yourself, you will need to update the folder paths. See the instructions below. Basic team summary statistics are calculated at the end.
How to Execute

Select all lines of code in 00_Download_MLB_Master.R and execute them after updating the "What to update" section.
Sections

    Today's MLB lines and prices for H2H, spreads, and totals
    Historical lines and prices for H2H, spreads, and totals
    Historical game scores
    Combines #2 and #3 into a final dataframe

Dataframes of Relevance

    sportsbook_%
    historical_%
    final_%

Average Vig Values at Pinnacle (%)

    H2H: 4.16%
    Spreads: 4.27%
    Totals: 4.58%
------------------------------------------------------------------------------

### **Packages**
```{r packages}
# List of packages to check and install if necessary
packages <- c("baseballr", "dplyr", "data.table",  "httr2", "tidyverse", "lubridate",
              "jsonlite", "ggplot2", "GGally", "purrr", "tibble")

```

### **What to update**
```{r mlb-variables}
## Paste your API key here
api_key <- "INSERT API KEY HERE"
# API parameters
regions <- c('us', 'eu')  # Change if needed
books <- c('pinnacle', 'draftkings')  # Change if needed
```

```{r csv}
# All of the sections write the dataframes to files.
# Update the variables to your own folder paths or document names

# Specify folder path
folder_path <- "C:/Users/WINDOWSUSER/Documents/%"  # Update the path as needed

```
