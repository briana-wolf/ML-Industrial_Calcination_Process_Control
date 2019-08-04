# Machine Learning Problem: Industrial Calcination Process Control
# Objective
In the mineral processing the calcination step improves an important property of the mineral which we have called PV. In order to control this property, operators have numerous levers to modify. The amount of time it is 
In this project I assess the feasibility of using supervised machine learning to determine for this multi-variate control problem. 

# Data
Data contains lab results from kiln discharge samples in a mineral calcincation process. Data uploaded here is a modified data set for demonstration purposes. 

Fields
 * Lab Analysis data was exported from LIMS for samples collected by the operators and send to the lab for analysis  
  * Sample time listed may not be actual 
  * PV is the sample variable measured, the target that we would like to control
  * Comp1 and Comp2 are also lab measured properties on the kiln discharge samples. Composition also impacts PV and is controlled by upstream processing steps and is not affected by the calcination process
 * Kiln control variables are tracked in the PI data historian. Values have been loaded as an average of the 2 hours given the ~2 hr residence time. Variables include the following:
  * Time Start in Kiln is time estimated that 
  * Kiln Rotation and Kiln Gas are parameters that the operator adjusts to control PV. The ML algorith would control these 
  * Other parameters such as kiln feed rate and feed bin height affect the process except these are not typically adjusted to control PV but rather to balance the process. Could be considered but not 

# Analysis Files
Analysis is performed in python with Jupyter notebooks. 
Data cleaning. 
* Machine learning notebook
* Charts to show if 

# Conclusions
There are quite a few challenges with this data set. 

* Tracability is difficult. Better data with exact time 
* Quantity of data 
* The PV test itself can have variability

