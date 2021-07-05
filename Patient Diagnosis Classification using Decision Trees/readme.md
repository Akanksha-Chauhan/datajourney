# Patient Diagnosis Classifcation using Decision Trees (sklearn)

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
