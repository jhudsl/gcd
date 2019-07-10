# Ethics in data science

From the emails automatically marked as spam in your Inbox and facial recognition on Facebook to the targeted advertisements you see whenever you're online, data science has made its way into our everyday lives. Often, this is a positive because data scientists generally set out to improve the world (say, by analyzing crime data in hopes of reducing violent crime) or to make our lives easier (by preventing spam in our mailboxes, for example). However, data science projects are certainly not without negative consequences. We will discuss some of the companies who have run up against issues properly securing user data in the last lesson; however, protecting the privacy of users' data is not the only time data scientists should consider the ethics of their work. In fact, **ethical considerations should be made from the start of a project and should never stop being made**. We'll discuss what we mean by that in this lesson.

When we talk about the ethics of data science, we're talking about how to use data to improve the lives of individuals in our society in the world without causing harm to any groups with our work. We're talking about putting in the work ahead of time to avoid unintended negative consequences. Rather than acting surprised when groups are inadvertently harmed or only dealing with unintended consequences after they occur and harm others, an ethical data scientist will consider whether they are doing any harm at each step along the way. 

### What is Data Privacy? 

[Data privacy](https://en.wikipedia.org/wiki/Information_privacy) is:  

> the "relationship between the collection and dissemination of data, technology, the public expectation of privacy, and the legal and political issues surrounding them."

This complex definition correctly suggests that data privacy is not a simple matter. A simpler definition of data privacy would maybe be **how to keep personal and private information safe**.

Concerns arise with data privacy whenever there is personally identifiable information (PII) or sensitive information that is being collected, stored, used (and eventually destroyed and deleted). When handled appropriately, only people who should have access to the information do. When mishandled, this information could be accessed by others who should not have that information.

Data are everywhere, so it's incredibly important to think about data privacy early on in every single data science project. It's much better to be **too vigilant** than to make a mistake, allow data to fall into the wrong hands, and have to try to clean up the mess, as you'll see in a few examples below. So, think of data privacy concerns early and often to avoid making a mistake.

### Personally Identifiable Information

In the US, [Personally Identifiable Information](https://en.wikipedia.org/wiki/Personally_identifiable_information), often simply referred to by the terms initials, PII, is any "information that can be used on its own or with other information to identify, contact, or locate a single person, or to identify an individual". This could be a first and last name, a picture of someone's face, a driver's license number, a date of birth, an address, an individual's genetic code, or a telephone number, among many other pieces of information. All of these pieces of information could help identify a person. It's these type of data that *must* be handled extremely carefully.

When you sign up for an app on your computer or phone, you likely provide that company with some PII. You often give them your name and your address (among other information). You likely assume that this company will handle your data appropriately, and, if everyone is following the rules, they will. This means they won't share it with others, use it for purposes other than those for which you've given them permission, or allow other companies/people to steal your information. However, as reported regularly in the news, companies do *not* always handle your data as they should. We'll discuss what concerns *you* should have as you're working with other people's data and how data *should* be handled. 

### What is encryption?

When data are [encrypted](https://en.wikipedia.org/wiki/Encryption), all the information is jumbled into a code that can only be decoded by someone who has the key. This means that if data are intercepted while being transferred, the person who has intercepted the data will not be able to understand the data, as they won't have access to the key and will only have the completely jumbled information. It is a security measure to help keep data safe. 

#### HTTPS

An additional reminder: websites that have ht<!-- -->tps:// (rather than just ht<!-- -->tp://) also use encryption for data transfer, increasing security for data that are transferred. When working with PII and transferring data, be sure that the websites you're working with are using HTTPS.

### Human Security

[Human security](https://en.wikipedia.org/wiki/Human_security) is the concept that individual people (rather than just countries) should be kept safe and secure. With regards to data science, this means that when working on the Internet, regulations and laws should be made not just to protect the security of a nation, but rather to **protect every individual and their data**. 

Data science projects should **NOT**:  

* increase risk or harm  
* pose threats to individuals  
* make individuals' PII publicly-available or susceptible to theft  
* break any laws  
* share data with other groups/companies without the consent of the individuals  
* save data insecurely  

### Computer Security

[Computer Security (or cybersecurity)](https://en.wikipedia.org/wiki/Computer_security) is: 

> "the protection of computer systems from the theft and damage to their hardware, software or information, as well as from disruption or misdirection of the services they provide."

This means that, in addition to keeping individuals' data safe (maximizing human security), data science projects must *also* consider how to ensure that the computers and software they use and create are designed in a secure manner. For data science projects, this means that data being transferred over the Internet should be done so safely (using encryption) and that software you develop or use should not post PII or other sensitive information to the Internet.

### Open Science

There is an important movement in science currently where individuals promote what is known as **open science**. Practitioners of open science support making their scientific studies as transparent as possible. Specifically, they provide all the data, programming code, and software necessary to repeat their analyses. Open science is great for the scientific community and public, as everyone has access to the tools and data used. However, it is not without its privacy risks. 

Open Science practitioners are still responsible for protecting PII. This means that individual-level information (names, dates of birth, addresses, etc.) must all be removed from one's dataset before it is released to the public. Being a supporter and practitioner of open science is great, but you must always ensure that when you're releasing and sharing data, you are not inadvertently putting others at risk.

#### Open Data

Open data are data that are freely-available to anyone. Local and federal governments as well as many scientists make their data freely-available to the public. Open data are wonderful in that anyone can work with them. Sharing data is a great thing! But, sharing must be done with the caveats already mentioned. Individual-level information (PII) should be removed from datasets prior to release. Individuals should *not* be identifiable from data freely-available on the Internet.

#### Open-source Software

Like open data, open-source software are software that are designed to be freely-available to anyone. This means that the software code is all available, so others can not only download and use the software for free, *but also* can download the code and modify it for their own purposes. The R programming language is itself an open-source project and all packages made for R are also open-source. This means that programming in R will always be free, and the code will always be publicly-available. 

### Data Breaches

To understand data privacy, it's good to know definitions and best practices, but it's also important to learn from past mistakes. Companies have not always handled data securely. Here, we'll discuss a few famous data breaches and touch on what went wrong so these errors can be avoided in the future.

#### Facebook

In March of 2018, The [New York Times](https://www.nytimes.com/2018/03/17/us/politics/cambridge-analytica-trump-campaign.html) and [The Guardian](https://www.theguardian.com/news/2018/mar/17/cambridge-analytica-facebook-influence-us-election) both broke stories about how data from at least 50 million Facebook profiles were used by a company, called Cambridge Analytica, to build profiles of individual US voters, allowing individuals to be targeted with personalized political advertisements. 

While the details are provided in the links provided above, briefly here, the data were mined from individuals who had consented for their data to be used for academic purposes. *However*, Cambridge Analytica was collecting these data for non-academic purposes  *and* collecting data from friends of these individuals who had consented to have their data collected but who had not consented to have their data used. 

This **data breach** at Facebook demonstrated that Facebook did not have sufficient protocols in place to protect user data. As a result, Mark Zuckerberg, Facebook's CEO, [had to testify before Congress](https://www.nytimes.com/2018/04/10/us/politics/mark-zuckerberg-testimony.html) and the company has [promised to make changes to improve data security](https://www.independent.co.uk/life-style/gadgets-and-tech/news/mark-zuckerberg-facebook-2018-resolution-fix-post-update-latest-challenge-personal-a8142181.html).

#### Equifax 

In the Fall of 2017, Equifax, a credit-reporting agency, [disclosed that partial driver's license information was stolen from 2.4 million US consumers](https://www.equifaxsecurity2017.com/). This hack was traced back to a ["preventable software flaw"](http://www.businessinsider.com/how-did-equifax-get-hacked-2017-9). In other words, in March of 2017, Equifax identified a weakness in a piece of software they were using. However, they did not move to fix that weakness quickly. Partial drivers licenses were stolen from May until June of 2017. Thus, Equifax knew about the problem before any data were actually breached. The entire breach could have been avoided. Prioritizing security and moving to fix problems immediately upon realizing an issue is critically important.

#### Ashley Madison

In July of 2015, Ashley Madison, a website that helps people cheat on their spouses, [was hacked](http://fortune.com/2015/08/26/ashley-madison-hack/) and personal information, including e-mail addresses, from 32 million site member's were stolen and published. The consequences rippled through society, leading to [resignations, divorces and suicides](https://www.theguardian.com/technology/2016/feb/28/what-happened-after-ashley-madison-was-hacked). The "Impact Team," the group of hackers responsible for this hack, publicly stated that part of the reason they decided to release the data was because Ashley Madison had been charging users a $19 fee to completely erase their profile information, but that Ashley Madison had failed to actually scrub these data from their records. The security lesson here is that there should always be a mechanism by which users can remove themselves from a dataset. In the European Union, the [General Data Protection Regulation (GDPR)](https://eugdpr.org/) has stated that, by law, companies must have this feature built-in. Users should always be able to remove themselves from a dataset.

#### OKCupid 

In May of 2016, researchers [scraped profiles](https://motherboard.vice.com/en_us/article/8q88nx/70000-okcupid-users-just-had-their-data-published) from [70,000 users on OKCupid](https://www.vox.com/2016/5/12/11666116/70000-okcupid-users-data-release), an online dating site, and made them completely open to the public. These researchers did not (1) have permission from OKCupid, (2) obtain informed consent from the users, nor did they (3) remove PII from the data prior to release. Since their original release on [The Open Science Framework](https://osf.io/), given the issues with the dataset just mentioned and the fact that the collection of the data did not follow OKCupid's Terms of Service, the dataset was taken down. However, [hundreds of people had already downloaded the data](https://www.vox.com/2016/5/12/11666116/70000-okcupid-users-data-release) at that point.

In this case, a set of researchers did not comply with the Terms of Service they agreed to by signing up for OKCupid. While it was likely not illegal to obtain the data, as OKCupid made the data sort-of-public, it was certainly unethical, as the researchers did not take individual data security practices into consideration. So, even when you're not necessarily doing something *illegal*, you can still do something unethical that does not follow good data privacy practices.

Web scraping can be a very powerful tool, but can be an ethically fraught minefield - web scraping requires serious consideration of [laws, copyright, and terms of services](https://benbernardblog.com/web-scraping-and-crawling-are-perfectly-legal-right/) before doing so, and as in the example above, can get data scientists into some trouble. 

#### Strava 

A similar example of using data legally but with unintended negative consequences occurred when data from Strava, a popular fitness-tracking app, [gave away the location of secret US army bases](https://www.theguardian.com/world/2018/jan/28/fitness-tracking-app-gives-away-location-of-secret-us-army-bases) throughout the world in late 2017. 

Individual users would use the app to track their activity; however, in foreign countries, where Strava-users are almost exclusively foreign military personnel, bases can be identified easily from Strava heatmaps, which show all the activity tracked by its app users, as they are the only individuals contributing to the maps in those areas. The lesson to be learned here is that when releasing data, always consider possible unintended consequences. Think hard about the implications of your data and your analyses. Being vigilant and always considering data privacy and possible unintended consequences of your work are incredibly important.

### Performing ethical data science projects

Now that we've covered some of the ethical considerations to take into account when working with and sharing data, we should look at what this means for concrete decisions you will need to make before and throughout your data science project. 

#### Data Science Team

Data science projects can be done by an individual; however, more often, they are carried out by a team of individuals who are all interested in using data to answer an interesting question. Whether it's one person setting out to answer the question or a team working to answer this question, it's important at this outset of a project to really think about whether all the necessary individuals are on the team.

For example, if a group of data scientists were setting out to reduce crime in a neighborhood, it would be in their best interest to either be very familiar with that neighborhood (say, live there themselves) or to talk to individuals who currently live in that neighborhood to be as informed as possible before they set out to analyze their data. By working with individuals who have more knowledge about the neighborhood than someone who has never been there, the team will be less likely to make incorrect assumptions or leave out critical pieces of information when analyzing the neighborhood's data.

#### The Data

After ensuring that the team you've assembled to answer the question is the right team to do so, there are *many* considerations to be made when collecting data. 

##### Sampling Bias

When data are collected, it's difficult to ever get information about an entire population. Thus, when data are conducted, researchers will typically get data from a subset of individuals within the population (a process called sampling) and then *infer* something about the entire population using what they learned from the subset of individuals. They will try to ensure that their subset is a random subset of the population. However, whenever sampling of a population is done, there's a chance for sampling bias. 

Sampling bias occurs whenever the sample of the population collected does not accurately reflect the population as a whole. For example, if the population you're interested in studying is half female and half male, but the subset of people you've sampled is made up of 70% females and 30% males, then your sample is biased. Having a plan to avoid sampling bias is an important first step in the process of data collection. 

Checking the data after the data have been collected to ensure that the sample is not biased is an equally important step. When data are collected by survey for example, they may be sent out to an equal number of males and females; however, maybe more males respond than females. Even though your plan was solid, your responses are biased. This has to be accounted for during the analysis, as your responses do not accurately represent the population as a whole. 

And to be clear, gender is not the only consideration to make when sampling. Samples can be biased by many factors including (but not limited to) race and ethnicity, age, income, and education. Sampling bias should always be avoided both when planning to collect data and after the data are collected.

##### Informed Consent

In addition to collecting data in an unbiased manner, data must be collected ethically. This means that individuals must consent to participating in data collection. **Informed consent** requires that the individual agreeing to share their information knows what data are being collected, has been informed of any possible consequences, and has been provided full knowledge of any risks or benefits of participation. 

If data are collected on individuals and later on, a data scientist wants to use those data for a different purpose, they can only do so if the initial consent allowed for the data to be used in this manner. Alternatively, if the data are de-identified, they may be able to be used for future analysis; however, this must be done with care.

##### Privacy

When collecting personally-identifiable information, these data must be protected. They should not be shared without the participants' consent and they should be stored in a secure manner.

##### Withdrawal of consent

If an individual consents to their data being collected and later changes their mind, they have every right to do so. It is your responsibility as the person collecting the data to have an effective plan for removing any data already collected from that individual.

#### The Analysis

After avoiding sampling bias, collecting data ethically, and avoiding privacy issues in data storage, there are still a number of ethical considerations to take into account during one's analysis. While we don't discuss the details in these courses, machine learning is currently a popular way to analyze data. In general, it uses existing data to predict how individuals will behave in the future. This means that any biases in the data used to build the model (the existing data) will likely be perpetuated in the predictions. This means that, for example, in predictive policing, where data scientists are trying to predict where crimes are more likely to happen, if the data used to build the model (often referred to as an **algorithm**) come from crimes that have occurred in primarily black neighborhoods, they are going to predict that crime happens more in primarily black neighborhoods. Then, if police officers are placed in these neighborhoods, they are going to find more crime, *not* because crime has increased, but just because there are more police in the neighborhood now. Essentially, any biases in the data used initially are going to be perpetuated in the models they generate. This means that it is *critically* important that data scientists fully know and understand the data their working with, its biases, and its limitations.

Further, even *when* something like race is predictive in the model, it's important for a data scientist to consider whether or not that variable *should* be included. Are you *absolutely positive* that race is the important variable and it's not just that you have a biased sample? Instead, if you're trying to predict crimes, it's likely best to use data about crimes that have occurred and where they have occurred in the model rather than race, since race is not a measure of what you're interested in modeling. Considering the implications of one's work when carrying out an analysis is incredibly important, and making decisions that do not unnecessarily harm any group of people is critical.

It was previously common for analysts to say that "data do not lie" and "algorithms are impartial," but recent history has shown that that is simply not the case. Data are collected by humans, and humans are not without their biases. The best way to avoid bias in your data is to be aware of this and constantly check to make sure you're not disadvantaging groups of people with your analyses.

Before considering any data analysis and publishing your results, make sure:

1. You have gone through your data and have made sure there is not any major flaw in your data collection. Data can be biased. You can't use the result of a study that is mostly based on data from men to say anything about women.
2. You have checked for common mistakes in your analysis and know that your methodology is valid and defensible. Messing up the data for a single variable can drastically change the result of your analysis.
3. The results of your work can not be used to harass people, especially minorities, in any way.
4. Your analysis is independent of your opinion about the specific problem you're trying to solve using data. When carrying out an analysis, you should be looking for the answer to a question, but be careful not to *want* a specific answer. By wanting the analysis to go a certain way, you can subconsciously analyze the data to get that answer. It's best just to collect the data ethically and analyze it carefully. Then, the answer is whatever the answer from the analysis says it is.

You can do awesome things with your data science skills: cure diseases, analyze health data, prevent climate change, improve your city, or fact check politicians. Don't let your biases or mistakes get in the way.

#### After the Algorithm

Finally, after someone answers an awesome data science question with their really great analysis and tell the world, they often think their job is done. However, if you've designed an algorithm that is going to predict something going forward or that is going to continue to be used, it is your job to maintain that algorithm. That means that it's your job to check for biases after the fact. Is your analysis disadvantaging groups of people? If it is, should it be? Does something need to be changed? There *has* to be a way for you to update your algorithm going forward. If something is continuing to be used by others, your job isn't done once you've built the algorithm. It's your job to check for biases after the fact and to update your algorithm should there be a need.

##### Ethical Questions to Answer

To summarize this lesson up to this point, be sure to answer all of these questions for every data science project you carry out:

1. Does the **team** on this project include all the necessary individuals to avoid bias in our analysis?
2. Does our data collection plan address ways to **avoid sampling bias**?
3. Are the data we've collected or the data we're using to answer the question of interest **biased**? In what ways?
4. Has **informed consent** been obtained from all participants?
5. Do we have a mechanism to **remove an individual's data** from our dataset if they so choose?
6. Are the variables we've chosen to use for our analysis appropriate? Do they **discriminate** against anyone?
7. Is our analysis **transparent**? Do we understand *how* and *why* we're getting the answer we're getting?
8. Have we considered possible negative or **unintended consequences** of our analysis and its results?
9. Do we have a way to **update** our analysis/algorithm going forward should biases in the results be found?

### Ethics in Data Science

Now that we've discussed the ethical considerations to be made before and throughout every data science project, we'll discuss a few data science projects that were recently covered in the popular media due to the questionable ethics of the project. 

We present these examples not only to highlight the ethics of the particular project, but also to state the importance of considering the implications of your work. It is **not** enough to argue that you just "did the analysis" but "didn't think of the implications" of the work. As a data scientist **it is your responsibility to both do the analysis and consider the implications of your work**.

#### Data Science in Sentencing

In April of 2017, Wired reported in an opinion piece that [courts were using artificial intelligence to sentence criminals](https://www.wired.com/2017/04/courts-using-ai-sentence-criminals-must-stop-now/) and made the claim that such practices must be put to an end. The piece explained that courts and corrections departments across the United States collect data on defendants that are then used in an algorithm to determine the "risk" that defendant poses. This aim of this algorithm is to determine how likely it is that the individual will commit another crime.

These likelihoods of reoffending from the algorithm are then used to make decisions for how to set bail, what the sentence should be, and the details of that individual's parole. These tools are often built by private companies. This means that exactly *how* they work and what data are used to assess risk are not disclosed. The article in Wired highlights the use of [Compas](http://www.equivant.com/challenges/supervision-and-compliance-monitoring), one of these risk-assessment tools developed by a private company and used by the Department of Corrections in Wisconsin, in a judge's decision to give a man a long sentence, in part because of his "high risk" score from the algorithm. In a courtroom, however, because the specifics of how this algorithm works are not disclosed, a judge and jury would *not* be able to determine whether or not the likelihood of reoffending was calculated accurately by the algorithm.

Initially, arguments were made that removing human biases and judgment from bail, sentencing, and parole decisions would be for the benefit of society. This initial goal was a noble goal that would improve society. However, over time, biases in the data used to generate these algorithms that perpetuated into [biases in the algorithms' outcomes](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing), the lack of transparency in how they work, and failure to check for inequities and biases in the algorithms after they were put in place have led to unfair decisions being made. 

While individuals *may* have been looking to improve society with their algorithm at the outset of this project (or at least that argument can be made), lack of considerations of the implications of their work and lack of transparency in the process of generating and using the algorithm have led to questionable ethics in the use of algorithms to make sentencing decisions.

### Artificial Intelligence in the Military

In March of 2018, Gizmodo reported that [Google was helping the US Department of Defense use artificial intelligence to analyze drone footage](https://gizmodo.com/google-is-helping-the-pentagon-build-ai-for-drones-1823464533), a project that started in April of 2017. The project between Google and the Defense department is called Project Maven, and the goal of this project was initially to take drone footage and accurately identify objects (such as vehicles) and to track individuals in the footage collected. 

A number of Google employees were upset that Google would provide resources to the military that would be used for surveillance in drone operations. Due to the fact that in other non-military situations [the use of machine learning has led to biased outcomes](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing), other employees felt there needed to be further discussion about the ethics in developing and using machine learning technology before it was deployed by the military. In response to these concerns, a Google spokesperson stated that Google is working ["to develop policies and safeguards" ](https://gizmodo.com/google-is-helping-the-pentagon-build-ai-for-drones-1823464533), that the technology is being used for "non-offensive uses only."

In this and many large data science projects where machine learning and artificial intelligence are being used in situations where lives could be negatively impacted, the project would benefit from taking ethical considerations into account and discussing these in a transparent way *before* deploying the technology. Developing policies and safeguards after the fact is not enough. 

#### Facial Recognition in Law Enforcement

In May of 2018, the [ACLU reported](https://www.aclunc.org/blog/amazon-teams-law-enforcement-deploy-dangerous-new-face-recognition-technology) that Amazon had teamed up with law enforcement agencies to use Amazon's face recognition technology, [Rekognition](https://aws.amazon.com/rekognition/). The ACLU called this new technology, which can quickly scan images to "identify, track, and analyze people in real time" both "powerful" and "dangerous." This story was picked up by many news sources, including [a piece](https://www.nytimes.com/2018/05/22/technology/amazon-facial-recognition.html) in the New York Times. 

Proponents of using facial recognition technology in law enforcement cite that such technology can help locate and identify criminals more quickly than we would have been able to in the past and that it will help ["keep residents and visitors...safe"](https://www.nytimes.com/2018/05/22/technology/amazon-facial-recognition.html). Proponents also argue that those who use the technology do so within the limits of the law. 

Opponents, like the ACLU, however, cite the civil liberties and civil rights concerns that constant surveillance with using facial recognition technology pose. The ACLU argues that there is substantial "capacity for abuse" and due to this, that citizens should not be watched by the government any time they walk outside, that facial recognition systems threaten freedom, and that the deployment of these technologies pose a greater threat to communities that are already unfairly targeted by the political climate. 

Concerns with the technology cite that anyone can be identified, not just criminals, a problem for civil liberties. Opponents further question the accuracy of the technology. Inaccuracies, which would misidentify individuals and suggest they were guilty of a crime when they were, in fact, not is clearly a problem. Further, there are concerns that accuracy varies based on gender and race, which if true, poses a clear bias in the use of this technology for the identification of criminals, as certain groups of individuals would be misidentified more frequently than others. 

### Additional Resources

* [Ethical Checklist for Data Science](https://dssg.uchicago.edu/2015/09/18/an-ethical-checklist-for-data-science/), by Alan Fritzler
* [*Weapons of Math Destruction*](https://www.amazon.com/Weapons-Math-Destruction-Increases-Inequality/dp/0553418815), by Cathy O'Neil
* [*Automating Inequality*](https://www.amazon.com/Automating-Inequality-High-Tech-Profile-Police/dp/1250074312/ref=sr_1_1?s=books&ie=UTF8&qid=1531417315&sr=1-1&keywords=automating+inequality), by Virginia Eubanks
* [Courts are Using AI to Sentence Criminals. That must Stop Now](https://www.wired.com/2017/04/courts-using-ai-sentence-criminals-must-stop-now/), by Jason Tashea in Wired
* [Machine Bias](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing), by Julia Angwin, Jeff Larson, Surya Mattu and Lauren Kirchner at ProPublica
* [Amazon Teams Up With Law Enforcement to Deploy Dangerous New Face Recognition Technology](https://www.aclunc.org/blog/amazon-teams-law-enforcement-deploy-dangerous-new-face-recognition-technology), by Matt Cagle and Nicole A. Ozer with the ACLU 
* [Amazon Pushes Facial Recognition to Police. Critics See Surveillance Risk.](https://www.nytimes.com/2018/05/22/technology/amazon-facial-recognition.html), by Nick Wingfield at the New York Times
* [Google Is Helping the Pentagon Build AI for Drones](https://gizmodo.com/google-is-helping-the-pentagon-build-ai-for-drones-1823464533), by Kate Conger and Dell Cameron at Gizmodo

### Summary 

Hopefully we've explained a number of considerations to take into account when working with and sharing data. Data are powerful. It's important to use them responsibly.

* Be careful with PII
* Fix security issues immediately
* Keep individuals' data safe
* Don't steal data
* Even if it's legal, it may not be right or ethical
* Consider unintended consequences of your work

We also went over some of the ethical considerations that must be taken into account at each stage of a data science project and looked at some of the occasions where data science has gone wrong. 

### Slides

This lesson's slides can be found [here](https://docs.google.com/presentation/d/1Q4Np_8mXBPjFRxtjWUpDj_PciKrLam5uY-KEnM4rivw/edit?usp=sharing)  
