# HackerNews Chrome Extension

This is an extension built to work with HackerNews.com. When the extension is used, 
it takes the article from the current page you are look at and uses advanced search techniques 
to find 5 articles that of similar interest that you can choose to look at. 

## Library Requirements

In order to run this github, you will need the following libraries installed:
Os, numpy, time, sklearn, joblib, pandas, sys, crawler, nltk, string, tqdm, itertools, 
ast, bs4, calendar, datetime, requests, tldextract, validators, fastAPI.

## Video on how to set this up (video presentation):

https://www.youtube.com/watch?v=2MKptyXzBh8

## Setting up the Extension: 

## Step 1: getting the data. Two methods for getting the data

### method 1: download the following data

If you just want to use the following github, here is file contained data already crawled by this crawler: https://drive.google.com/file/d/11bZ53ukSD7kwLpItcdEId142TtF-KS4H/view . From there, you can download these files: https://drive.google.com/file/d/1K1K1dWj8UWjoSL3QJW-ZxaKYDGB0gucP/view . These files are the .pkl files that store the k-means cluster, the TF-IDF vector, and some other anciallary information

### Method 2: getting the data manually


### Method 2a: 

To get the data necessary for the extension to work, we first need to crawl Hackernews.com for data. To do so, you need to run the main function in crawler.py. There is a pre-set in the function, but that can be changed to the date range you desire. It will crawl up to 365 days ahead of the initial date entered. This is the longest step of the whole process, and it will take time to crawl the data.

### Method 2b: Clustering.py

After you have crawled the data, the next step is to run the main function in clustering.py. This function takes in three inputs: the folder containing all the data, the word cluster, and the amount of clusters you would like the data to be divided into. An example would be: py clustering.py <directory_holding_files> cluster <#>. This can vary based on user performance needs. After this is done, it will create and store pickle files that will hold all the info necessary for the chrome extension to work.

From here, both methods follow the same steps

### Step 2: Setting up the API

From here, we need to set up the FastAPI, which is simple. One needs to go to the terminal they are using and type ``` 
uvicorn api:app --reload  ```
This will begin the process of loading all the data acquired from clustering.py into the file so that the API will work. Eventually a message in the terminal will pop saying that the API is all set, and ready to begin.

### Step 3: Adding the Chrome Extension
Now all we do is add the extension to Chrome. Go to the settings for chrome extensions and enable developer tools. From there, press the button load unpacked. The folder ro unpack is the folder extensions in the github code. Once this is loaded, you are all set and ready to use the extension!

## Using the extension

To use the Extension itself, you just need to click on the extension, and press the button get similar articles. This will take about 30 seconds to work, but when its done a table of 5 article titles and URLS will pop up that you can feel free to look at. From there, you can repeat as many times as you want on any page. Happy Usage!
