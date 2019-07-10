In the first lesson we mentioned that Application Programming Interfaces (APIs) are, in the most general sense, software that allow two different web-based applications to communicate with one another over the Internet. Modern APIs conform to a number of standards. This means that many different applications are using the same approach, so a single package in R is able to take advantage of this and communicate with many different applications, as long as the application's API adheres to this generally agreed upon set of "rules". In this lesson, we'll install this package and interface with a few different APIs to cover the general concepts. 

The R package that we'll be using to acquire data and take advantage of this is called H T T R. This package name suggests that this is an "R" package for "HTTP". So, we know what R is, but what about HTTP? You've probably seeing HTTP before at the start of web addresses, e.g. in http://www.gmail.com, so you may have some intuition that HTTP has something to do with the Internet, which is absolutely correct! 

HTTP stands for Hypertext Transfer Protocol. In the broadest sense, HTTP transactions allow for messages to be sent between two points on the Internet. You, on your computer, can request something from a web page, and the protocol (HTTP) allows you to connect with that webpage's server, do something, and then return to you whatever it is you asked for. 

Working with a web API is similar to accessing a website in many ways. When you type a URL (e.g.: www.google.com) into your browser, information is sent from your computer to your browser. Your browser then interprets what you're asking for and displays the website you've requested. Web APIs work similarly. You request some information from the API and the API sends back a response.

The H T T R package will hep you carry out these types of requests within R.. Let's stop talking about it and see an actual example! HTTP is based on a number of important verbs : Get, head, patch, put, delete, and post. For the purposes of retrieving data from the Internet, you may be able to guess which verb will be the most important for our purposes! Get will allow us to fetch a resource that already exists. We'll specify a URL to tell Get where to go look for what we want. While we'll only highlight Get in this lesson, for full understanding of the many other HTTP verbs and capabilities of H T T R, refer to the additional resources provided at the end of this lesson. Get will access the API, provide the API with the necessary information to request the data we want, and retrieve some output. 

The example is based on a wonderful blogpost from Tyler Clavelle. In this example, we will take advantage of Git Hub's API, because it's accessible to anyone. Other APIs, while often freely-accessible, require credentials, called an API key. We'll talk about those later, but let's just get started using Git Hub's API now! The URL you're requesting information from is known as the API endpoint. The documentation from Git Hub's API explains what information can be obtained from their API endpoint which can be found at A P I dot Git Hub dot com. That's the base endpoint, but if you wanted to access a particular individual's Git Hub repositories, you would want to modify this base endpoint to: A P I dot Git Hub dot com slash users, slash, username, slash, repos, where you would replace username with your Git Hub username. Now that we know what our API endpoint is, we're ready to make our API request using Get. 

The goal of the provided request is to obtain information about what repositories are available in your Git Hub account. To use the example below, you'll want to change the username jane everyday doe to your Git Hub username. First you will load the H T T R and D plier packages. Then you will save your Git Hub username and the Git Hub base endpoint as variables. Using these variables and the get command you will construct your API request. Note: In the code provided, you see the function paste. This function concatenates (links together) each of the pieces within the parentheses, where each piece is separated by a comma. This provides Get with the URL we want to use as our endpoints! 

Let's first take a look at what variables are available within the api_response object. In following the provided code, while we see ten different variables within api_response, we should probably first make sure that the request to Git Hub's API was successful. 

We can do this by checking the status code of the request, where "200" means that everything worked properly. But, to be honest, we aren't really interested in just knowing the request worked. We actually want to see what information is contained on our Git Hub account. To do so we'll take advantage of H T T R's content function, which as its name suggests, extracts the contents from an API request.

You can see here that the length of repo_content in our case is 6 by looking at the object in the Environment tab. This is because the Git Hub account jane everyday doe had six repositories at the time of this API call. We can get some information about each repo by running the provided function using L apply. Doing so, we've pulled out the name and URL of each repository in Jane Doe's account; however, there is a lot more information in the repo_content object. To see how to extract more information, check out the rest of Tyler Clavelle's wonderful post.

For this next example, the data are available for download from this link: data dot fivethirtyeight dot com, but are also hosted on Git Hub at the provided link, 

and we will want to use this specific URL for this file in our Get request.

To do so, we would make the API request using get and extract the content from the API response using content. More specifically, we specify our url within Get followed by use of the helpful content function from H T T R to obtain the CSV from the api underscore response object. DF underscore steak includes the data from the CSV directly from the Git Hub API, without having to download the data first!

