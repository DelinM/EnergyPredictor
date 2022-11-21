![cover_photo](./readmefile/cover.png)
# EnergyPredictor
*Combination of a building's hourly energy consumption data and hourly weather information, EnergyPredictor predicts how changes in climate factors will impact a building's energy consumption, so that facility managers can making the best decisions among: 1. Do nothing! 2. Spend capital for upgrade and save downstream operational cost! 3. Suffer increased operational costs due to climate factors and only spend capital when required!*
<img src='https://github.com/DelinM/EnergyPredictor/blob/main/figures/TemperatureEnergyCostProfile3.png' width='25'>
# Background & a note to my engineering friends  
  *With the rise of tech industry, an increasing number of government agencies such as Toronto Water and York Region are considering or even starting to use machine learning and artificial intelligence to improve their engineering design and decision making capabilities.*
  
  *As a Professional Engineer working in engineering consulting, I notice that the consulting firms started to advertise themselves as ML/AI experts in solving the hardest engineering problems for a better future. I can confirm that it is possible that, with the help of leading consulting firms, the public sectors will be rich with ML within next 10 years. In fact, as far as I know, the most respectful engineers and managers with 15-30 years of practical experiences have been thinking and developing scenarios of where AI could be in play in traditional engineering field. The vision is crystal clear and cutting edging.*
  
  *However, I have to admit that to allow for this technical disruption comes to maturity, aside from master our own engineering specialization we as engineers need understand what is ML, how to use them, and most importantly, how to efficiently integrate ML into traditional engineering workflow and decision making processes. Just like process engineering or electrical engineering, ML, standalone, is a complex field. I feel lucky that as early as the winter of 2019, I started to learn coding to improve my engineering works. It has been some time and I developed extremely strong interest in coding and wanted to see how I can influence and convince more people to use it to better a traditional engineering world. I think that, if the industry has not been disrupted yet, I want to be that pusher and contributor to fuel the disruption.*
  
  *The intent of this small case study is to show what can be done using ML, and hopefully it will allow you to think outside of the engineering box. This example is related to asset management, engineering condition assessment, and engineering capital & maintenance decision making. Possible applicable examples:*
    *1. Use **Pump SCADA(Supervisory Control and Data Acquisition) data**, **Weather data**, **HVAC SCADA** and **Energy Consumption Data** to produce a optimized process and building mechanical control strategies for lower energy consumption.*
    *2. Use **Air Blower SCADA data**, **influent sewage SCADA data including flowrate and temperature**, **effluent SCADA data**, **weather information** to improve air blowers VFD (variable-frequency drive) efficiency.*
    *3. Better EA predictions combing public factors, human factors and engineering factors.*

# Data
Two data sets are used for the case study: building energy consumption and weather data set.

All energy consumption data used for the project come from BDG2 (Building Data Genome 2) data set. BDG 2 is an open data set that made up of 3,053 energy meters from 1636 buildings. The time range for the data set is two full years. The data set includes over 30 academic buildings located in Ottawa, Canada. A building is selected from the dataset as the case study subject.

The weather data of Ottawa is downloaded from Statistics Canada. Statistics Canada is the the national statistical office of Canada. It ensures Canadians have the key information on Canada's environment, society, and economy.

# Modeling
There are three ways that heat is transferred: conduction, convection, and radiation. Keep this key heat and mass transfer knowledge in mind, the following features are included for modelling after exploration data analysis:
**Air temperature**: temperature of air in degree Celsius (ºC)
**Cloud Coverage**: portion of the sky covered in clouds
**Dew Point**: the atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form.
**Building Footprint**: footprint of the building in square meters.



## 3. Data Cleaning 



## 4. EDA



## 5. Algorithms & Machine Learning

## 6. Which Dataset to choose?


## 7. Coldstart Threshold


## 7. Predictions


## 8. Future Improvements


## 9. Credits
