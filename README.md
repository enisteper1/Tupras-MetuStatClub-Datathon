<h1 align="center">
TUPRAS METUSTATSCLUB DATATHON
</h1>
<p align="center">
<img src="https://user-images.githubusercontent.com/45767042/161608520-8f38965e-afd2-4bbd-a44f-5a03af72ee2e.png">
</p>

Petroleum refineries use a variety of physical and chemical processes to transform crude oil into products including gasoline, jet fuel, LPG kerosene and diesel.

The refinery uses process and laboratory metrics to control unit operations. Critical metrics that determine refinery profitability are estimated using process and laboratory variables from production. Due to operating limitations in the Plant-X unit of our ABC Refinery, D measurement (Conversion Rate) may only be measured once a day. As a result of this circumstance, operational interventions to improve product efficiency are not being carried out successfully in the units that have a direct impact on profitability.

To put everything in a nutshell, o predict D conversion rate we will follow steps that are given below.

1. First Look to Data
2. Data Visualization & Preprocessing
3. Feature Engineering
4. Train & Evaluation

Note: This project based on real life data and because of privacy policy data is not published with notebook. In addition, notebook is updated to improve succes rate and visualization of the project.

## 1. First Look to Data

The data set is encoded to preserve privacy policy. Brief information of features:

1. **Y1** 1st Zone Temperature Process Difference Value
2. **Y2** 2nd Zone Temperature Process Difference Value
3. **E1** Element_1 Laboratory Measurement
4. **E2** Element_2 Laboratory Measurement
5. **A1** A Chemical Flow Rate
6. **Y3** 3rd Zone Temperature Process Difference Value
7. **Y4** 4th Zone Temperature Process Difference Value
8. **Y5** 5th Zone Temperature Process Difference Value
9. **Y6** 6th Zone Temperature Process Difference Value
10. **U1** Product Density
11. **U2** Product Flow Rate
12. **O1** Chemical Flow Rate
13. **O2** Chemical Flow Rate
14. **D** Conversion Ratio (Target)

<h3 align=center> NaN Value Visualization </h3>
<img src="https://user-images.githubusercontent.com/45767042/161611333-8adb59a8-f1fb-412c-b8db-3bd4f3d699bf.png">

## 2. Data Preprocessing & Visualization

In this section, wrongly encoded datetime values are cleaned and data is shifted from 29 Feb 2015 because 29 Feb is not happened at 2015. Additionally, some outliers on output are eliminated.

<img src="https://user-images.githubusercontent.com/45767042/161612186-760778ca-5443-4249-82ee-f69b7c9154bc.png">


## 3. Feature Engineering

Because of data is encoded we are not able to obtain any information except their definitions. That is why, features are generated and tested if they are improving the success rate on test data or not.

At first, season data is generated from months. It may affect data since different seasons have different average temperatures and weather conditions. Y values were representing different temperature difference process values at same refinery. That is why all of their differences are summed to obtain total temperature difference process value per hour. Because of different chemicals thats flow may combined at one section or they may be flow from same pipes, their ratios with respect to each other are obtained.

<img width=1080 height= 720 src="https://user-images.githubusercontent.com/45767042/161612912-d8c736e9-9220-43ab-b375-924c4f75d78d.png">

## 4. Train & Evaluation

Different regression algorithms are tried to find the best solution for the problem. Their results will be compared with different metrics. These metrics are:
* Explained Variance Score
* Maximum Error
* Mean Absolute Error
* Mean Squared Error
* Median Absolute Error
* R2 Score


<img src="https://user-images.githubusercontent.com/45767042/161613635-aa471e42-2cc5-4f83-a86b-c91b8648ce25.png">


