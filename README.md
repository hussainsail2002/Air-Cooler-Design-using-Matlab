# Air-Cooler-Design-using-Matlab
Air Cooler Design For Arizona (Psychrometrics)


Introduction
Psychrometry:

Before jumping into the design of an evaporative cooler let us first understand the idea of Psychrometry which is the thermodynamics of atmospheric air or to be more precise it is the study of air-water vapor mixtures. In our study the mixture will be binary, meaning that only air and water vapor will be considered as parts of the mixture. One of the most fascinating aspects about psychrometry and about this mixture is that we can control its properties by making adjustments to them. This ability to control its properties has given rise to many interesting products, one such product being Air-coolers also known as swamp coolers. Let us understand few of the properties of Psychrometry:
	Dry Bulb temperature: This simply means the current temperature of the environment when measured with a thermometer. The word dry bulb means that we keep the bulb of the thermometer dry and measure the temperature of the atmosphere at the current state.
	Wet Bulb temperature: If you were to cover the bulb of the thermometer with a wet cloth and sling it around in the air, the temperature that you will read will be the wet bulb temperature. This temperature will usually be lower than dry bulb because of the loss of heat during evaporation. The wet bulb temperature will be useful when designing our evaporative cooler.
 


![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/3ccb29a3-97f7-4b56-bdce-d50d5ca82c09)







Humidity Ratio: This ratio measures the amount of water that is present in the air per unit of air on a mass basis it can be measured as grams of water vapor / kilogram of air or Kilogram of water vapor per kilogram of air. The Humidity ratio can also be written in terms of partial pressures of water vapor and air. The equation below will help us understand:
                                                          ω_(1 ) = 0.622  P_v1/P_a1                 	                        	  (1)
	
 Relative Humidity: As the name suggests this is the amount of water vapor that the air is holding at a given temperature to the maximum amount of water vapor that the air can hold at that particular temperature. As the temperature increases the capacity of air to hold water vapor also increases. The relative humidity plays an important role in the design of the evaporative cooler.
	Dew Point Temperature: If the pressure is to be maintained constant and the temperature is decreased. The lowest temperature that can hold 100% relative humidity or maximum amount of water vapor in the air. If the air were to be cooled any further, the water in the air will start to condense and come out of the air in the liquid form.
There are a few more important parameters such Specific Volume, Enthalpy etc. as these are not covered in the project calculations to the required depth.
ASHRAE Standards
Another important aspect to discuss are the standards set by international organizations such as ASHRAE. ASHRAE has set standards on the temperatures and humidity levels that are required for cooling and comfort. The average temperature for human comfort varies from 72 F to 80 F and the Relative humidity (RH) varies from 30% to 60%. If the RH were to fall below 30% it would cause irritation and uneasiness to the human body and if the RH were to raise above 60% then that would cause molds and other fungus growth in the house hold. In this project we will target to maintain a constant RH of 45%. 
Evaporative Coolers:
In this project we will need to design an Evaporative cooler for a house in Arizona. To do this we will dive into the working of such a device. 
Evaporative coolers work on the principle of Psychrometry, it is a device that makes a trade between temperature and RH. It takes in hot air with low RH and gives out cool air with higher RH. This is exactly what we need for human comfort! Another great advantage of Evaporative coolers is that it has a low running cost as it does not have a compressor sucking a lot of energy. It uses a simple blower/fan and a water pump.
Some of the down sides though are that they can only work in areas that have low RH, if the RH is higher that 60% it does not make sense to add more humidity to the air. It also requires more frequent maintenance as there is a lot of water movement inside the machine and the water pads will also need frequent changes
Arizona being a desert has very low RH and very high temperatures during the summer and this makes it a good location for using Evaporative coolers. 
Analysis
Air Changes: 
When using an evaporative cooler or air cooler we have the advantage of using more fresh air than compared to a vapor compression air conditioning system. It is recommended to have at least 20 to 40 air changes per hour. This will pump in more fresh air and will also be helpful to regulate the temperature as we will see in the coming sections.
The area of our room is given as 300 Sq-ft and we will assume that the height of the room will be 9 feet. This gives a volume of 2700 cubic feet. If we require 20 air changes in an hour then the volume will be come 54,000 cubic feet per hour. Diving this value by 60 will give us 900 which is the cubic feet per minute required from our fan/blower. As we will run the fan at different modes, we will be able to give different temperature output to the user. We will choose 3 modes first one will have 20 air changes second mode will have 30 air changes and final mode will have 40 air changes. This means that fan will need a capacity from 900 CFM to 1800 CFM.   

