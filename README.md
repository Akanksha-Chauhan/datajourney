# My Data Journey
Hello, 

This repository contains all the projects I have worked on in the last 2 years. In 2020, I enrolled in the MS - Information Systems program at DePaul University, Chicago and chose the data and analytics concentration. Thereafter, I learnt a great deal about data and data analysis techniques/processes. I am a strong believer in hands-on experience and I feel that is the true way of learning. Hence, I am posting my data journey here for people like me who come from a non-technical background and are starting out new with Python/Data Analysis/Data Science. 


## Project 1 - Identifying Biofilm infections as they are difficult to treat due to physiological heterogeneity. We can measure biological heterogeneity in a population of cells by looking at the cellular concentrations of ribosomes, by performing fluorescence in situ hybridization (FISH) analysis which correlates to the cellular level of ribosomes.

### Project Supervisor - 
**Prof. Thiruvarangan Ramaraj
Assistant Professor, SoC, CDM, DePaul University, Chicago**

**Aim:** Identifying Biofilm infections as they are difficult to treat due to physiological heterogeneity. We can measure biological heterogeneity in a population of cells by looking at the cellular concentrations of ribosomes, by performing fluorescence in situ hybridization (FISH) analysis which correlates to the cellular level of ribosomes. We will analyze the outputs/images of the various FISH analyses. 

We would aim to find a way/ways to easily quantify cellular heterogeneity in biofilms from a large library of epifluorescent microscopy FISH images. These are the images we will be analyzing in the project, to show how our method works. 

In our approach, we would perform rapid identification of biofilm regions from FISH images that are counterstained with fluorescent dyes. We are hoping to prove that this method is an easy to use and quick way to enable users to detect biofilm boundaries and extract intensity values from FISH images for quantitative analysis of biofilm heterogeneity. This methodology provides advances over other computational methods, allowing subtraction of spurious signals and non-biological fluorescent substrata.

We are mostly looking at the red color channel and then filtering out non-biofilm regions - Similar data cleaning/pre-processing to ensure it does not hinder our analysis). Finally, calculating rotation angle using linear regression and then performing the rotation and identifying the biofilm boundaries.

**Phase 1 Steps:**

·      Converted CZI file to PNG file.
·      Converted PNG file to Numpy Array to read pixel level data.
·      Split the Numpy Array  into RGB Channels.
·      Extract Red channel as a separate image/array.
·      Generated descriptive statistics from the data. 
·      Compared pixel level means between various CZI/PNG images. 

**Python code present for the above in the folder**

## Project 2 - Stock Prediction using Holiday-based Interaction Terms and VIX Scores

I worked on stock market data and applied regression modeling to derive insights, relationships, and predictions between teh various variables of the stock dataset. This is both interesting and important, as the Stock market is the biggest money machine and people lose/gain billions every day. This is not only an opportunity to test our data science skills but also to analyze if we can actually predict and guide our investment strategy better with historical data and machine learning. 

**Aim of the model– Predictions of closing price depending on the type of day (Holidays/Weekends) and volatility index.**

We will run the model at 4 PM to predict the closing price for that day. Depending on this predicted price we will either -
Questions answered by prediction-
**1.	Do we Hold/Sell/Buy more shares based on the predicted closing price before and after WEEKENDS and HOLIDAYS?**
**2.	Can we use the Volatility index (VIX) to improve our previous model for predicting the closing price of a stock?**

**Dataset** –
Stock market datasets are mostly focused on prices, volume, and trading behavior. In our dataset, we would be using the open and close price of a/few stocks along with their trading volume. This dataset is the basis of our experiment and has been used by all the team members in one way or other in this project. Hence not going into details here
However, in addition to the base dataset of High,Low,Close,Volume etc. I have also added dummy variables to mark weekends and holidays derived from the date variable. 
Lastly, regardless of variables or Model1/2, our dependent variable would be the stock’s closing price when markets closed.i.e at 5:00 PM.

**Model outcome**
Predicting closing price is the main aim here to guide the investor to either:
**HOLD/BUY Shares - In case the predicted closing price is higher than the current price. We will make a profit as prices will increase and hence, we can sell at a higher price later. 
                                                                        OR
SELL Shares - In case the predicted closing price is lower than the current price. We need to sell as the prices will go down and hence, we need to avoid a loss.**

Python code/notebooks present in the Stock Predictions folder above. 

## Project 3 - Patient Diagnosis Classifcation using Decision Trees (sklearn)

This problem illustrates the classification approach by using decision trees and the Lupus data. The data consists of 300 patient records. Each record contains 12 elements. The first 11 elements stand for different symptoms and the final element of each record indicates the diagnosis. 

**Steps Involved
1. Uploading the data and defining labels for Symptoms and the Diagnosis. 
2. Divide the data into the dependent and independent variables. X has all the symptoms and Y has the diagnosis. 
3. We then divide the data into training and testing datasets. I have chosen 30% of the dataset to be dedicated to testing our model
4. We then create the tree using the DecisionTreeClassifier within sklearn in these combinations to test the best accuracy – 

  **Use the Entropy criterion first without defining a maximum depth.  
    Use the Gini criterion first without defining a maximum depth.  
    Use the Entropy criterion first with setting a max_depth of 3.  
    Use the Gini criterion first with setting a max_depth of 3.  **
    

**Iteration 1 - Use the Entropy criterion first without defining a maximum depth** - We can see that this tree has a high depth(6) as we did not limit the maximum depth parameter while plotting the tree. Moving on, we will limit the depth and see how that affects accuracy.  There are a total of 27 nodes in this tree. Also, we should note that the leaf nodes very low samples/cases (less than 10 or 20). We have used the **entropy criterion** here. 
**The accuracy of this tree is 95.5% and below is the confusion matrix with only four incorrect classifications out of 90 classifications **

