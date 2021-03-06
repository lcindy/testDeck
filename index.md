---
title       : Developing Data Product
subtitle    : Coursera Project - Shiny Apps
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Tip Calculator

This is a simple shiny app for Developing Data Product course.  

The app is a simple calculator to calculate the tip for the meals and to split the expense among dining party.

Users can use the calculator to choose desired precentage of tip and calculate the total cost after tip, and

divide the cost among the size of the party.  

---
## Where to find it?


https://lcindy.shinyapps.io/lcindy_shiny/

---
## Inputs

1. Total: total bill  
2. % of Tip: percentage of tips you are willing to pay  
3. Number of People to Split: Number of people to split the cost  


## Outputs

1. Calculated Tip: Tips calculated based on the total and % of tip  
2. Total After Tip:  Total bill after adding the tip  
3. Per Peron: Total cost per person   

---

## Functions used in Tip calculator

```r
CalcTip <- function(TotalPmt,TipPercent) {
    TotalPmt*TipPercent/100
}
CalcTotal <- function(TotalPmt,TipPercent) {
    TotalPmt*(1+TipPercent/100)
}
CalcPerPerson <- function(TotalPmt,TipPercent,NumPPL) {
    TotalPmt*(1+TipPercent/100)/NumPPL
}
# Simple Example
c(CalcTip(100,5),CalcTotal(100,5),CalcPerPerson(100,5,3))
```

```
## [1]   5 105  35
```
