# 615hw2

#This is my homework2

library(tidyverse)
child<-read.csv("~/Desktop/child.csv")
child
read.csv("~/Desktop/co2.csv")
library(tidyr)
library(dplyr)
files<-c("~/Desktop/child.csv",
         "~/Desktop/co2.csv")
tidydata<-data.frame()
for(i in 1:length(files)){
  temp<-read.csv(files[i])
  data<-c(data,temp)
}
library(knitr)
tidydata %>%
  pivot_longer(country, names_to = "years", values_to = "values")%>%
  slice_sample(n=10)%>%
  kable()
