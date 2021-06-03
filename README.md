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
  mutate("B-D1" = D1,
         "B-D2" = D2, 
         "B-D3" = D3, 
         .after = D4) %>% 
  select(1:9) %>% 
  rename("A-D1" = 2,
         "A-D2" = 3,
         "A-D3" = 4,
         "A-D4" = 5)
data_quadas2  

# Run edited function
rob_traffic_light2(data_quadas2, tool = "QUADAS-2")
```
