![cover_photo](./readmefile/Cover.png)
# EnergyPredictor
*Integrating the building's hourly energy consumption data and hourly weather information, EnergyPredictor predicts how changes in climate factors will impact a building's energy consumption, so that facility managers can making the best decisions among: 1. Do nothing! 2. Spend capital for upgrades and save downstream operational cost! 3. Only spend capital when required!*
<img src='https://github.com/DelinM/EnergyPredictor/blob/main/readmefile/Readme_1.png'>

# Background / Note to my Engineering Colleagues
  *With the rise of tech industry, an increasing number of government agencies such as Toronto Water and York Region are considering or even starting to use machine learning and artificial intelligence to improve their engineering design and decision making capabilities.*
  
  *As a Professional Engineer working in engineering consulting, I notice that the consulting firms started to advertise themselves as ML/AI experts in solving the hardest engineering problems for a better future. I can confirm that it is possible that, with the help of leading consulting firms, the public sectors will be rich with ML applications. In fact, as far as I know, the most respectful engineers and managers with rich practical and business development experience have been thinking and developing scenarios of where AI could be in play in traditional engineering field. The vision is crystal clear and cutting edging.*
  
  *However, I have to admit that to allow for this technical disruption comes to maturity, aside from master our own engineering specialization we as engineers need understand what is ML, how to use them, and most importantly, how to efficiently integrate ML into traditional engineering workflow and decision making processes. Just like process engineering or electrical engineering, ML, standalone, is a complex field. I feel lucky that as early as the winter of 2019, I started to learn coding to improve my engineering works. It had been some time and I developed extremely strong interest in coding and wanted to see how I can influence and convince more people to use it to better a traditional engineering world. I think that, if the industry has not been disrupted yet, I want to be that pusher and contributor to fuel the disruption.*
  
  *The intent of this small case study is to show what can be done using ML, and hopefully it will allow you to think outside of the engineering box in your next engineering studies. This example is related to asset management, engineering condition assessment, and engineering capital & maintenance decision making. Possible applicable examples:*
- *Use **Pump SCADA(Supervisory Control and Data Acquisition) data**, **Weather data**, **HVAC(Heating, ventilation, and air conditioning) SCADA** and **Energy Consumption Data** to produce a optimized process and building mechanical control strategies for a lower energy consumption.*
- *Use **Air Blower SCADA data**, **influent sewage SCADA data including flowrate and temperature**, **effluent SCADA data**, **weather information** to improve air blowers VFDs (variable-frequency drives) efficiency.*
- *Better EA predictions combing public factors, human factors and engineering factors.*

# Data
Two data sets are used for the case study: building energy consumption and weather data set.

All energy consumption data used for the project come from BDG2 (Building Data Genome 2) data set. BDG 2 is an open data set that made up of 3,053 energy meters from 1636 buildings. The time range for the data set is two full years. The data set includes over 30 academic buildings located in Ottawa, Canada. A building is selected from the dataset as the case study subject.

The weather data of Ottawa is downloaded from Statistics Canada. Statistics Canada is the the national statistical office of Canada. It ensures Canadians have the key information on Canada's environment, society, and economy.

# Modeling
There are three ways that heat is transferred: conduction, convection, and radiation. Keep the key heat and mass transfer knowledge in mind, the following features are included for modelling after exploration data analysis:
**Air temperature**: temperature of air in degree Celsius (ºC)
**Cloud Coverage**: portion of the sky covered in clouds. Radiation of heat.
**Dew Point**: the atmospheric temperature (varying according to pressure and humidity) below which water droplets begin to condense and dew can form.
**Wind Direction**: direction of the wind
**Wind Speed**: speed of wind. Convection of heat.
**Building Footprint**: footprint of the building in square meters. Convection and conduction of heat.
**Hour**: hour during the day. Typically the energy consumption is way lower at night.
**Weekday**: day of the week. Public facilities, for instance, are closed over the weekend so less energy consumption would be expected.
**Month**: month of the year.
**Sea Level Pressure**: air pressure. An indicator of weather systems at surface.
**Meter Readings**: hourly building energy consumption data.
The correlations of the features are shown below. Note that the correlations varies based on seasonal change. Discussions are included in the Jupyter notebook.
<p align="center" width="100%">
<img src='https://github.com/DelinM/EnergyPredictor/blob/main/readmefile/Readme_2.png'>

The data are split into training and test data sets. Three machine learning models are used for preliminary model selection: linear regression, random forest, LightGBM. Strategies such as cross validation, grid search, and random search hyperparameter turning are used to find the best dataset. As a result, random forest model is selected as the best model with the lowest error and highest accuracy.
<img src='https://github.com/DelinM/EnergyPredictor/blob/main/readmefile/Readme_3.png'>


# Scenarios
For a academic facility, how would annual energy expenditure change under the following scenarios:

  1. Average annual temperature **increase** by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.
  2. Average annual temperature **decrease** by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.
  3. Average annual temperature **increase only in spring and summer, and decrease in fall and winter by 0.2 degree, 0.4 degree, 0.8 degree, 1.2 degrees, 1.8 degrees, 3 degrees, 5 degrees, 10 degrees, and 15 degrees.


# Results
1. Scenario 1 - Annual Temperature Increase: the model shows that average annual temperature increase will result in **a lower energy use intensity** and **a lower energy cost**. For instance, when annual average temperature increase by 0.4°C, the annual energy cost will decrease by $1.0k.
2. Scenario 2 - Annual Temperature Decrease: the model shows that average annual temperature decrease will result in **a higher energy use intensity** and **a higher energy cost** for the target building.For instance, when annual average temperature decreased by 0.4°C, the annual energy cost will increase by $1.2k.
3. Scenario 3 - Temperature change by Seasons: The modeled temperature condition is closer to reality: when we have hotter summer and colder winters. The colder the winter, the more energy will be consumed to maintain the building temperature. For instance, when the annual temperature varies by 0.4°C, the annual energy cost will increase $1.7k.

# Next Steps
1. Use ARIMA combining with Random Forest Model to achieve better result.
2. If possible, apply similar models to the facilities where energy cost would be a main cost driver.