Mass and Energy balance:
As the Evaporative cooler is a thermodynamic device it is important to analyze the system from the first principles standpoint. We will take a look at the mass and energy balance of the system, these equations will also help us to write the MATLAB /automation code that control such devices!
We will need to follow the basic principles of thermodynamics and the mass balancing helps us understand the amount of water getting evaporated into the system.
The mass of air from the inlet to the exit remain constant. The mass of vapor will increase as we are adding water to the incoming air and increasing its relative humidity.
Mass Balance: 
                                                                         m_v1  + m_w  = m_v2                                                     (2)
                                                                         m_a1= m_a2                                                                    (3)

Where,
m_v1  is the mass of water vapor in the incoming ambient air
m_w  is the mass of water added by the Evaporative cooler to the incoming air
m_v2  is the mass of water vapour in the air exiting the Evaporative cooler and entering the house
Although the air exiting the 
Energy balance:
                                       m_a2 h_a2+m_v2 h_g2  = m_a1 h_a1+m_v1 h_g1  + m_w h_f                                    (4)

Where,
h_a2,h_a1,h_g2,h_g1 and h_f can be found from the Ideal air and Water vapor tables at the respective temperatures.
The energy balance is arrived at this form when we consider that there is no heat exchange the takes place and no work is done by or on the system and Kinetic and potential energy is taken as negligible.
 Psychrometric charts are also useful for analyzing data that we get from the conditions around us. If we know at least two data points, then we can plot the remaining properties. 
Evaporation rate:
A very important factor that does not get covered is the evaporation rate. To design an evaporative cooler, it is imperative to know how much water will be evaporated from the pads that hold the water. These pads can be made of many different materials and the most common one is cellulose. By calculating the effective area that is available and the speed at which the air flows over the pad we will be able to calculate the mass of water that is evaporated into the moving stream of air. As evaporation rates and their factors do not come under the scope of the current topics we will not be using these factors to design the evaporative cooler. Rather we will be making certain assumptions to arrive at the design considerations.
Schematic Diagram:
 
Figure 2:Schematic Diagram of an Evaporative cooler

![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/0b6c045b-a21c-4fee-9474-a8c433d69492)


Operating principle:
The Thermodynamic process is a simultaneous heat and mass transfer or adiabatic cooling and follows a constant enthalpy line on the psychrometric chart. Since the deviation of the constant wet-bulb line and constant enthalpy line is small, it is assumed that the wet-bulb temperature is constant across the evaporative stage.






![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/e12d2782-0fbd-4ea9-95e3-158e9b8331e3)










Using the above principle of maintaining the wet bulb temperature constant let us look at a practical problem of finding the output temperature and also the amount of water absorbed to reach the required temperature and relative humidity.
We make the following further assumptions in our calculations. 
	The Relative humidity of the exit air will be 45% when the fan runs at 1350 CFM and then we calculate the mass of water evaporated. By changing the fan speed we can achieve a ± 10 % relative humidity temperature difference by using the higher end and lower end CFM values.
	As mentioned earlier we assume that the wet-bulb temperature will be constant.
	The pressure inside and outside the room will be at a constant 1 atm.
As we are working on designing a evaporative cooler for the Arizona region we will need to find the temperatures and relative humidity for Arizona. The temperature and humidity data were taken from timeanddate.com. the data was captured for the three months of May, June and July.

