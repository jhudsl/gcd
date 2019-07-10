# Summarizing data

Throughout data cleaning and analysis, it will be important to summarize information in your dataset. This may be for a formal report or for checking the results of a data tidying operation.

### Grouping Data

Before we get into how to summarize data, first we need to look at how to group data. Often, data scientists will want to summarize information in their dataset. While you may want to know how many people are in a dataset, more often, you'll want to know how many people there are within a group in your dataset. For example, you may want to know how many males and how many females there are. To do this, grouping your data is necessary. Rather than looking at the total number of individuals, to accomplish this, you first have to **group the data** by the sex of the individuals. Then, you count within those groups. Grouping by variables within `dplyr` is straightforward.

#### `group_by()`

There is an incredibly helpful function within `dplyr` called `group_by()`. `group_by()` groups a dataset by one or more variables. On its own, it does not appear to change the dataset very much. The difference between the two outputs below is subtle:

```r
msleep

msleep %>%
  group_by(order)
```

![**msleep before and after the `group_by()` command**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-02.png)

In fact, the only aspect of the output that is different is that the number of orders is now printed on your screen. However, in the next section, you'll see that the output from any further functions you carry out at this point will differ between the two datasets.

### Summarizing data 

Now that we know how to group data, we can start looking at the different ways to summarize your data. 

#### `summarize()`

If you wanted to figure out in total how many samples are present in your dataset, you could use the `summarize()` function. 
```r
msleep %>%
  summarize(N=n())
```

This provides a summary of the data with the new column name we specified above (`N`) and the number of samples in the dataset. Note that we could also obtain the same information by directly obtaining the number of rows in the data frame with `nrow(msleep)`.

![**Summarize with `n()`**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-03.png)

However, if you wanted to count how many of each different `order` of mammal you had. You would first `group_by(order)` and then use `summarize()`. This will summarize within group.

```r
msleep %>%
  group_by(order) %>% 
  summarize(N=n())
```

The output from this, like above, includes the column name we specified in summarize (`N`). However, it includes the number of samples in the `group_by` variable we specified (`order`).

![**`group_by()` and `summarize()` with `n()`**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-04.png)

There are other ways in which the data can be summarized using `summarize()`. In addition to using `n()` to count the number of samples within a group, you can also summarize using other helpful functions within R, such as `mean()`, `median()`, `min()`, and `max()`. 

For example, if we wanted to calculate the average (mean) total sleep each order of mammal had, we could use the following syntax:

```r
msleep %>%
  group_by(order) %>% 
  summarize(N=n(), mean_sleep=mean(sleep_total))
```

![**`summarize()` using `mean()`**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-05.png)

#### `tabyl()`

In addition to using `summarize()` from `dplyr`, the `tabyl()` function from the `janitor` package can be incredibly helpful for summarizing categorical variables quickly and discerning the output at a glance. If we wanted to get a summary of how many samples are in each order category and what percent of the data fall into each category we could call `tabyl()` on that variable. For example, if we use the following syntax, we easily get a quick snapshot of this variable. 

```r
msleep %>%
  tabyl(order)
```

![**Summarizing data using `tabyl()` from the `janitor` package**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-06.png)

#### `summary()`

Note, that `tabyl()` assumes categorical variables, like in the `order` variable. If you want to summarize numeric variables, like those found in the `sleep_total` column, the base R function, `summary()`, works well. For example, this code will summarize the values in `msleep$total_sleep` for you. 

```r
summary(msleep$sleep_total)
```

![**`summary()` is appropriate for numeric variables while `tabyl()` still treats them as categorical!**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-07.png)

#### `skim()`

When you would rather get a snapshot of the entire dataset, rather than just one variable, the `skim()` function from the `skimr` package can be very helpful. The output from `skim()` breaks the data up by variable type. For example, the `msleep` data set is broken up into `character` and `numeric` variable types. The data are then summarized in a meaningful way for each. This function provides a lot of information about the entire data set. So, when you want a summarize a dataset and quickly get a sense of your data, `skim()` is a great option!

```r
skim(msleep)
```

![**You can summarize an entire dataset using `skim()` from the `skimr` package**](resources/images/18_GCD_Summarizing/18_GCD_Summarizing-08.png)

### Summary 

In this lesson, we looked at the `group_by()` function and how it can be piped into the `summarize()` function, which can be used to *summarize* your data. We then looked at how you can summarize your data with the `tabyl()` function, which counts the number of times each value of a categorical variable appears. This is compared to the `summary()` function, which is used for numerical values. And finally, we looked at the `skim()` function which will summarize both categorical *and* numerical values for you! 

### Slides

This lesson's slides can be found [here](https://docs.google.com/presentation/d/1FOjlUAtwhHaYrohZ0ldSxm2euaI6U11Ae84Qs4Ivg4w/edit?usp=sharing)  
