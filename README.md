**School of Computer Science and Engineering (Nanyang Technological University)
SC1015 Lab FDAA Group 4**

**Group Members:**
1. Quek Jared (U2321219D)
2. Teo Wen Jie Dexter (U2322933C)
3. Edison Lim Wei Xuan (U2320929L)

**Title:** Predicting Pneumonia using Convolutional Neural Network

**1. Problem Formulation:**

Our Dataset: https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

Our Aim: To create a model that acts as the first layer when screening patients for Pneumonia. Only when the model predicts that the patient has Pneumonia, then the radiologists will take a look at the X-rays to confirm whether they have Pneumonia or not. This will greatly reduce the amount of X-rays that each radiologist would have to look through and can reduce the number of errors they make. Research has shown that after a certain number of hours, the accuracy of radiologists would decrease so it is crucial that we can reduce the number of X-rays they need to read through. 

**2. Data Preparation and Cleaning:**

    - We converted our image data into a NumPy array to allow for further processing and analysis of the image data in Python.
    - We resized all the images to the same size since many machine learning models, especially convolutional neural networks (CNNs), expect input images to have a consistent shape.
    - The smaller image size also requires less memory amd leads to faster training times.
    - We also performed some changed to the image data which we thought might affect the robustness of our model (Augmented our image data to ensure that there is balanced data in our training data).

**3. Training our Model:**

We decided to train 4 different models to see which model would produce the best metrics. We trained 2 models for 15 epochs (one augmented, one non-augmented) and trained another 2 models with an early stopping callback, looking at validation accuracy. (one augmented, one non-augmented)

**4. Deciding which model is best for our goal:**


Since our goal is to predict which patient has Pneumonia, we want the model to have:

    - A high sensitivity (True Positive Rate) ensures that the model can detect as many pneumonia cases as possible, minimizing the risk of false negatives (missed pneumonia cases).
    - A high specificity (True Negative Rate) reduces the number of false positives (non-pneumonia cases incorrectly classified as pneumonia), which helps minimize unnecessary follow-up by radiologists.

In the context of reducing the workload of radiologists, optimizing for high sensitivity while maintaining reasonable specificity is often desirable to ensure that pneumonia cases are not missed while minimizing unnecessary follow-up for non-pneumonia cases. We have decided that it is ultimately more suitable to prioritise a high sensitivity in our model as we do not want to miss any cases which is the main point since our model is the first check to see whether patients have Pneumonia.

**5. Data driven insights and Conclusion:**

The metrics (TPR and TNR) of each model can be found in our python notebook. As of now, the specificity of our model is still low which means that radiologists still have to look through the bulk of X-rays. However, once we increase the number of training data, we believe that we can more accurately predict which patient has Pneumonia to achieve our goal. Ultimately, our model still manages to achieve our goal to filter out X-rays that radiologists do not need to look through which reduced their workload. 

**Individual Contributions:**

Dexter: Data Visualization, Video Production

Jared: Neural Networks, Data Extraction

Edison: Neural Networks, Data Visualization

**References:**

https://doi.org/10.3348%2Fkjr.2023.0966

https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia/data

https://www.svhlunghealth.com.au/conditions/pneumonia 

https://www.moh.gov.sg/resources-statistics/singapore-health-facts/principal-causes-of-death 

https://www.analyticsvidhya.com/blog/2022/01/convolutional-neural-network-an-overview/ 

https://doi.org/10.1259%2Fbjr.20190043
