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





