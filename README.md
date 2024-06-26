---
title: "Andys MLB Download"
author: "Andy Ouellette"
email: "willandy14@gmail.com"
date: "6/21/2024"
---

## *READ ME*

### **Information**
- This is an R script that can be used to download historical MLB game scores and sportsbooks closing lines and prices.
- The main data sources are the baseballR package and the-odds-API. 
- The script can be run with a free API key obtained through the-odds-API website. If you plan to use the script more frequently , you will have to get a paid API license. 
- The script is setup to start executing from the start of the 2024 MLB season until yesterday for all downloads. 
- The script downloads todays betting lines and prices for h2h aka moneyline, spreads and totals
- The script is using the default sportsbooks of DraftKings and Pinnacle
- The prices are downloaded as American and converted to Decimal for convenience and further calculations
- The script downloads historical prices that reflect the closing line, can be modified to download for certain time intervals before game time. 
- The historical game scores returns game rows with home and away team scores, winning percentages and other game identifiers.
- The sportsbook vigorish % is calculated for Pinnacle on h2h, spreads and totals is saved into variables avg_vig_%
- The final dataframe final_combined_df_wide should have 3 rows for each game, one for h2h spreads and totals with the respective line information.
- The script writes the dataframes to csv files, if you want to run this yourself you have to update these folder paths. See below.
- Calculates some basic team summary stats at the end


### **How to execute**
Select all of the lines of code on "00_Download_MLB_Master.R" and execute after updating "What to update". 

### **Sections**
1. Todays MLB lines and prices for h2h, spreads and totals
2. Historical lines and prices for h2h, spreads and totals
3. Historical game scores
4. Combines #2 and #3 into a final dataframe

### **Dataframes_% of relevance**
- sportsbook_%
- historical_%
- final_%

-------------------------------------------------------------------------------
### Average Vig Values at Pinnacle in %

- **H2H:** 0.04159131
- **Spreads:** 0.04273564
- **Totals:** 0.04582104
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
