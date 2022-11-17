
Raspberry Pi is the name of a series of single-board computers made by the Raspberry Pi Foundation. The Raspberry Pi is a very cheap computer that runs Linux, but it also provides a set of GPIO (general purpose input/output) pins, allowing you to control electronic components for physical computing and explore the Internet of Things (IoT). We are using it as a solution to automate testing process at industry level. It will be connected to local area network and can be operated remotely.

## ANN
![[Assets/Pasted image 20221115213231.png]]

## **Implementation**

### Better Processing 

- Dataset consist of 10 files of faulty gearbox data and healthy gearbox data each at different load percentage. Each of these files has different number of data points because of the different time length of experiment. Hence, to make each load percentage experiment data of same length, we need to bring all the dataset at the same dimension. Hence, this function will select first **88200** datapoints from each file. As it is perfectly divisible 300 and none file had lesser amount of data points. 
- The shape of the dataset after trimming is $(1764000, 7)$. The dataset shall be separate on the basis of fault, i.e. "Healthy" or "Broken". From this data, we have to create feature which shall be used to train our machine learning algorithms to predict the type of fault.
1. FFT : - FFT function is to convert a signal from time domain to frequency domain. This function takes an pandas Dataframe as an input argument and spit out an absolute value of FFT in Pandas Dataframe format.![[Assets/Pasted image 20221115114917.png]]

2. Arrange Dataframe : - This function is used to rearrange the the RMS values of frequency of each sensor and rename the columns depending upon the frequency number (ranging from 1 to 15 Hz).
3. RMS : - This function is responsible to take the RMS values of all the datapoint lies in the frequency bin of a single frequency. In this setting, each bin contains 10 datapoints.

Using above mentioned functions we create the features for the given dataset. As an output, we get 60 features, 15 for each sensors.
The logic of the function is:-
- Separate the data on the basis of load_percentage (Load). Output should have **88200** rows.
- A subset of 300 datapoints from the separated dataset thus we get 294 chunks of subset.
- This subset of dataset is used for FFT.

### Logistic Regression

Logistic regression is a statistical method used to predict the outcome of a dependent variable based on previous observations. It's a type of regression analysis and is a commonly used algorithm for solving binary classification problems. Logistic regression is a classification algorithm that predicts a binary outcome based on a series of independent variables. For our problem we have two possible outcomes "Healthy" or "Broken". Logistic regression works by measuring the relationship between the dependent variable (what we want to predict) and one or more independent variables (the features). 

We used the processes data (mentioned above) and applied Logistic Regression to train the classifier. 
![[Assets/Pasted image 20221115105714.png]]
Figure : Confusion Matrix

The accuracy of the model is **100%** but we can't always say that as the input database was not that big but in our test it worked every time.

Raspberry PI 

Mechanical and manufacturing engineering has changed over time, adopting some of the most cutting-edge, cutting-edge technology. Artificial intelligence and robotics have had a significant impact on how some crucial procedures are carried out. With the development of new microcontrollers and computer vision algorithms, quality testing has dramatically improved. It can automatically categorise and distinguish between functional and nonfunctional items.

As our project also included implementation on Raspberry PI. We saved our model into a file to be used in RPI. We created a flask server to run in local area network. Flask is a micro web framework written in Python.  It has no database abstraction layer, form validation, or any other components where pre-existing third-party libraries provide common functions. Created a route to get data from request and use the data to predict the result.

Example Input:
```python
  "a1":[-10.8023,13.9087,6.37438,-15.2817,3.13954,0.677448,-10.5754,-4.03329,1.86867,7.58148],
  "a2":[-5.15393,7.88091,-3.59342,3.73856,6.8219,-3.23441,7.7254,2.57692,-5.0894,6.20596],
  "a3":[6.84189,-2.98886,0.590603,4.00437,-2.92981,-1.72599,-2.18401,1.46843,5.34229,-6.12133],
  "a4":[-3.60985,6.41759,2.61505,1.52184,1.55903,-3.14302,2.56965,2.72891,-1.36563,11.5483],
  "load": [90,90,90,90,90,90,90,90,90,90]
```

As the model was trained on 300 samples we need to provide at least 300 samples to get accurate result. The result will be either "Healthy" or "Broken".  
![[Assets/Pasted image 20221115154741.png]]

### Discussion

In our research we talked about how the raw data is not always useful and how just some basic processing help us get verry good result and how we can use Fourier Transform to get more incites of data. From the finding we got the result that Neural networks are not alwasy the best choice sometime just  good processing and proper choice of method can help get better result and can save time. 