![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/6f4c8b94-7118-492e-b8dc-1705bf730630)

Figure 4: Temperature data for Arizona during Summer 2022

![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/ea2286f6-cd2e-4291-ad4c-79a187b05af3)

Figure 5: Relative Humidity for Arizona during Summer 2022
The temperature of the water that is stored on the pads will be the wet bulb temperature. The wet bulb temperature can be extrapolated from the dry bulb temperature and the relative humidity of the air. 


![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/f595f17d-87e7-48ac-b7c3-abd8decb4ab5)

 
Figure 6:Wet bulb Temperature during summer 2022

The user has 3 modes to vary the temperature of the room, this is done by varying the fan speed. By increasing the fan speed and spraying a greater amount of water into the air. This will cause an increase in the relative humidity but will decrease the temperature further.
As we know the input Temperature and RH we are able to locate the other properties from the Psychrometric table. We calculate the mass flow rate for 30 air changes and assume the output RH will target 45% based on which we can calculate the Humidity ratio and the mass of water vapor in the air. Once we find the mass of water vapor we can subtract from the initial water vapor mass and find the amount of water absorbed from the evaporative cooler. We again assume that the RH at the higher and lower fan speed will vary by ± 10 % and we can calculate the amount of water absorbed by the moving air once we know the input and out put conditions. On an average the amount of water absorbed can be seen below in the graph

![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/cf22ce98-d4b8-4349-866c-013c48393d51)

Figure 7: Mass of Water added by the Evaporative cooler

The temperature range that the cooler can operate within is dependent on the ambient temperature and humidity. The lower RH values will signify lower wet bulb temperatures which will in turn be helpful for decreasing the temperature and also the ambient ai will be able easily absorb the water as the RH is low.
An important for evaporative coolers are the effectiveness, this is the ration of the difference between the inlet and exit temperatures and the inlet and wet bulb temperatures. The wet bulb temperature is the temperature that will be reached if the air is 100% saturated with water vapor. 

E=( T_(db-Inlet)  -  T_(db-Outlet))/(T_(db-Inlet )  -  T_wb  )  x 100
Where,
T_(db-Inlet)  is the inlet dry bulb temperature
T_(db-Outlet)  is the exit dry bulb temperature
T_wb  is the wet bulb temperature of the ambient air
Conclusion
One of the major inferences that we can make during the study is that the Relative humidity of the ambient air makes a great difference in the effectiveness of an evaporative cooler. The graphs below show that during a spike in the relative humidity, there is a sharp drop in the temperature variation and a drop in evaporator effectiveness


![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/eb311b96-ab70-4bb0-b2b3-3ffbcbc1b3f9)


Figure 8: Exit Temperature Range shown with Ambient air conditions





![image](https://github.com/hussainsail2002/Air-Cooler-Design-using-Matlab/assets/32453875/ea65ab5d-cbbe-4cc9-ac3a-23e11bd7a42c)



 
Figure 9: Effectiveness of the evaporator with Ambient air conditions

It can be seen that the highest effectiveness of the cooler is reached when the RH is at the lowest and the lowest effectiveness is reached when the RH is at the highest point. This follows the thermodynamic laws as when the air is dry it can easily absorb more moisture and water from its surroundings and hence decrease its temperature by a greater extent than if the air was already carrying more water.
The temperature values are indicated in degree Celsius and the mass of water is shown in Kg per hour. 
The mass of water is also estimated to be 18 liters per hour during the peak temperatures. Approximating it to require 144 liters per day. The Fan sizing has been chosen based on the size of the room and number of air changes that are required
Looking forward (Two Stage Evaporative Coolers):
Evaporative coolers greatest advantage is the cost factor, it makes air conditioning relatively inexpensive and saving power. The major downside though is that it works only in dry conditions. To tackle this issue, HVAC engineers have used innovative ways to come up with two stage and three stage evaporative coolers that can use both Refrigerants and also make use of the natural evaporation cooling. This gives the best of both worlds and helps us save cost.
  








