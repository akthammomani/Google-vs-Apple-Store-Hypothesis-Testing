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
  
  
3. Modelling:
   * Hypothesis formulation:  
      - **Null hypothesis** **H<sub>null</sub>**: the observed difference in the mean rating of Apple Store and Google Play apps is due to chance (and thus not due to the platform).
      - **Alternate hypothesis** **H<sub>alternative</sub>**: the observed difference in the average ratings of apple and google users is not due to chance (and is actually due to platform)
      - We're also going to pick a **significance level** of 0.05. 
   * Getting the distribution of the data
   ![google_apple](https://user-images.githubusercontent.com/67468718/104695002-e4f67a00-56c0-11eb-8043-7349c0252ca9.JPG)
   
   * Permutation test:
      - Since the data aren't normally distributed, we're using a non-parametric test here. This is simply a label for statistical tests used when the data aren't normally distributed. These tests are extraordinarily powerful due to how few assumptions we need to make.
      - The difference in the means for Permutation1 (0.001103) now looks hugely different to our observed difference of 0.14206.
      - It's sure starting to look like our observed difference is significant, and that the Null is false.
      - platform does impact on ratings but to be sure, let's create 10,000 permutations, calculate the mean ratings for Google and Apple apps and the difference between these for each one, and then take the average of all of these differences.
      - Let's create a vector with the differences - that will be the distibution of the Null.

4. Evaluating and concluding 
   * What is our conclusion?
      - The p-value of our observed data is just the proportion of the data given the null that's at least as extreme as that observed data.
      - As a result, we're going to count how many of the differences in our difference list are at least as extreme as our observed difference.
      - If less than or equal to 5% of them are, then we will reject the Null.
      - Zero differences are at least as extreme as our observed difference!
      - p-value of the observed data is 0.
   * What is our decision?
      - It doesn't matter which significance level we pick; our observed data is statistically significant, and we reject the Null.
      - We conclude that platform does impact on ratings. Specifically, we should advise our client to integrate only Google Play into their operating system interface.

    

