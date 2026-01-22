- `Python3`
- `BalancedRandomForestClassifier`

##  Problem
In this project we find out if an individual earns >50k USD using certain demographic and educational information about them. We will be using the dataset[^1] https://archive.ics.uci.edu/dataset/2/adult to solve this problem. 

## Dataset
The dataset was sourced from , it consists of 14 features and 48842 records containing information such as sex, education, marital status etc. The extraction was done by Barry Becker from the 1994 Census database.

## Approach
I treated this as a binary classification problem. The dataset is imbalanced, with one income group appearing much less frequently than the other. Since tree based ensemble models tend to handle class imbalance better, I chose to use a Balanced Random Forest (BRF) classifier. Using a BRF allowed me to deal with the imbalance directly during training, so I didn’t need to apply additional techniques like oversampling, undersampling, or SMOTE to the training set.

The model was trained and evaluated using standard preprocessing steps.

## Results
The model achieved an overall accuracy of approximately 85% with a ROC-AUC of 0.80. Performance on the minority class (income >50K) showed a balanced precision and recall around 0.70, indicating that the model was able to identify higher-income individuals reasonably well despite class imbalance. These results highlight the tradeoff between overall accuracy and minority class performance in imbalanced classification problems.

## Reflections
Working with an imbalanced dataset highlighted the importance of choosing appropriate evaluation metrics beyond accuracy. This project reinforced how model performance and interpretability tradeoffs become especially important in real world decision making contexts.

Another important thing to keep in mind with this dataset was that it included several sensitive demographic features. Due to the presence of such details the model is evaluated with emphasis on transparency and responsible use.

## Conclusion

While working with an imbalanced data can be challenging for many reasons, this project taught me the importance of using a variety of metrics to find out the real performance of a model. In the future I would like to experiment with other tree based models (XGBoost) etc and compare their performance. Also, the dataset itself is quite old, and I would love to experiment with more recent data and probably uncover new insights about income prediction.


References

[^1]: Becker, B. & Kohavi, R. (1996). Adult [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5XW20.
