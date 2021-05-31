# robvis_edited
This repo contains edited rob_traffic_light function from [robvis](https://github.com/mcguinlu/robvis) package for [Quadas-2](https://www.bristol.ac.uk/population-health-sciences/projects/quadas/quadas-2/) tools. So, both main domains are included in the plot:     

a) Risk of bias    
b) Applicability concerns 

How to use?   
Load robvis package, then source the R file from this repo.

```Example
# Load packages
library(robvis)
library(tidyverse)

# Source the R file
devtools::source_url("https://raw.githubusercontent.com/tengku-hanis/robvis_edited/main/rob_traffic_light_edited.R")

# Edit quadas data from robvis
data_quadas2 <- data_quadas %>% 
  mutate(D1b = D1,
         D2b = D2, 
         D3b = D3, 
         .after = D4) %>% 
  select(1:9) %>% 
  rename(D1a = 2,
         D2a = 3,
         D3a = 4,
         D4 = 5,
         )
data_quadas2  

# Run edited function
rob_traffic_light2(data_quadas2, tool = "QUADAS-2")
```
