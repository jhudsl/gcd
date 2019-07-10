# How to update a Coursera course 

### Outline the course lessons 

First step in creating the course is to work with Jeff and to review the old version of the course, to create an outline for what each of the weeks should look like. 

I like to sign up for the old version of the course myself and go to the forums to look at what questions people are asking, what guides the forum moderators are linking and then also look at the reviews for the course and see where the major complaints lie. I then incorporate these comments into the outline. 

### Finding course content 

This is where the bulk of the work lies; for each proposed lesson from the outline, you need to flesh it out with all of the relevant topics and if appropriate, which packages and functions you will need to cover. Finding other people's guides and tutorials is very useful. Note what is in common and use your own experiences to guide what you think is important. I usually create a Word document for each lesson and sketch out the lesson's content and link all of the resources I have found during my research. I try and think of an exercise to do at the end of the lesson to bring together a few of the different functions that we have learnt and briefly outline it here.

### Organizing your repo 

Before you get started, create a new GitHub repository for this course update. In it, create four folders: 

1) manuscript 
2) scripts
3) videos 
4) HTML 

Within the manuscript directory, create a folder called `resources` and within that, create a folder called `images`. For each lesson you create, you will generate a directory within `images` with the lesson number, course name, and lesson title. The images of the slides for that lesson will go in these folders.

In the manuscript folder will go the .md's for the written lesson. The scripts folder holds the script for generating the video. The compiled video will go in the videos folder. And finally, Coursera prefers the lessons be compiled as HTMLs, so once everything is complete, reknit all of the lessons as HTMLs and you will place them here. 

### Creating the lesson 

Each lesson has three components: 
1) A blogpost style, written lesson 
2) Slides to go along with this
3) A video that brings together the slides and the written content 

#### 1) The lesson 

Each lesson follows the same structure, into a new markdown file, paste the following: 

```

# Title

### Content

### Summary 

### Additional resources [optional]

### Slides and Video

This lesson's slides can be found [here]()  
The lesson's video can be found [here]()  

### Quiz 

{quiz, id: quiz#}  

? 
  
{/quiz}

```

##### The title and preamble

As you can see, the title is always a top level header, while each subsequent heading is preceded by `###`. If within a section, it further needs to be broken up, `####` and `#####` are used to create the subsections. 

Following the title and before the first subsection, there is a paragraph the explains the goals for the lesson, what operations we will be learning, and introduces a bit about why this topic matters in the context of data science.

##### The content

Next comes the first subsection which starts the actual content of the lesson. This is where having the fully fleshed out outline is helpful. 

##### The summary 

Every lesson ends with a paragraph summarizing everything learned in the lesson and when it might need to be applied. If any content links to future lessons, discussing how the topic will be useful in the future is a good idea.

##### The additional resources section 

Here is where you can link any of the resources you found while you were researching the topic that you found particularly helpful or are at a more advanced level than what you covered in the lesson, for if a learner wants to delve more deeply into the topic. Not all lesson's will have a section like this; if there is only one or two links that you found particularly useful, you can either link them here or you could put them in links in the bulk of the lesson, or I have found that preamble paragraph to be a particularly good spot. 

##### Linking 

To link to another website, format your references like so: 

```
[Text to display](Link)
```

There is some problem that Ira is still working out with the links not opening in new windows once it has been uploaded to Coursera. Adding {target ="_blank"} after each link **does not** fix the problem and in fact exacerbates it. Figuring this out is still ongoing. 

##### The quiz 

