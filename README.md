#  Label Bias with resampled experiment

# Details about the case study
**Data**. We explored a 2023 Kaggle dataset, surveying 2556 adults aged 18–60 across multiple cities, exploring depression risk through demographic and lifestyle factors such as gender, job status, sleep duration, dietary habits, education, and family history. With 1223 females (214 at risk) and 1333 males (241 at risk), the dataset labels depression risk as a binary variable based on self-reported data, not clinical assessments.

**Simulating label bias**. To study the effect of label bias, our study simulates bias in observed labels y_obs, obtained by randomly flipping a portion of the actual female depression labels from 0 (no depression) to 1 (depression). This is done at different proportions from 5% to 70% in 5% increments, to observe the effect of different amounts of bias in the observed labels y_obs. By comparing the model behaviour when testing the algorithm against either the original labels y_true or the biased observed labels y_obs, we are able to evaluate how label bias impacts model performance, interpretation, and algorithmic fairness assessments. 

**Model training and validation**. To demonstrate the effect of label bias we train a Gradient Boosting Model with a 80/20% split for training and testing. This was repeated 10 times with resampled training/test splits. To imitate real life behavior, we train with the observed biased labels y_obs and report both the observed and true underlying performance for the test labels y_obs and y_true. For interpretability, we used Variable Importance in Projection (VIP), a gain-based feature importance method which is often used to evaluate and interpret the performance of decision trees, random forests, and gradient boosting machines. 

