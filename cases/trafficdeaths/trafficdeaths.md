---
layout: page
---

### Example: traffic fatalities

Data files:  
\* [trafficdeaths.csv](trafficdeaths.csv): Year by year state fatalities
due to traffic accidents, along with some potential predictors.  
\* [fips.csv](fips.csv): Standard FIPS numerical codes for each state.

First read in both data sources: traffic deaths and fips (state codes).
The relevant variables in the data set are:  
\* mrall: traffic deaths per 10000 residents  
\* vmiles: average miles per driver  
\* perinc: per capita personal income  
\* jaild: whether the state has mandatory jail for drunk driving

The first thing you'll want to do is merge the two data sets into a
single file:

    traffic2 = merge(trafficdeaths, fips, by.x = "state", by.y="fipsnum")

Having done this, address the following questions.  
1) Define new variables that compute a mean value for each state's
statistics (vmiles, mrall, and perinc) across all years. Remember how to
compute groupwise means in R.  
2) Make a scatter plot and fit a linear models that shows the
relationship between fatality rate (response variable) and miles per
driver (predictor).  
3) Do the same thing, except with per capita income as the predictor.  
4) Make a lattice plot that stratifies the scatter plot of fatality rate
versus miles driven by the categorical variable indicating whether the
state has mandatory jail for drunk driving. What does this plot suggest?