Each quiz is formatted to [Leanpub specifications](https://leanpub.com/markua/read#leanpub-auto-quizzes-and-exercises). So each starts with `{quiz, id: quiz#}` where you replace the hashmark with the lesson number. 

Each question is formatted like so: 

```
? To convert JSON data to a data frame, which function would you use?

C) `fromJSON()`
m) `toJSON()`
o) `jsonlite()`
o) `JSONlite()`
o) `GET()`
o) `POST()`

```

Each new question is preceded by a question mark. The correct option is listed first and is denoted with a capital C. Wrong options are denoted with a lowercase o. If you would like to specify a mandatory wrong option, it is preceded with a lowercase m. 

These questions will be reformatted to Coursera specifications, but this format is easily understood and transcribed to that format. 

#### 2) The slides 

Slides are created in Google Slides. Each slide desk is formatted like [seen here](https://docs.google.com/presentation/d/1xiRHJDSAItgZ6QB8FyStBi97PLXDqIiMZ2axET3LgZk/edit?usp=sharing). Each slide deck starts with a title slide indicating the lesson name and the course that it belongs to. This is followed by content slides, in which there is a textbox running along the bottom for links and references, where relevant. And finally, each slide deck ends with a summary slide that just reiterates the title of the lesson again.

##### Stock images 

Each part of the written lesson will need to have an accompanying slide and for some lessons that are more abstract in their topics (eg: Ethics of DS), there aren't code snippets or plots that you can show to go with the text. In these cases, we can turn to stock images to highlight the concept. I've used [Freepik](https://www.freepik.com) and [Unsplash](https://unsplash.com/) - on each slide using images from these sites, you must credit the original author (make sure the author name is appropriate!) in the bottom text box of the slide. 

##### Code snippets 

To display code and its output, I have a separate R project open where I will perform all of the R code with the display settings set such that the text is zoomed in sufficiently large to take screenshots for the slides. I will screenshot the code from the Source panel and the output from either the Console or Plots panel.

##### Format of the slides 

If there is text on the slides, it is in Roboto Condensed font and if it, or a box or arrow, is being used to highlight something, we use the bright pink colour (magenta) that is at the far right end of the top row on the colour palettes, in deference to colourblindness. If using an arrow or a box, try and use line width 3, where possible. 

##### Creating the slides as you go

As you are writing the blogpost style lesson, you will be generating code and output as you go and you will want to incorporate some of those as images included in the written lesson. As such, it is often easiest to have the Google Slides open while you are writing the lesson, so that you can copy and paste things onto the slides as you go, and write the intext reference to that slide number as you create them. This can be troublesome if you go back and change the slide order after the fact, in which case all of your intext slide references will be wrong - so it bears some planning ahead. 

##### When you are done 

At the end of the lesson, when you are happy with your slides, you will go to File > Share > Get shareable link, and confirm that the setting is set to "Anyone with the link **can view**". Copy and paste this link into the appropriate section of the written lesson. 

Next, go to File > Download as > PDF. Move this PDF to the appropriate folder in the /manuscript/resources/images directory. Open up terminal and navigate to that same directory. In terminal, use the pdftoppm command to create a PNG for each slide in the PDF, like so: `pdftoppm -png *.pdf ##_[Course title]_[Lesson title]`. For example, in the Getting and Cleaning Data course ("GCD"), lesson 18, named Summarizing, this was the command used to conver the PDF to the PNGs:

```
pdftoppm -png *.pdf 18_GCD_Summarizing
```

In doing so, each image will be titled like `18_GCD_Summarizing-01.png` for the first slide, as an example. This file name is what you will reference in text to embed the images in your written lesson. 

**Embedding images in the lesson**

Using markup, you can reference the slides that you downloaded like so: 

```
![**Caption for figure, bolded**](resources/images/##_Course_Title/##_Course_Title-##.png)

```

#### 3) The video 

Each video requires two parts: the slides, downloaded as PNGs, and a script. You should already have downloaded the slides, so we'll focus on making the script. We will use the R package `ari` (For full explanation see [GitHub](https://github.com/seankross/ari) to compile the video. 

##### The script

The script is essentially word-for-word the contents of the lesson. For each slide in your slide deck, you need a single paragraph in your script. For example, if you have 18 slides, your script will contain 18 paragraphs. 

Into a new MD file, copy and paste the contents of the lesson. We need to format it such that the Ari package (and really the Amazon Polly) can interpret the text and read it properly. 

This means you will need to remove all headers, links, markdown formatting, code snippets, the quiz, additional resources, etc. Anything that shouldn't or can't be said by Amazon Polly. To quickly do this, first, I search for `*`, ```r, ```, and () and replace these with nothing. Next, I find where all the code snippets used to be and convert them to plain text instructions. This can be challenging and often ends up sounding more like instructions or reiterating the comments and less so the actual functions. For example, in the case of the following lead up and code chunk:

Let's plot our results of the primates and see the distribution of these species' sleep patterns. 

```r 
# Save the result of our filtering to an object 
sleepy_primates <- msleep %>% 
  filter(order == "Primates")

# Plot each species' amount of sleep 
ggplot(sleepy_primates, # plot data from the sleepy_primates object 
  aes(x=name, y=sleep_total)) + # with the species name on the x and the amount of sleep on the y axis
  geom_bar(stat="identity") + # use a bar plot
  coord_flip() # flip the x and y axes so that the species names are horizontal and easy to read

```

Would turn into: 

```
Let's plot our results of the primates and see the distribution of these species' sleep patterns. First, Save the result of our filtering to an object called here sleepy underscore primates. Next, we plot each species' amount of sleep using G G plot 2, where we plot data from the sleepy primates object with the species name on the X and the amount of sleep on the Y axis, specify the use of a bar plot and flip the X and Y axes so that the species names are horizontal and easy to read.
```

Specifying every parenthesis, comma, quote, and equal sign is cumbersome and so often is interpreted like above. 

Finally, Amazon Polly has trouble interpreting some of the words that are used in programming. You can see in the above example `ggplot2` was converted to `G G plot 2` - this is to prevent Amazon Polly from misprouncing the package name. We have a running list of all of the words that Amazon Polly has issues with [here](https://docs.google.com/spreadsheets/d/1RlZNiSV7CQhRLZj1-_EFTNEnErMjcpkVP_2NH6y73iQ/edit?usp=sharing). After you compile your video, you will have to listen to it and follow along with the script, waiting to find words that the program struggles with and then finding a phonetic transliteration of that word that she can pronounce. You will edit the script, recompile the video and listen again to make sure the fix was appropriate and Amazon Polly is now pronouncing it correctly. This can take multiple iterations. Best practice I've found is to listen once through the entire video noting the mispronunciations, fix them all in one go, and then recompile. On the next listen, you then only have to pay attention to those few words that have been changed. 

##### Compiling the video 

Complete instructions for compiling the videos are located in the `making_videos.Rmd` file, also found in this repo. Briefly, with packages `aws.s3` and `aws.polly`, you will set your Amazon keys to access the Polly service (to get your keys, follow the instructions [here](http://seankross.com/2017/05/02/Access-Amazon-Web-Services-in-R.html)). You will then use the `ari` package and the command `ari_spin` using the voice Joanna to create the video. To do so, ari needs to know where the script file and slide images are located. 

Finally, create a Google Drive folder containing all of the videos to share with Ira. He will download them and upload them to the Coursera system. 

##### Compiling issues 

Sometimes the version of Ari uses encoding that is not compatible with Coursera video/audio standards. Compile all of your videos and check that they work on Apple and Windows computers and upload to YouTube (listing as a private video) to confirm playback proceeds normally pre-Coursera. Once Ira has uploaded the videos to Coursera, make sure that the playback is still okay (previous problems include: audio going quicker than the slides progress, audio not being said for first slide so then all audio is off by one slide, missing the last 30 seconds of audio, or no audio for the last slide). The current version of Ari, at the time of this writing, is supposed to be compatible with Coursera, after we got Sean Kross to work with Ira and a Coursera partner to get the encoding correct, but there may still be small issues that you will need to catch. 

### Finalizing everything 

Once you've created your lesson, the slides, and the video for each lesson, you are good to go! While all of this will be saved to a private repo, we want to be able to share these lessons with the public. **But!** We need to remember to remove the quiz questions with the answers from the bottom of each lesson, so that precocious Coursera learners cannot go to the public repo and ace their quizzes with the answers they find there. Coursera also requires all the lesson files to be HTMLs hosted on an https site. To do this, create a repo on the [jhudsl GitHub](https://github.com/jhudsl), upload all of the MD files from the manuscript directory (plus all of the slide images in the resources/images dir) less the quiz questions, and preview and save all of your MD files as HTMLs.  

And with this, you should have a completed Coursera course! The final repo contains the HTMLs of the lessons and images of the slides and the videos are hosted in the Google Drive folder and uploaded to Coursera. With these three components completed, sit back and hope your new learners enjoy the course! 