**Iteration 2 - Use the Gini criterion first without defining a maximum depth** - We can see that this tree has the same as compared to the previous tree (entropy based) but the number of nodes has increased by 4 from 27 to 31.   Also, we should note that the leaf nodes still has very low samples/cases (less than 10 or 20). 

**Iteration 3 - Use the Entropy criterion first with setting a max_depth of 3** - When we limit the maximum depth of the tree to 3, the accuracy falls slightly from 95.5% to 93.33% as No. of misclassifications went up from 4 to 6 when we limited the depth of the tree to 3. We can see that the depth of the tree has been reduced but the parent node is still S10 with the same number of samples 210.

**Iteration 4 - Use the Gini criterion first with setting a max_depth of 3** - When we limit the maximum depth of the tree to 3, the accuracy falls slightly from 96.66% to 94.44% and the total number of nodes reduces . No of incorrect classifications go up to 5 from 3 when we did not limit depth using Gini earlier and the number of nodes also decreased by half when limiting depth

## Findings ##

**The three most important lupus data features are Symptom 10, Symptom 11 and Symptom 1 as they have the highest normalized feature importance score in the decision tree.**

These importance values have been calculated using the features_importance method within sklearn, which computes the importance of features based on total reduction of the criterion brought by that feature. It is also known as the Gini importance.

Please see below, features sorted based on their importance:
**Feature	Importance**
'S10'	0.67894583
'S11'	0.1066765
'S1'	0.06469504
'S6'	0.03361569
'S9'	0.02773586
'S3'	0.02555059
'S4'	0.02206759
'S8'	0.01746896
'S7'	0.01604916
'S2'	0.00618763
'S5'	0.00100717

In our original decision tree (Gini, Depth = 6), we can see that most leaf nodes have a sample size which is less than 20. When we increase the minimum sample size of nodes to 20, we see that the complexity of the tree decreases along with the following changes to the decision tree: 
**•	Total number of nodes decreases from 31 to 13.
  •	The depth of the tree reduces from 6 to 3.
  •	However, the accuracy reduces from 96.66% to 90%.**
  

Code attached. 


## Project 4 - Wine Classification using Decision Tree (sklearn)

**This problem illustrates the effect of the class imbalance of the accuracy of the decision trees. Download the red wine quality data from the UCI machine learning repository at: http://archive.ics.uci.edu/ml/datasets/Wine+Quality**

Dataset has  6 classes (quality levels) in the dataset – 3, 4, 5, 6, 7, 8. 


**Iteration 1 - We create our initial decision tree using the Gini criterion without any limitations on depth and/or sample size.This gives us a rather large/complex decision tree with 585 nodes and a depth of 19. We have an accuracy of 60%. In our test dataset of 480 samples, our decision tree could predict 280 values correctly out of the 480 values resulting in a 60% accuracy.** 

We can see that the top three most important features are Alcohol, Sulphates and Volatile Acidity in our feature set. 
**Feature	Importance** 
alcohol	0.18494352
sulphates	0.10265159
volatile acidity	0.10096897
total sulfur dioxide	0.09594696
residual sugar	0.08886918
density	0.08144391
citric acid	0.07506444
pH	0.07427905
fixed acidity	0.07413289
chlorides	0.06821411
free sulfur dioxide	0.05348538

**Iteration 2 - Using the Entropy criterion, without limiting depth or sample size, we get a slightly better decision tree than the Gini criterion used above. However, the depth of the tree and number nodes increase considerably as well. This can result in overfitting too.The accuracy of this decision tree is 63.125% which is ~3% more than the previous decision tree we made using the Gini criterion. Meaning, our tree classified 303 test samples accurately out of total of 480 in the test dataset. More Depth and Nodes than the Gini Tree.    


**Further Iteration - We now test out various combinations to reduce complexity and incrase accuracy. Methods inlcude but not limited to - 

**1. Pruning - Limiting Depth of the tree**

     **Max Depth = 10** - The accuracy improves from the previous tree but is still lower than the tree in Q2. The new accuracy when we limit depth to 10 is 63.75% which is less than the accuracy of the tree earlier. 
     **Max Depth = 15** The accuracy further improves from the previous but is still slightly lower than the tree in Q2. The new accuracy when we limit depth to 15 is 64.375% which is slightly less than the accuracy of the tree earlier. 
     **Max Depth = 7** The accuracy decreased from the previous tree but is still slightly lower than the tree in Q2. The new accuracy when we limit depth to 15 is 64.375% which is slightly less than the accuracy of the tree earlier. 


**2. Reducing Sample counts - Set minimum sample size required to be at a leaf node -** 
   For minimum samples at leaf node = 50, the accuracy went down to 59.58% which is worse than the previous tree. 
   For minimum samples at leaf node = 100, the accuracy went down to 60.62% which is worse than the previous tree. 
   For minimum samples at leaf node = 150, the accuracy went down to 55.62% which is worse than the previous tree. 
   
**3. Removing low importance features-** Finally, I chose to look at feature selection and check if we can remove a few variables which are least important. For this we used the feature_importance method to get feature importance score. We can see that the lowest important feature is ‘Fixed Acidity’ (first feature) and so we create a tree after removing that variable/feature. 


### When we create the tree again, we can see that at max_depth =15 and removing an unimportant feature , our accuracy went up slightly even from the best tree we made in the B part of this question. The new accuracy is 67.5% which is the highest accuracy we ever received in all our combinations. ###


