# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data

I'll be using dplyr(), so the last step in preprocessing is loading the data in a data frame using tbl_df()

```r
library(dplyr)
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```r
url <- "https://d396qusza40orc.cloudfront.net/repdata%2Fdata%2Factivity.zip"
download.file(url, dest="activity.zip", mode ="wb")
unzip ("activity.zip", exdir = ".")
raw_file <- "activity.csv"
raw_tbl <- read.csv(raw_file)
raw_data <- tbl_df(raw_tbl)
```


## What is mean total number of steps taken per day?


```r
mean_steps_pr_day <- raw_data %>%
     na.omit() %>%
     group_by(date) %>%
     summarize(sum(steps))
```

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
