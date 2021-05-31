# robvis_edited
This repo contains edited rob_traffic_light function from robvis package for Quadas-2 tools. So, both main domains are included in the plot:     

a) risk of bias    
b) applicability concerns 

How to use?   
Load robvis package, then source the R file in this repo.

```Example
library(robvis)
library(tidyverse)

devtools::source_url("https://raw.githubusercontent.com/tengku-hanis/robvis_edited/main/rob_traffic_light_edited.R")

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

rob_traffic_light2(data_quadas2, tool = "QUADAS-2")
```
