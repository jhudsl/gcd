Throughout data cleaning and analysis, it will be important to summarize information in your dataset. This may be for a formal report or for checking the results of a data tidying operation. Before we get into how to summarize data, first we need to look at how to group data. Often, data scientists will want to summarize information in their dataset. While you may want to know how many people are in a dataset, more often, you'll want to know how many people there are within a group in your dataset. For example, you may want to know how many males and how many females there are. 

To do this, grouping your data is necessary. Rather than looking at the total number of individuals, to accomplish this, you first have to group the data by the sex of the individuals. Then, you count within those groups. Grouping by variables within D plier is straightforward. There is an incredibly helpful function within D plier called group by. group by groups a dataset by one or more variables. On its own, it does not appear to change the dataset very much. The difference between the outputs of M sleep alone versus M sleep grouped by order is subtle. In fact, the only aspect of the output that is different is that the number of orders is now printed on your screen. However, in the next section, you'll see that the output from any further functions you carry out at this point will differ between the two datasets.

Now that we know how to group data, we can start looking at the different ways to summarize your data. If you wanted to figure out in total how many samples are present in your dataset, you could use the summarize function. This provides a summary of the data with the new column name we specified above (N) and the number of samples in the dataset. Note that we could also obtain the same information by directly obtaining the number of rows in the data frame with N row M sleep.

However, if you wanted to count how many of each different order of mammal you had. You would first group by order and then use summarize. This will summarize within group. The output from this, like before, includes the column name we specified in summarize (N). However, it includes the number of samples in the group by variable we specified (order).

There are other ways in which the data can be summarized using summarize. In addition to using N to count the number of samples within a group, you can also summarize using other helpful functions within R, such as mean, median, min, and max. For example, if we wanted to calculate the average (mean) total sleep each order of mammal had, we could use M sleep piped to the group by function on the basis of order, which in turn is piped to the summarize function, which summarizes the number of observations but also calculates the mean of the sleep total column. 

In addition to using summarize from D plier, the table function from the janitor package can be incredibly helpful for summarizing categorical variables quickly and discerning the output at a glance. If we wanted to get a summary of how many samples are in each order category and what percent of the data fall into each category, we could call table on that variable. For example, if we apply the table function to the order column, we easily get a quick snapshot of this variable. 

Note, that table assumes categorical variables, like in the order variable. If you want to summarize numeric variables, like those found in the sleep_total column, the base R function, summary, works well. For example, using summary with M sleep dollar sign total underscore sleep inside will summarize the values therein for you. 

When you would rather get a snapshot of the entire dataset, rather than just one variable, the skim function from the skim R package can be very helpful. The output from skim breaks the data up by variable type. For example, the M sleep data set is broken up into character and numeric variable types. The data are then summarized in a meaningful way for each. This function provides a lot of information about the entire data set. So, when you want a summarize a dataset and quickly get a sense of your data, skim is a great option!

In this lesson, we looked at the group by function and how it can be piped into the summarize function, which can be used to summarize your data. We then looked at how you can summarize your data with the table function, which counts the number of times each value of a categorical variable appears. This is compared to the summary function, which is used for numerical values. And finally, we looked at the skim function which will summarize both categorical and numerical values for you!