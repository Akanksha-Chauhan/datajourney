
## Wine Classification using Decision Tree 

**This problem illustrates the effect of the class imbalance of the accuracy of the decision trees. Download the red wine quality data from the UCI machine learning repository at: http://archive.ics.uci.edu/ml/datasets/Wine+Quality **

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
