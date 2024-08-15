# Covid-19-CNN
College project aimed at creating a convolutional neural network to identify COVID-19 through lung X-ray images.

Please, Refer to the jupyter notebook available in the repository in order to see the Pyhton code.

**Disclaimer**

> This project was solely created for educational purposes. I drew inspiration from the original work done by myself and my colleagues in class to create an enhanced version of my own, focusing exclusively on the identification of COVID-19 using a CNN, and to compare its performance with an already existing standard.

> Within the jupyter notebook file, you will find a references section listing the names of the authors of the original work submitted for the course.

#### 2023F-T3 AISC2007 - Deep Learning

---

#### CASE STUDY Week 6 - Predict Covid-19 based on lung X-Rays

> Teacher : **Bhavik Gandhi**
---

#### Description
- The professor provided us with a dataset of lung X-rays paired with image masks highlighting the position of the lungs.
- The dataset is organized into three folders:

    **COVID-19**: X-rays classified as suffering from COVID-19.<br>
    **Non-COVID**: X-rays classified with other diseases.<br>
    **Healthy**: X-rays classified as healthy.<br>


#### Author
> Fabio Duarte Junior <br> fabioduartejunior@loyalistcollege.com / fabio_jr@pm.me


#### Objective
> Build a model to predict whether a person has COVID-19, other infections, or no lung infection from the lung X-rays.

#### My Approach
> 1 - Data Preprocessing: Analyzing image histograms and applying image processing techniques using the OpenCV (CV2) library.
>> I experimented with various transformations to enhance the image, ultimately settling on a combination of CLAHE, HE normalization, and sharpening techniques.<br>
>> Subsequently, I cropped the images using the image masks.

> 2 - For modeling, I used a CNN (Convolutional Neural Network) and also attempted to implement a version of the AlexNet CNN as a baseline to compare my model.
>> I used Precision, Recall, and F1-Score as metrics, since it is a medical diagnostic case and it is important to have confidence in both positive and negative results.<br>
>> I am also measuring the AUC-ROC to assess how well my model can differentiate between classes.<br>
>> In addition, I guided my CNN modeling by observing the outputs of the layers.<br>
>> I ran executions with 90 epochs varying the batch size, always using the same for both CNN implementations.

#### Conclusion
>> After several attempts and testing various approaches, I believe I have reached a satisfactory result compared to AlexNet.<br>
>> I achieved a model that has excellent ability to distinguish between classes and a good capacity to identify cases of COVID-19.<br>
>> Compared to the AlexNet-like implementation, the results were very close across all metrics, but a crucial detail in favor of my model is<br>
>> that the epoch processing speed is much lower than that of the AlexNet-like implementation.<br>
>> While each epoch of my CNN model took an average of 20 seconds to run, the AlexNet-like implementation took no less than 60 seconds, showing several spikes.<br>
>> In other words, I achieved a model with very similar metrics, but that consumes far less computational resources and time than an AlexNet-style implementation.

**Example of Metrics Gathered in the Process**

<span style="white-space: nowrap;display: inline;">
<span style="float:left;"> 
    
| Metric           | My Implementation | AlexNet-like Implementation |
|------------------|-------------------|-----------------------------|
| AUC-ROC Micro    | 0.937165          | 0.935511                    |
| AUC-ROC Macro    | 0.938801          | 0.938398                    |
| AUC-ROC Weighted | 0.938728          | 0.938339                    |
    
</span>
    
<span style="float:left;"> 

My CNN| Implementation| _| _ | _
---|---|---|---|---
Class/Metric| precision| recall| f1-score | support
COVID-19|0.861963|0.737533|0.794908|381.000000
Other|0.727941|0.868421|0.792000|342.000000
Healthy|0.822857|0.797784|0.810127|361.000000
Accuracy|0.798893|0.798893|0.798893|0.798893
Macro avg|0.804254|0.801246|0.799012|1084.000000
Weighted avg|0.806656|0.798893|0.799059|1084.000000
</span>
<span style="float:left;display: inline;"> 
  

AlexNet| style|implementation|_ |_    
---|---|---|---|---    
Class/Metric| precision|recall|f1-score|support
COVID-19|0.823529|0.771654|0.796748|381.000000
Other|0.813456|0.777778|0.795217|342.000000
Healthy|0.787500|0.872576|0.827858|361.000000
Accuracy|0.807196|0.807196|0.807196|0.807196
Macro avg|0.808162|0.807336|0.806608|1084.000000
Weighted avg|0.808352|0.807196|0.806625|1084.000000

</span>
</span>



<br>
<h6><small>This work is based on the original study case project created by Group E for the term 3 A.I. students of Loyalist College (October 2023), in which I had the honor to participate.<br>
It is intended solely for educational purposes.
Please refer to the reference section.<br>
We do not have information about the source of the images, they are provided by the professor in moodle without credits, for that reason I am not making it available, just the code.</small></h6>
