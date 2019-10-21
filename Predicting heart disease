# Setting working directory
setwd("C:/Users/cbatra/Documents/R_heartdisease")
library(tidyverse)

# Loading files
train <- read_csv("train_values.csv")
str(train)
table(train$heart_disease_present)
head(train)

test <- read_csv("test_values.csv")

train <- select(train, -patient_id)

glimpse(train)

#building a model with train data
trainLog <- glm(heart_disease_present ~ ., data = train, family = binomial)
summary(trainLog)

#predicting on test set
predictTest <- predict(trainLog, type = "response", newdata = test)

predictTest <- as.data.frame(predictTest)
write_csv(predictTest, "predictTest.csv")

