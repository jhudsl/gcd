In the next lesson, we will discuss the basics of working with strings within the string R package. However, before we do that, working with strings becomes infinitely easier with an understanding of regular expressions. 

Strings are a sequence of characters, letters, numbers or symbols. Within R, you can create a string using by assigning a variable name to a string of text that begins and ends with quotation marks, and is assigned to a variable name. Multiple strings can be stored within vectors. So, if you have multiple strings that you want to store in a single object, you could do so by using c around the strings you want to store and commas to separate each individual string:

Regular expressions are used to describe patterns within strings. They can take a little while to get the hang of but become very helpful once you do. 

Let's create some strings and perform some basic matches with regular expressions. To visualize the matches, we are going to use the string R function STR view all. So let's install and load the string R package and then create a few strings to practice on. Our first string will be "The quick brown fox jumps over the lazy dog." and our second string will be "There are 8 planets in our solar system: Mercury, Venus, Earth, Mars, Jupiter, Saturn, Uranus, and Neptune. There used to be a 9th planet: Pluto." Before we move on, the STR view all function works by specifying the string you want to search first, and then pattern you want to look for second. Let's practice this. 

At the most basic, we can search a string for a letter or number that you specify. Let's find all of the times E shows up in our second string. In the Viewer, you should see the result of our search - all of the E's are highlighted. But you might also have noticed, the "e" in "Earth" isn't highlighted. Searches using regular expressions are case sensitive. 

Let's repeat this, but search for a number in the second sentence. Search for the number 8. 

What would happen if the number or letter you are looking for doesn't exist in the string? You can see, nothing is highlighted in our string when there are no matches.

To search for any letter in a string, regardless of whether the letter is capital or lower case, you can use alpha. 

If you specifically want upper or lower case letters, you will use upper or lower respectively. To search for digits (i.e.: numeric variable between 0 and 9) in a string, you use digit. Around each of these search terms, you will use double square brackets and colons. Let's see how these searches will match with our strings from before! Searching for all letters, we can see that numbers, punctuation, and spaces are excluded from the search. 

We can search for spaces, tabs, and newlines - collectively known as "whitespace" - either individually or as a group. For now, we'll look at how to find spaces or spaces and tabs - we'll look at newlines and the like later in this lesson when we cover special characters. If we wanted to search for spaces only, we can use space. We can search for tabs and spaces with blank. Since none of our strings have tabs in them, searching for space yields the same output as blank. 

We can also search for all punctuation, by using P U N C T. In the strings provided, we include all of the different characters that are considered punctuation. 

To identify all characters except for a newline you can use a period. Since none of our strings we are practicing on have newline characters, this will highlight all characters in our strings.

One of the benefits of regular expressions is the ability to combine them to create more complicated searches. Above, we learned how to search for a single letter - what if we wanted to search for more than one letter? If we want to search for all occurrences of a series of letters, we can combine them within square brackets. So to match all vowels in our first sentence, you would specify a, e, i, o, and u within square brackets as our search term. 

Another way we can search for more than one character at a time is by specifying a range - so if we only wanted to highlight the first half of the alphabet, we can specify to search for that range of letters: a to m. 

What if we wanted to find all the consonants? We could put all of the letters of the alphabet except a, e, i, o, and u within the square brackets, or we could specify that we want everything but the vowels. We specify "anything but" with a caret. 

But, we can see this has also highlighted punctuation and spaces, and we just want consonants. So we can expand on our matching by specifying we don't want vowels OR spaces OR punctuation. We specify or with the pipe character (by your enter key). Let's try our search for consonants again by searching for NOT vowels OR spaces OR punctuation

Anchors are a way to specify a position within a string to search. If you are interested in finding a pattern at the beginning (caret) or end (dollar sign) of a string, you can specify that using a regular expression. Be careful! The caret here doesn't mean NOT like before - if the caret is outside of the brackets, it is being used as an anchor. Let's create some new strings to practice this with. So if we wanted to search for names beginning with an M, we would use caret capital M. You can see that the M in Keisha's last name is not highlighted, since that is the beginning of a word and not the string as a whole. 

Before, we talked about how we can search for any character but a newline with a period. But what if we wanted to search for periods? The period is a special character because it has a meaning in regular expressions, so we can't just search for it like we would, for example, the letter "S". We can still search for these patterns, but we need to escape the regular expression so that we are searching for the literal character and not the special function. We do this by preceding the special character with two back slashes. So to search for a period, we would use back slash back slash period. 

Other special characters include for example: tabs, new lines, question marks, exclamation marks, and brackets. We will create a new string with some special characters in it and use it to practice searching for exclamation and question marks, and brackets. 

There are special characters we can use to specify how many times a pattern should be found within the string. To do so, you use the following: question mark for 0 or 2 times, a plus sign for one or more times and an asterisk for zero or more times. Additionally, you can specify the number of times a character must appear inside curly brackets. 

Using these definitions, we can use the plus sign to identify patterns within the names vector where M shows up one or more times in a string. 

Let's compare this to specifying we want to find the letter m one time with the number one in curly brackets. While the difference is slight in the output here, we're identifying portions of the string where m shows up exactly once. So, instead of the M M in "Mohammed" matching together, the code here splits these up, due to the fact that we're specifying the pattern match, M, exactly one time. 

If you only wanted to match strings where m showed up twice in a row, you could specify that with a two in curly brackets. 

This could similarly be achieved by specifying to search for the pattern M M one or more times with the plus sign.

In this lesson we learned about regular expressions - which are patterns of characters within strings. We learned how to search for letters and numbers, either singly or as an entire class (eg: alpha). We searched for spaces (space), whitespace (blank) and punctuation (P U N C T) as a whole. We learned how to search for multiple characters at the same time (with square brackets). We learned how to specify NOT (caret) or or (pipe) in our searches. We learned how to use anchors to specify whether to search for strings beginning (caret) or ending (dollar sign) in a specific character. Additionally, we looked at how to search for special characters, by escaping (two backslashes) the search. And finally, we looked at how to use quantifiers to specify the number of times a pattern needs to appear to be a match. 

There's still a lot of nuance to using regular expressions and they can get quite complicated looking! To help you on your way, there are two R cheatsheets about using regular expressions that you can download. This is one of them. 

This is the second that will also be useful in the next lesson on string R! 