Not all API's are as "open" as Git Hub's. For example, if you ran the code for the first example above exactly as it was written (and didn't change the Git Hub username), you would have gotten information about the repos in jane everyday doe's Git Hub account. Because it is a fully-open API, you're able to retrieve information about not only your Git Hub account but also other users' public Git Hub activity. This makes good sense because sharing code among public repositories is an important part of Git Hub. Alternatively, while Google also has an API (or rather, many API's), they aren't quite as open. This makes good sense. There is no reason I should have access to the files on someone else's Google Drive account. Controlling whose files one can access through Google's API is an important privacy feature.  In these cases, what is known as a key is required to gain access to the API. API keys are obtained from the website's API site (e.g., for Google's APIs, you would start  at https://developers.google.com/A P I's dash explorer. Once acquired, these keys should never be shared on the Internet. There is a reason they're required, after all. So, be sure to never push a key to Git Hub or share it publicly. (If you do ever accidentally share a key on the Internet, return to the API and disable the key immediately.)

For example, to access the Twitter API, you would obtain your key and necessary tokens from Twitter's API and replace the text in the key, secret, token and token_secret arguments. This would authenticate you to use Twitter's API to acquire information about your home timeline. 


After logging in, you should see a screen like that shown. 

In the upper left of the window, there is a drop-down menu, click on this and a new window will open. 

In this window, click on "NEW PROJECT". 

Name your project and click "Create".

Once done, you should be presented with the project dashboard.

Click on "Enable APIs and Services."

In the API library search, search for "YouTube."

In the search results, Click on the "YouTube Data API v3."

Click "Enable" and from this dashboard, 

click on "Credentials"

From this webpage, you can answer the provided questions

and an API key will be generated! 

Now we are ready to make a query of the YouTube API! To do so, we are going to, yet again, use H T T R's Get function. In this example, we are going to search for videos of the Internet's favourite subject: kittens. First, save your API key as a variable. NEVER share this with anybody -- including accidentally sharing on Git Hub! Next, save the Base URL for the YouTube API as a variable. Then, save as a variable our query term, formatted as per YouTube API requirements as provided. Finally, we will Combine each of these to perform the query using Get. Now that the query has been performed, we need to Check that our request worked by examining the status code. Provided the request worked, it's time now to See what we got back using the content function. 

To just see the titles of the videos you got back, you can run the for loop provided. And there we have it, we have the 10 most recent videos featuring kittens! 

Bringing it back to a previous lesson, oftentimes, APIs will produce results in J sawn format. We can use the J sawn lite package from before to query the YouTube API using the from J sawn function as provided. 

So far, we've discussed how to work with data you've obtained from the Internet. However, things on the Internet can change. If you're not downloading the file to your system directly, you won't have a static copy saved on your system. This means that while you're saving space on your computer and not creating unnecessary copies of an identical file, the next time you go to access the file, it may not be there or it may have been updated. For these reasons, it's incredibly important to record the date of when you acquired the data. This can be recorded in your R Markdown file where you're doing your analysis, and the function Sys dot time is of great help in doing so. Regardless how you do it, a record of the date you acquired the data is incredibly important. To see the volatility of some API requests, let's just repeat our request to the YouTube API and see how the kitten video situation has changed in these last few minutes! 

If you've gone particularly quickly through this lesson and the citizens of YouTube aren't very busy, you may see that these results haven't changed (by my estimations, a kitten video is uploaded every five to ten minutes). Try waiting a few minutes and seeing if the results have changed after a bit of a wait!

In this lesson, we covered the basics of accessing APIs, mainly through using the package H T T R. We first looked at how to structure a query and access the response, using an open API: Git Hub, where you don't need a key to access information. We then practiced this by querying the FiveThirtyEight Git Hub to access a CSV file. Next, we learned about API keys and how they keep websites and their data secure. We also emphasized that you should be vigilant of your API keys and not share them, especially inadvertently by pushing them to Git Hub. We then got our very own API key to access the YouTube API and found the latest in kitten videos! Finally, by repeating our query in an ever changing API, we demonstrated the requirement that you keep track of when you accessed an API, as the data you get back from a query can change! Hopefully you feel a little more comfortable accessing APIs through R Studio - next lesson we will learn how to scrape information from the internet without an API! 