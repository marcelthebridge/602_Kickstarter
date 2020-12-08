<img src="https://github.com/marcelthebridge/602_Kickstarter/blob/main/anything_helps.png" width=500 />

# Kickstarter Exploratory Data Analysis and Modeling
This project was an exervise in machine learning principles.

## Overview
Kickstarter is a crowdsourcing venture that seeks to empower individuals and groups worldwide.  
There have been some incredible success stories such as:
- [Pebble Time smartwatch](https://www.kickstarter.com/projects/getpebble/pebble-time-awesome-smartwatch-no-compromises)
  - Earned over $20 million in funding, with other 2 million devices shipped. 
  - Sadly no longer a company.  I guess popularity does not ensure success. The company was sold, and funds for the Pebble 2 were returned.
- [Travel Jacket](https://www.baubax.com/)
  - Earned $9 million in funding.
  - Perhaps the dorkiest item in existence, the jacket boasted pockets for every gadget and device you could imagine.  It also had built in gloves AND a neck pillow.
- [Exploding Kittens](https://explodingkittens.com/)
  - Just shy of $9 million in funding
  - I have seen this game on almost every friend or family members bookshelf I can remember.

## Contents
- [Technical Notebook](Kickstarter_Final.ipynb)
- [Data](Kickstarter_Data.zip)
- [README](README.me)
- [Images](images)
- [Original Kickstarter EDA notebook](Kickstarter_Early_EDA.ipynb)
  - This was an attempt earlier in the semester to explore the data.  This was worked on during the first 4 or 5 weeks of the semester.  

## Goals
- Explore the Kickstarter dataset, and get a sense of:
  - Trends at a Glance
  - Currency Breakdowns
  - Category Breakdown
   - Success to Failure rates
    - Grouped by Category
    
  ## Data
 The dataset contains a few hundred thousand project campaigns that had been hosted on Kickstarter.
 Features to note include:
  - name
    - Name of the project
  - category
    - The broad category the project fits under
   - main_category
    - Easier to think of this as the more specific category of the project
  - campaign_length
    - An engineered feature that is the length(duration) of the campaign
  - state
    - Status of the project:
      - completed
      - failed
      - canceled 
      - live
      - suspended
      
      
# So, what did we learn?

## Some clear breakdowns of what people are interested in creating for the world
<img src="/images/cat_breakdown.png" />

## The stats on failed vs successful categories
<img src="/images/pass_fail_cat.png" />

## Model exploration or How I overreached and met my limits
I may have gotten a little lost during my journey for making use of various tools and models.  The more I fell into the documentation and methods, the further I got from focusing on the goal.  The amount of support and options for conducting classifications is astounding. I had a few false starts and redos when performing my early EDA, and then doing the clean up.  One Hot Encoding felt like it would give me the greatest understanding of all the varied possible values in the features selected, although I should have performed a heat map correlational plot before making the changes I did to the dataframe.  

<img src = "/images/model_eval.png"/>

We have a clear strong performer in our GradientBoosting model.  
- From a [piece by Jason Brownlee](https://machinelearningmastery.com/gentle-introduction-gradient-boosting-algorithm-machine-learning/) :
  - Building from the idea of Probably Approximately Correct learning, boosting is the idea of filtering observations, leaving those observations that the weak learner can handle and then focusing on developing new weak learners to handle remaining observations.  Gradient Boosting also built upon the foundation of [AdaBoost](https://machinelearningmastery.com/boosting-and-adaboost-for-machine-learning/) which itself is used to boost performance of decision trees.  
  - Gradient Boosting is comprised of three elements:
    - Optimization of a loss function
    - Weak learner for predictions
    - An additive model to add weak learners, minimizing the loss function
  - There is a lot of very interesting work out there on Gradient Boosting and based on how this model outperformed the others, this is going to be one I will keep a tab on as I seek to update and perfect my notebooks. 
  
  #### Other limitations
  With one hot encoding creaing many new columns, I found my understanding of how I was handling the data to become less and less grounded. I adjusting my data prep a few times trying to employ better feature selection, but settled on a more is more approach.
  I also think that, as I revisit this data set I would like to create a better set of functions to split data sets into categories and get better ML data  based on the interest of the user.  Do we want to investigate tech only campaigns? Maybe if the pandemic continues we will want to only fund campaigns that are focused on generating new entertainment content. 
  What we are left with is a seemingly overbuilt frankenstein notebook that can be hacked apart and strengthened into a very smart process for a variety of interests.  
