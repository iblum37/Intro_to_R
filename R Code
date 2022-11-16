# Isaac Blumhoefer, 11/15/2022
# Credit to Fusheng Yang

# R and any coding language is an instruction guide for a computer
# You write lines of code that the computer turns into formulas, etc.
# i.e. use as a calculator, write a function to perform operations, or **manipulate data

### R Basics

# R as a Simple Calculator
3 + 8
5 * -9

# Using functions for mathematical calculations
sqrt(15)
exp(3)           
D(expression(x^2 + 2*x + 1), name = 'x')
# There are a ton of functions to perform many different operations
# Don't try to memorize them all; look them up as needed

# Getting Help
?mean

# Variables
x <- 5
y = 10
x
y
w = x - y
w

z <- "Hello world"
z

a = TRUE
a



### Data Structures
# Ways to organize data in one location

# Vector - One Collection of data points
X <- c(1.2, 3.5, 9.2, 7.7, 8.1)
X
X[2] # indexing - second element
X <- c(X, 22.3) # add elements
X

Y <- c(TRUE, TRUE, FALSE, FALSE)
Y

# List - Multiple COllections of data points
empId = c(1, 2, 3, 4) # 1st attribute: employee IDs
empName = c("Debi", "Sandeep", "Subham", "Shiba") # 2nd attribute: employee names
numberOfEmp = 4 # 3rd attribute: number of employees
empList = list(empId, empName, numberOfEmp) # make a list
empList
empList[[2]] # 2nd element of the list
empList[[2]][2] # 2nd element of the 2nd element of the list

# Matrix & Array

# Dataframe
Name = c("Amiya", "Raj", "Asish")
Language = c("R", "Python", "Java")
Age = c(22, 25, 45)
df = data.frame(Name, Language, Age)
df
df[1,3] # Get the element on the first row and the third column
df[["Age"]] # Get values of the variable "Age"
df$Age



### Functions
# Write your own formulas and operations
sqrt(9) # is a function already in R

hello <- function() { # create a function with the name hello
  print("Hello World!")
}
hello()

name <- function(fname, lname) {
  paste(fname, lname)
}
name("Peter", "Griffin")

multiplier <- function(x) {
  return(5 * x)
}
my_function(5)



### Loops
# If you want to do an operation multiple times

# For Loop
for (i in 1:5) {
  print(i)
}

sum = 0
for (number in 1:10){
  sum = sum + number
}
sum

# While Loop
i=1
while(i <= 5){
  print(i)
  i = i + 1
}



### Conditions
# See if something is true or false (if/else statements)

x <- -3 
if (x < 0) {
  print("x is a negative number")
} else if (x == 0) {
  print("x is zero")
} else {
  print("x is a positive number")
}

for (i in 1:5) { # combine loop and condition
  if (i == 2) {
    print(i)
  } else {
    print("i is not 2")
  }
}




##### Onto the fun stuff....Data Manipulation

### First off, installing & loading packages
install.packages("readr")
install.packages("dplyr")
library(readr)
library(dplyr)

### Loading in a dataframe
plays <- read_csv("plays.csv")

### Checking out the Data
View(plays)
head(plays)   # first 5
tail(plays)   # last 5
table(plays$yardsToGo)
summary(plays$yardsToGo)

### Manipulating the Data
select(plays, quarter, yardsToGo)   # selects the columns you want to keep
filter(plays, possessionTeam == 'MIN')    # selects the rows you want to keep
plays %>%   # "pipe operator" -> allows multiple function calls in a row by putting previous dataframe in first parameter
  mutate(yardsToFirstDown = playResult - yardsToGo) %>%   # can edit existing columns or add new columns
  mutate(first_down = yardsToFirstDown > 0) %>%
  View()

arrange(plays, yardsToGo)   # changes ordering of dataframe based on selected column
summarize(plays, mean = mean(yardsToGo))    # obtain summary statistics
plays %>%
  group_by(possessionTeam) %>%    # groups likewise data together to be manipulated as a group
  summarize(mean = mean(yardsToGo)) %>%
  arrange(desc(mean))

