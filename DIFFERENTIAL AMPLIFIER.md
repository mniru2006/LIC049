# Expeiment-3

## Aim:
Design and Analyze the MOS differential amplifier circuit for the following specifcations and Perform DC analysis,Transient Analysis,Frequency response and extract parmeter

VDD=2.2v,P<=2mW,Vicm=1.2v,Vocm=1.25v,Vp=0.4v

#### Differential Amplifier:

differential amplifiers  consist of two transistors M1 and M2, whose sources are joined together. If two transistor are connected to the different voltage input then there current across M1 and M2 are different due to gate voltage.If in case the voltage supply at gate terminal is same then the current through the M1 and M2 are same.This configuration is called "Common Mode input voltage differential Amplifier".WHatever may be the load resistor, the MOSFET M1 and M2 should not go to the Triode region. It should be verified that MOSFET should be in Saturation Region.

For all this circuit we need find out the AC analysis ,Transient analysis And Frequency Response.
# Circuit-1
Components Required: MOSFET(M1,M2 and M3), Resistor,voltage supply's 
![exp3c](https://github.com/user-attachments/assets/d254d715-429c-40fe-ad76-53cdb6b1f9e4)



Procedure :
Make the circuit connection as given above.
connect the resister at the source terminal of both mosfet 
now calculate the value of Iss as power and vdd is given
and calculate the Id1 and Id2 
now calculate the Rss and Rd 

Now to get the desired values of output voltage and current we have to vary the width and length of both the mosfet
we got L=1m and W=24.9m 
![image](https://github.com/user-attachments/assets/5128ccce-289b-476f-bed6-f8cbf9ea0d4c)







# DC analysis:


   To perform the DC analysis we have to select the {DC op pnt} in the edit simulation command and run the simulation
   the figure below is the values obtained from the DC analysis

![exp3dc](https://github.com/user-attachments/assets/eb2328a6-1fa5-475f-bcb9-ddac21edef72)


Here in dc analysis we got the vout as expected and id1 and id2 we got the same 


# Transient analysis:

  To perform transient analysis we have to select the transient analysis in the edit simulation
   and give the stop time as 5ms and run the simulation .
   and the graph velow shows the transient response of the design.

   ![Screenshot 2025-03-02 222413](https://github.com/user-attachments/assets/1816471b-f5af-4a2e-b683-e49322ad36f2)



# AC analysis:

   TO perform AC analysis we have to select the ac analysis in the edit simulation command given the values as shown below

   ![Screenshot 2025-02-17 184334](https://github.com/user-attachments/assets/b5b9b5b2-cc27-459c-87d9-27411895f901)
 

   ![1 4](https://github.com/user-attachments/assets/e38ceac5-13a9-46b8-ad3c-efeac570178f)





# Circuit-2:


Now replace the R3 resister with a current source :
connect a current souce of 1mA
![image](https://github.com/user-attachments/assets/904b40b3-b1dc-40ba-9d7b-0f6713e478bb)




# DC analysis:

  To perform the DC analysis we have to select the {DC op pnt} in the edit simulation command and run the simulation
   the figure below is the values obtained from the DC analysis

  ![image](https://github.com/user-attachments/assets/021268d1-be7a-4d12-959c-fb069852cd8c)




   # Trasient analysis:

  To perform transient analysis we have to select the transient analysis in the edit simulation
   and give the stop time as 5ms and run the simulation .
   and the graph velow shows the transient response of the design

   
   we have to give deg of 180deg to one mosfet and 0deg to the other mosfet
   and ac amplitude 1 for one mosfet and 0 for other mosfet
  ![Screenshot 2025-03-02 220014](https://github.com/user-attachments/assets/8e4c15d1-706e-42ee-b6fb-ee16e28983c4)




 # AC analysis:
 
  <img width="959" alt="image" src="https://github.com/user-attachments/assets/98ec35e3-cac9-41a6-b2cf-5384f4559b01" />




  # Circuit-3:

  Now replace the R3 resister with a Mosfet  :
    Given vp=0.4v and wkt vt=0.36v we got the gate voltage of the new mosfet as 0.76v 

  ![image](https://github.com/user-attachments/assets/4565061b-ac59-4f4f-8a9a-0582ed2c7403)


 To get the output voltage and vp and current desired value we have to 
 vary the width and length of the new mosfet
![image](https://github.com/user-attachments/assets/54c1b180-0ea5-4bac-92a3-9c99cb5d6795)



# DC analysis:
![image](https://github.com/user-attachments/assets/d0fd306c-8480-4ad2-ab36-49a8f5c2e282)


 # Transient analysis:
 give ac amplitude as 1 for one mosfet and 0 for other mosfet 

 ![image](https://github.com/user-attachments/assets/6251a343-ad89-4442-9c38-313acc5ca01d)


# AC analysis:
<img width="959" alt="image" src="https://github.com/user-attachments/assets/56a10839-f8b8-40e4-8c2f-a01d9dda29f3" />








  


   



   

   

   
