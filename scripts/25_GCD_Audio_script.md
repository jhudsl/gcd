So much of the data generated today comes in the form of audio files. This could be all the data contained within the MP3 files of your favorite songs or the audio files saved in the archives from the speeches of politicians. While certainly not tabular data, there is a lot of information stored within all the audio files we've generated! It likely isn't surprising that there are many different file types to store audio data. MP3s are currently the most common file format, becoming popular as CDs became less popular due to the fact that the same audio file saved as an MP3 would take up much less space than the same file stored on a CD. 

There are two packages that will likely be helpful for analyzing audio files in R: tune R, a package to analyze music and speech, and seewave, a package to analyze, manipulate, display, edit and synthesize sound waves. Admittedly, working with audio files in R is not as common as working with tabular data; however, that just means there's room for development and exploration of how to approach audio files in R. . To see how others have worked with audio files in R, take a look through the provided examples, where Vesna Memisevic transcribes musical notes and also clusters music on the basis of their similarity. A lot of the functions in these packages are for highly specific use-cases that are out of the scope of this general introduction - particularly the analysis functions of see wave; check out some of the ways to use it at the provided link. For more in depth examples of how these tools can be used, check out the Additional Resources section at the end of this lesson. For now, we are going to do some of the most basic functions - read and write audio files, plot music amplitude and frequency, and create audio from within R. .  Before we get into it, first, let's install and load the two main audio analysis packages for R. . 

We will be playing with the song "Sneaky Snitch" by Kevin MacLeod, who releases his music as royalty free music under a Creative Commons: By Attribution 3.0 License, meaning it is available to be used in this course! Go to the provided link to download the "Sneaky Snitch" MP3 file. Move the downloaded MP3 file to a directory of your choice, that you can find from within R. We have chosen to save it in a folder on the Desktop called GCD. 

First thing we need to do is read the MP3 file into R. We will use the read MP3 function to do so. Call the Wave object to get some information about the audio file. Once we've loaded the file, we can play it, using the play function. Doing so should open either Windows Media player (if you are on a Windows computer) or iTunes (if you are on a Mac). If you have a problem with tune R not finding the correct media player for your computer when you call the play function, you can tell it what program to use using the setWavPlayer function. From this, we can see, for example, that our audio file is 136 seconds long, has a sampling rate of 44100, and is stereo (i.e.: has two channel audio). One thing to note, the file which started as an MP3 is now in Wave format. Wave files are an uncompressed audio file so there is maximum audio quality possible in this form. Helpfully, Wave files are the file type that is required by see wave - so this is a first step to working with both the tune R and see wave packages. 

For some of the plotting that we are going to do, we don't necessarily want to see the entire song - so let's shorten down the audio file so that we only look at the first 5 seconds. We will use the extract Wave function to extract the audio from 0 to 5 seconds. Preview the file to confirm the length is 5 seconds and play the resulting audio clip. Doing so, we have now created a Wave object that is the first five seconds of our song! 

One of the other base functionalities of tune R that we need to cover now is how to write an audio file from within R. We will use the write Wave function, specifying that we want to save the file to our GCD directory on the Desktop. tune R is only able to write out Wave files, which since they are uncompressed are much larger files than MP3s. This is also a great function for converting MP3s to Wave files. 

Audio analysis at first glance, doesn't seem like a particularly visual medium, but there are plenty of different ways we can plot sound! One way we can plot our data is to look at the amplitude (i.e.: the loudness) of the music across time. We can use the function plot With the wave object from the tune R package to plot the amplitude. Where there are peaks, the sound is louder; where the amplitude is closer to zero, the sound is quieter. One thing you might notice is that that plot command produces two plots. Each plot represents one of the channels in stereo audio: the left and the right. You can see that there are subtle differences between the left and right channel -- this is why songs sometimes can sound funny if you are only listening with one earphone. 

We can average the left and right channels to make the audio into "mono". This means that if you play the song across many speakers, all of them would play the exact same sound. Whereas in stereo, the speakers on the left are playing different sounds from the right. We will use the mono function to convert both channels into one. When you plot the amplitude, you can see that only one plot is produced.

The other main property of sound is frequency. While amplitude directs how loud something is, the frequency determines what note is heard. To plot this, we have to estimate the frequencies, using the periodogram and FF functions. We will then derive the notes from these frequencies using note From FF. And finally, we will plot these notes using the melody plot function. 

This is going to be imperfect given how complex our input music is, but you can see how this could be used to go from a music file to suggested notes, which can be further processed/analysed. 

To fully capitalize on the functions above, we are going to simplify the analysis by creating our own very simple audio file from within R. . Sound is essentially just made up of waves, so we can use the sine function from the tune R package to create waves of different frequencies, which in turn will be derived into notes, which we can then plot. First, we will create and play a single tone lasting 1 second to test the sine function. Then we will create a series of 7 sounds, each lasting 1 second with the frequencies specified. When you play the song, can you tell what it is?               

Now let's do the same plotting exercise as before, where we estimate the frequencies, derive notes and plot them, using periodogram, FF, note from FF and melody plot.

You can see from this analysis just how much more clean the frequency and note estimations are when the input is so simple. There are many different directions to take any of these analysis components - from here, you will need to explore the help files, vignettes, online tutorials, and other people's analyses to experience the full range of possibilities that these packages provide. 

In this lesson, we introduced some of the basic functions in the tune R package for audio analysis. We learned how to read and write audio files, listen to them from within R, and sample audio files to pull out audio clips. We then looked at some basic visualization of audio files - plotting either the amplitude or calculating the frequencies and notes and plotting those. Finally, we looked at how to create sound from within R using sine waves. Audio analysis is not the most common file type to analyse in R; but hopefully you feel equipped to at least approach audio analysis in R with this introduction. 