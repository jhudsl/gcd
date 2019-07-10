Let's look at how we can use the string R package to look at strings in R! 

As we learned in the last lesson, a string is a sequence of characters, letters, numbers or symbols. To show the power of regular expressions, we used a single function, S T R view all from the string R package, but we didn't cover any other functions in this package or really how S T R view all even works. So, let's fix that!

string R is a package within the tidyverse specifically designed to work well with strings. All functions within this package start with S T R, as you'll see below. There are  many  helpful functions within the string R package. We'll only review the basics here, but if you're looking to accomplish something with a string and aren't sure how to approach it, the string R package is a good first place to look. There's a great cheatsheet for using the string R package that covers some of those other functions we won't cover here. If you haven't already, install and load the string R package.

As we'll only cover a few of the functions within string R in this lesson, it's important to remember that if you start typing "S T R" within R Studio, a list of the many options will show up.

When working with strings, some of the most frequent tasks you'll need to complete are to: determine the length of a string, combine strings together, subset strings and sort strings.  

Returning to our object with three strings from the last lesson, we can determine the length of each string in the vector. Here we see that the first string has a length of 26. If you were to go back and count the characters in the first string, you would see that this 26 includes each letter, space, and period in that string. The length of a string does not just count the letters in its length. The length includes every character. The second and third strings each have length 21. 

If you were interested in combining strings, you'd want to use S T R C function.

However, the output from this doesn't look quite right. You may want a space between these two words when you combine the two strings. That can be controlled with the sep argument, which indicates what character should separate the strings.

Often, it's important to subset out one part of a string. To do this, you'll want to subset the string using the S T R sub function. For example, if you wanted only the first three characters in the strings below, you would specify that within S T R sub, where you specify the strings, and the start and end positions of the characters you want to subset.

You can also use negative numbers to count from the end of the string. For example, use the provided code to return the last three positions in the string.

Finally, if you wanted to sort a string alphabetically, S T R sort can help you accomplish that. You can also sort in reverse order, by specifying decreasing equals true.

Here we will put into use some of the skills we learned from the last lesson on regular expressions. To use regular expressions with the string R package, the general format is function then string  then the pattern matching a regular expression, which you'll see used in practice here. We'll cover a number of helpful string R functions that can use regular expressions, including S T R view to View the first occurrence in a string that matches the regular expression; S T R view all to View all occurrences in a string that match the regular expression. There's S T R count  to Count the number of times a regular expression matches within a string and S T R detect to  Determine if a regular expression is found within a string. S T R subset returns a subset of strings that match the regular expression and S T R extract returns the portion of each string that matches the regular expression. Finally, S T R replace replaces the portion of the string that matches the regular expression with something else. 

To get comfortable with using regular expressions with strings, S T R view can be very helpful. The output from S T R view highlights what portion of your string match the pattern specified in your regular expression with a grey box. For example, we'll use anchors and S T R view with the names vector to identify strings that start with a capital M. In this first example we see in the Viewer Panel that S T R view has identified the names that start with the letter M.

To identify names that end with the letter "e", you would search for a lowercase e with a dollar sign for the anchor. 

Note, however, that regular expressions are case sensitive. To match patterns, you have to consider that uppercase "E" and lowercase "e" are different characters. So, S T R view does not identify any names that end with capital E  

One thing to pay attention to is that S T R view only will find the first instance of a pattern match, whereas the function we were using in the previous lesson, S T R view all, finds all matches. So if we were to search for the letter M in our names object, S T R view will only identify a single lowercase M in "Mohammed Smith" while S T R view all will identify all three. 

To count the number of matches within your strings, you would use S T R count. Below, using the names vector we've been using, we see that S T R count produces a 1 for those names that start with "M" and a 0 otherwise.

However, if we instead wanted a count of the numbers of lowercase M's, we could still use S T R count to accomplish that. Notice in the code provided that we've removed the specification to just look at the beginning of the string. Here, we're looking for lowercase m's anywhere in the string and counting them.

Instead of returning a count, at times you're just interested in knowing which strings match the pattern you're searching for. In these cases you'll want to use S T R detect. This function simply returns a true if the string matches the pattern specified and false otherwise.

To return the actual string that matches the specified pattern, rather than a true false, you'll look to S T R subset. This function pulls out those strings that match the specified pattern. For example, to obtain the subset of names whose values start with the capital letter "M", you would use  S T R subset and specify a capital M anchored to the beginning of the string. 

To extract only the portions of the string that match the specified pattern, you would use S T R extract. This function returns the pattern specified for strings where it is found and N A otherwise. For example, by searching for names that start with M, we see that the second and fourth strings in our vector return the pattern specified ("M") and that the first and third strings in the vector return N A, as they do not start with a capital "M".

The final basic function from string R that we'll discuss is S T R replace. This function identifies a regular expression and replaces each occurrence with whatever replacement the user specifies. For example, here we search for strings that start with the capital letter "M" and replace each of them with a question mark. All strings that do  not  match the regular expression are returned unchanged.

This can be a particularly useful function when cleaning data - for example, if you have a dataset that specifies the sex of people surveyed, but they are inconsistently written, you can use the S T R replace function to tidy the data and have a consistent way of denoting sex. To practice, create a vector of strings with names and their sex as shown and Note the inconsistent capitalization of the sex. Let's fix that with S T R replace as provided. With this, we have converted everyone's sex to lowercase. This also demonstrates how we can capitalize on the ability to use pipes with the string R package. 

This lesson set out to introduce you to how to work with strings within R Studio, using the string R package. We've covered how to use string R functions to calculate the length of strings, combine and subset strings, and sort them. We then looked at how we can use regular expressions with string R functions to maximize string R's abilities. We looked at how to find matches for a regular expression and count those matches. We also looked at how to detect whether a string contained a match, which strings those are, and further, how to extract that match. Finally, we looked at how to find a match to your regular expression pattern and replace it with a different pattern, which also demonstrated how we can use pipes to combine string R functions together.