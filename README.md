<p align="center">
  <a href="https://www.udacity.com/">
    <img src='https://course_report_production.s3.amazonaws.com/rich/rich_files/rich_files/5511/s300/udacity-logo.png' alt="Udacity logo" width = 100px>
   </a>
</p>
<h3 align="center"><a href='https://www.udacity.com/course/data-analyst-nanodegree--nd002'> Udacity Data Analyst Degree </a></h3>
<h4 align="center">  Project IV: Wrangle and Analyze Data </h4>
<h5 align="center">  January 2023  </h4>

## Table of Contents
- [Introduction](#Introduction)
- [Project Instruction](#instruction)
- [Project Motivation](#ProjectMotivation)
- [Project Submission](#ProjectSubmission)
- [Result](#result)

## Introduction <a name="Introduction"></a>

In this project, I wrangle the data of tweet from the WeRateDogs twitter account along with the image prediction data set. After wrangled data, I come up with the analysis based on both data set. Finally, deliver two reports which are wrangle report which use for communication internally, and act report to report findings to the public.

## Udacity's Project Instruction <a name="instruction"></a>
Real-world data rarely comes clean. Using Python and its libraries, you will gather data from a variety of sources and in a variety of formats, assess its quality and tidiness, then clean it. This is called data wrangling. You will document your wrangling efforts in a Jupyter Notebook, plus showcase them through analyses and visualizations using Python (and its libraries) and/or SQL.

The dataset that you will be wrangling (and analyzing and visualizing) is the tweet archive of Twitter user @dog_rates, also known as WeRateDogs. WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, though? Almost always greater than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs Brent." WeRateDogs has over 4 million followers and has received international media coverage.

WeRateDogs downloaded their Twitter archive and sent it to Udacity via email exclusively for you to use in this project. This archive contains basic tweet data (tweet ID, timestamp, text, etc.) for all 5000+ of their tweets as they stood on August 1, 2017. More on this soon.
  <h3 align="center">  <img src='https://video.udacity-data.com/topher/2017/October/59dd378f_dog-rates-social/dog-rates-social.jpg' width = 350px> </h3>

WeRateDogs banner
Image via Boston Magazine

Project Steps Overview
Your tasks in this project are as follows:

Step 1: Gathering data

Step 2: Assessing data

Step 3: Cleaning data

Step 4: Storing data

Step 5: Analyzing, and visualizing data

Step 6: Reporting

your data wrangling efforts
your data analyses and visualizations

## Project Motivation <a name="ProjectMotivation"></a>

### Context

Your goal: wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. The Twitter archive is great, but it only contains very basic tweet information. Additional gathering, then assessing and cleaning is required for "Wow!"-worthy analyses and visualizations.

### The Data

In this project, you will work on the following three datasets.

### Enhanced Twitter Archive

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced." Of the 5000+ tweets, I have filtered for tweets with ratings only (there are 2356).

<h3 align="center"> <img src='https://video.udacity-data.com/topher/2017/October/59dd4791_screenshot-2017-10-10-18.19.36/screenshot-2017-10-10-18.19.36.png' width = 850px> </h3>

<p align="center"> The extracted data from each tweet's text </p>

I extracted this data programmatically, but I didn't do a very good job. The ratings probably aren't all correct. Same goes for the dog names and probably dog stages (see below for more information on these) too. You'll need to assess and clean these columns if you want to use them for analysis and visualization.
<h3 align="center"> <img src='https://video.udacity-data.com/topher/2017/October/59e04ceb_dogtionary-combined/dogtionary-combined.png' width = 850px> </h3>

Dogtionary from WeRateDogs book
The Dogtionary explains the various stages of dog: doggo, pupper, puppo, and floof(er) (via the #WeRateDogs book on Amazon)

### Additional Data via the Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But you, because you have the WeRateDogs Twitter archive and specifically the tweet IDs within it, can gather this data for all 5000+. And guess what? You're going to query Twitter's API to gather this valuable data.

### Image Predictions File

One more cool thing: I ran every image in the WeRateDogs Twitter archive through a neural network that can classify breeds of dogs*. The results: a table full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).
<h3 align="center"><img src='https://video.udacity-data.com/topher/2017/October/59dd4d2c_screenshot-2017-10-10-18.43.41/screenshot-2017-10-10-18.43.41.png' width = 850px> </h3>

<p align="center"> Tweet image prediction data </p>

So for the last row in that table:

tweet_id is the last part of the tweet URL after "status/" → https://twitter.com/dog_rates/status/889531135344209921
p1 is the algorithm's #1 prediction for the image in the tweet → golden retriever
p1_conf is how confident the algorithm is in its #1 prediction → 95%
p1_dog is whether or not the #1 prediction is a breed of dog → TRUE
p2 is the algorithm's second most likely prediction → Labrador retriever
p2_conf is how confident the algorithm is in its #2 prediction → 1%
p2_dog is whether or not the #2 prediction is a breed of dog → TRUE
etc.
And the #1 prediction for the image in that tweet was spot on:
<h3 align="center">  <img src='https://video.udacity-data.com/topher/2017/October/59dd4e05_dog-pred/dog-pred.png' width = 350px> </h3>
<p align="center"> A golden retriever named Stuart </p>


So that's all fun and good. But all of this additional data will need to be gathered, assessed, and cleaned. This is where you come in.

## Project Submission <a name="ProjectSubmission"></a>
Create a 300-600 word written report called wrangle_report.pdf or wrangle_report.html that briefly describes your wrangling efforts. This is to be framed as an internal document.

Create a 250-word-minimum written report called act_report.pdf or act_report.html that communicates all the insights and displays the visualization(s) produced from your wrangled data. This is to be framed as an external document, like a blog post or magazine article, for example.

Both of these documents can be created in separate Jupyter Notebooks using the Markdown functionality of Jupyter Notebooks, then downloading those notebooks as PDF files or HTML files (see image below). If you want to write a report this way, there are two Jupyter Notebook files, named "wrangle_report" and "act_report" for you in the workspace. You might prefer to use a word processor like Google Docs or Microsoft Word, however.

## Result <a name="result"></a>

I've generated the <a href="https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/wrangle_report.pdf">wrangle report</a> for internal communication purpose, and<a href="https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/act_report.pdf
"> act report </a> to communicate the finding to the public which you can find the result of analysis. 

By the way, do you know what is the most popular dog name? or which stage of dog that have been retweeted the most? Find the answer in <a href="https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/act_report.pdf
"> act report </a>

<h3 align="center">
  <a href="https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/wrangle_report.pdf">
    <img src='https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/wrangle_report_cov.png' alt="Singhanart Nakpongphun Wrangle and Analyze Data", width = 350>
   </a>
    <a href="https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/act_report.pdf">
    <img src='https://github.com/Taebetta/Wrangle-and-Analyze-Data-Udacity-Data-Analyst-Nanodegree-Project-4/blob/main/act_report_cov.png' alt="Singhanart Nakpongphun Wrangle and Analyze Data", width = 350>
</h3>

