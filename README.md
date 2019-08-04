# Machine Learning Problem: Industrial Calcination Process Control
## Objective
In the processing of an industrial mineral, the calcination step determines an important mineral property which is identified as PV (process variable) for this project. In order to control the PV, operators have numerous levers that impact the kiln temperature and product flow through the kiln. Given the number of various input parameters that also affect PV as well as the lag in feedback on any adjustments, the calcination is not well controlled manually leading to out of specification product. In this project, the feasibility of using supervised machine learning to control kiln operation is assessed for this multi-variate control problem. 

## Data
Data uploaded here (KD - mod.xlsx) is a modified data set for demonstration purposes. 

 * Operators collect samples from the kiln discharge every ~2 hrs and send to the production lab for analysis. Results are entered into LIMS and have been exported to Excel for use here. This data contains the following fields:
  * Date is the date that the sample was entered into LIMS. 
  * The notes typically contains the sample time and this text field has been converted to a date. Sample time may not be very accuracy as operators may not take the sample right at the hourly scheduled time but the sample time is still recorded as such.
  * PV is the sample variable measured, the target property to be controlled
  * CompA and CompF are also lab measured properties on the kiln discharge samples. Composition also impacts PV and is controlled by upstream processing steps. It is not affected by the calcination process
 * Kiln control variables are tracked in the PI data historian. Values have been loaded as an average of the 1 hour time period prior to the sample given the ~1 hr residence time. Variables include the following:
  * Start Time Kiln is one hour prior to sample time
  * Kiln Rotation and Kiln Gas are parameters that the operator adjusts to control PV
  * Kiln Temperature is indirectly controlled by the gas rate and other material loading, moisture characteristics etc
  * Other parameters such as kiln feed rate and feed bin height also affect the calcination process. Similar to the composition, these parameters are not typically adjusted to control PV, but are rather a result of upstream processes. Such values could be incorporated as additional variables in the model as well.  

## Analysis Files
Analysis is performed in python with Jupyter notebooks. 
* Data exploration, modeling and model evaluation are performed in the Machine Learning Notebook
* Prior to implementing machine learning control, a manual step would be for operators to use multi-variate charts to determine kiln set points based on input parameters

## Conclusions
There are quite a few challenges with this data set. 
* Tracability is difficult with the ~1 hr residence time in the kiln. Properties of the calcination are assumed. This could be somewhat refined if the exact sample time were recorded instead of the hourly approximation. 
* Current process may be over controlled. Would learn better if variables were left and not adjusted. 
* Quantity of data is limited for PV and for composition
* The PV test itself has a relatively high variability

There is mild predictive power with the simple model demonstrated, but performance would improve with a more robust data set so that additional input parameters can be included. The model would then look at inputs from upstream properties and determine how to control the kiln. While the concept proves promising, data collection must be improved to further develop models for use. 
Upstream process control to eliminate feed variability into the kiln will always be preferred to these methods. 

