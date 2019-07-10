# Tidying data

So far we've discussed what tidy and untidy data are. We've (hopefully) convinced you that tidy data are the right type of data to work with. And, more than that, hopefully we've explained that data are not always the tidiest when they come to you at the start of a project. An incredibly important skill of a data scientist is to be able to take data from an untidy format and get it into a tidy format. We've started to discuss how to do this in the last lesson where we learned to reshape data. In this lesson, we'll discuss a number of other ways in which data can be tidied and the necessary tools to **tidy data** which we'll be covering in greater depth in the remaining lessons this week. 

These skills are often referred to as **data wrangling**. They are skills that allow you to wrangle data from the format they're currently in into the format you actually want them in. 

As this is an incredibly important topic, this will be the focus for the next few lessons, covering a number of packages and topics. Take your time working through them and be sure to understand all of the examples!

### dplyr

Within R, there is a package specifically designed for helping you wrangle data. This package is called [`dplyr`](https://dplyr.tidyverse.org/) and will allow you to easily accomplish many of the data wrangling tasks necessary. In the next few lessons, we will cover a number of functions that will help you wrangle data using `dplyr`, including:

* `%>%` - pipe operator for chaining a sequence of operations
* `glimpse()` - get an overview of what's included in dataset
* `filter()` - filter rows
* `select()` - select, rename, and reorder columns
* `arrange()` - reorder rows
* `mutate()` - create a new column
* `group_by()` - group variables 
* `summarize()` - summarize information within a dataset
* `left_join()` - combining data across data frames

If you have not already, you'll want to be sure this package is installed and loaded:

```r
install.packages('dplyr')
library(dplyr)
```

### tidyr

We will also return to the `tidyr` package. The same package that we used to reshape our data will be helpful when tidying data. The main functions we'll cover from `tidyr` are:

* `unite()` - combine contents of two or more columns into a single column
* `separate()` - separate contents of a column into two or more columns

If you have not already, you'll want to be sure this package is installed and loaded:

```r
install.packages('tidyr')
library(tidyr)
```

### janitor

The third package we'll include here is the `janitor` package. This package provides tools for cleaning messy data. The main functions we'll cover from janitor are:

* `clean_names()` - clean names of a data frame
* `tabyl()` - get a helpful summary of a variable

If you have not already, you'll want to be sure this package is installed and loaded:

```r
install.packages('janitor')
library(janitor)
```

### skimr

The final package we'll discuss here is the `skimr` package. This package provides a quick way to summarize a data frame. We'll discuss its most useful function:

* `skim()` - summarize a data frame

If you have not already, you'll want to be sure this package is installed and loaded:

```r
install.packages('skimr')
library(skimr)
```

These are the main packages we will be looking at for the rest of this week, but before we delve into the various ways to tidy your data, we need to cover one thing: the pipe operator. 

### The Pipe Operator

Before we get into the important functions within `dplyr`, it will be very useful to discuss what is known as the **pipe operator**. The pipe operator looks like this in R: `%>%`. Whenever you see the pipe `%>%`, think of the word "then", so if you saw the sentence "I went to the store and %>% I went back to my house," you would read this as "I went to the store and *then* I went back to my house". The pipe tells you to do one thing and *then* do another.

Generally, the pipe operator allows you to string a number of different functions together in a particular order. If you wanted to take data frame A and carry out function B on it in R, you could depict this with an arrow pointing from A to B:

A --> B

Here you are saying, "Take A and *then* feed it into function B."

In R syntax, from what you've seen so far, what is depicted by the arrow above would be carried out by calling the function B on the object A:

```r
B(A)
```

Alternatively, you could use the pipe operator (`%>%`):

```r
A %>% B
```

However, often you are not performing just one action on a data frame, but rather you are looking to carry out multiple functions. We can again depict this with an arrow diagram.

A --> B --> C --> D

Here you are saying that you want to take data frame A and carry out function B, *then* you want to take the output from that and *then* carry out function C. Subsequently you want to take the output of that and *then* carry out function D. In R syntax, we would first apply function B to data frame A, then apply function C to this output, then apply function D to this output. This results in the following syntax that is hard to read because multiple calls to functions are nested within each other:

```r
D(C(B(A)))
```

Alternatively, you could use the pipe operator. Each time you want to take the output of one function and carry out something new on that output, you will use the pipe operator:

```r
A %>% B %>% C %>% D
```

We'll be using this pipe operator *a lot*. Essentially, it takes output from the left hand side and feeds it into a function on the right hand side. You'll get a better understanding of how it works as you run the code in the next lesssons. But, when in doubt remember that the pipe operator should be read as "then".

### Summary

We have introduced the four main packages that we will spend time focusing on for tidying data. These include dplyr, tidyr, janitor, and skimr. We then spent the rest of the lesson introducing the pipe operator, an important operator used frequently in tidying data. Mastering the skills introduced in this lesson will provide you with a number of critical data science skills. So now that you are prepared for the next lessons, hop to it! 

### Additional Resources

* [dplyr](https://dplyr.tidyverse.org/), part of the [tidyverse](https://www.tidyverse.org/)
* [janitor](https://cran.r-project.org/web/packages/janitor/index.html), from [Sam Firke](http://samfirke.com/)
* dplyr tutorials by [Suzan Baert](https://suzan.rbind.io/) [Part 1](https://suzan.rbind.io/2018/01/dplyr-tutorial-1/) [Part 2](https://suzan.rbind.io/2018/02/dplyr-tutorial-2/) [Part 3](https://suzan.rbind.io/2018/02/dplyr-tutorial-3/) [Part 4](https://suzan.rbind.io/2018/04/dplyr-tutorial-4/) 
* [janitor tutorial](https://medium.com/@verajosemanuel/janitor-a-good-r-package-for-data-cleaning-f3c733632ad9) by
* [dplyr join cheatsheet](http://stat545.com/bit001_dplyr-cheatsheet.html) by [Jenny Bryan](https://www.stat.ubc.ca/~jenny/)

**Note**: a lot of the examples in the following lessons were modified from the dplyr tutorials by [Suzan Baert](https://suzan.rbind.io/). To get an even **deeper** understanding of how to tidy data using `dplyr`, take a look at all of her dplyr tutorials. 

### Slides

This lesson's slides can be found [here](https://docs.google.com/presentation/d/1RUQBMFPmuKc106p-CBcvCymkqnbffwPiTWfvHH85lvo/edit?usp=sharing)  
