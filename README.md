# ✰ Google Play vs Apple Store: 

![header_PT_0803_The-Differences-Google-Play-vs-Apple’s-App-Store](https://user-images.githubusercontent.com/67468718/103197528-0a028480-489b-11eb-9892-681d69c351c8.jpg)

A company that designs operating systems, wants to build a major apps store into their user interface. To this end, they want to know whether Google Play
apps have higher reviews on average than Apple Store apps (or vice versa) , as they’re intending to strike a deal with just one of these companies. 

To help this company, we’ll work through a series of steps known as the Data Science Pipeline, or DSP. The DSP is a general and fairly broad sequence of steps data
scientists use to tackle and solve business problems. 

## ✰ Datasets source: 
   * Apple Store: https://www.kaggle.com/ramamet4/app-store-apple-data-set-10k-apps
   * Google Play: https://www.kaggle.com/lava18/google-play-store-apps

## ✰ Stages of the project

1. Sourcing and loading 
   * Load the two datasets
   * Pick the columns that we are going to work with 
   * Subsetting the data on this basis 
 
 
2. Cleaning, transforming and visualizing
   * Check the data types and fix them
   * Add a `platform` column to both the `Apple` and the `Google` dataframes
   * Changing the column names to prepare for a join 
   * Join the two data sets
   * Eliminate the `NaN` values
   * Filter only those apps that have been reviewed at least once
   * Summarize the data visually and analytically (by the column `platform`)  
  
  
3. Modelling 
   * Hypothesis formulation: 
   
   1. Our Null hypothesis is just: 
      **H<sub>null</sub>**: the observed difference in the mean rating of Apple Store and Google Play apps is due to chance (and thus not due to the platform).

   2. The more interesting hypothesis is called the **Alternate hypothesis**:

      **H<sub>alternative</sub>**: the observed difference in the average ratings of apple and google users is not due to chance (and is actually due to platform)

      We're also going to pick a **significance level** of 0.05. 
   
   * Getting the distribution of the data
   * Permutation test 


4. Evaluating and concluding 
   * What is our conclusion?
   * What is our decision?
   * Other models we could have used. 
    

