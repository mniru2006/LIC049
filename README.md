## Experiment 1
### Design 1: Simulation of CS Amplifier
### Aim
Simulate the DC analysis, Transient, and AC analysis of a CS amplifier circuit using LTSpice.
### Circuit
![Screenshot 2025-02-17 185656](https://github.com/user-attachments/assets/c8b81451-b11b-4c01-b3e3-c2bcb4996010)


### Procedure

1. Design the CS amplifier circuit.
2. Naming the NMOS as CMOSN.
3. DC Analysis:Apply the DC voltage of  V<sub>DD</sub> = 1.8 V and V<sub>GS</sub> = 0.9 V . In LTSpice, go to the Simulate option and select Edit Simulation Command.Click on DC Analysis, then press OK.Click on Run in the tab menu to obtain the DC operating point V<sub>out</sub> .Set the Length as constant and determine the Width such that I<sub>D</sub> = 55.1 uA .

4. Transient Analysis:Modify the  V<sub>GS</sub> voltage source to a sine wave input with:
     - DC level= 0.9 V 
     - Amplitude= 50 mV 
     - Frequency= 1 kHz 
     
     In LTSpice, go to Edit Simulation Command, select Transient Analysis. Set the Stop Time as 5ms, then click OK.

5. AC Analysis:In Edit Simulation Command, select AC Analysis.Set the Type of Sweep to Decade.Set Points per Decade to 10.Set the Frequency Range from 0.1 Hz to 1 THz.Click OK. Determine the gain and frequency response of the circuit.

### Calculation

Power Calculation
 P = 100 uW

Drain Equation
V<sub>DD</sub> = V<sub>DS</sub> + I<sub>D</sub>*R<sub>D</sub> 

 P = I*V

Given: I<sub>D</sub> = 55.5 uA, V<sub>DD</sub> = 1.8 V 

Thus V<sub>DS</sub> = V<sub>out</sub> 

R<sub>d</sub>=32.4 Kohm ,but used 10 Kohm

Length= 3um

Width=5.6 um(Found by keeping the Length constant).

V<sub>DS</sub>=1.24 V

Q point is (1.24 V,55.1 uA)

## Results:
1.**DC Analysis:**
![Screenshot 2025-02-17 191224](https://github.com/user-attachments/assets/a75c930d-d7b7-43b9-b8bc-64411c7da395)


drain current I<sub>d</sub>=55.1 uA
V<sub>out</sub>=1.24 V \
Width=5.6 um for length=3 nm\

2.**Transient Analysis:**
![Screenshot 2025-02-17 191617](https://github.com/user-attachments/assets/557622e4-b5b9-4311-9b97-b7b82261a0e7)

There is 180 degree phase shift between input and output 

3.**AC Analysis:**
![Screenshot 2025-02-17 192428](https://github.com/user-attachments/assets/40031f4b-ceb1-45ca-9617-84175b0a36ca)


Gain=21 dB

## Inference:
1.The Width of the MOSFET directly effects the Drain durrent.\
2.By changing the dimensions of the MOSFET we can directly control the amount of Drain current.\
3.180 degree phase shift between the input and output waveform.\
4.The CS amplifier has larger gain =21dB.(ie, the ouput signal is 21 times larger then the input signal)\

### Design 2: Simulation of CMOS Amplifier
### Aim
Simulate the DC analysis, Transient, and AC analysis of a CMOS amplifier circuit using LTSpice.
### Circuit
![image](https://github.com/user-attachments/assets/b734acc2-6c81-4490-8094-b516ecb1fb92)

### Procedure

1. Design the CMOS amplifier circuit.
2. Naming the NMOS as CMOSN and PMOS as CMOSP.
3. Apply the DC voltage of  V<sub>DD</sub> = 1.8 V
4. DC sweep Analysis: Go to the edit simulation command and select the DC sweep option and choose:
 -Source name= V<sub>3</sub>.
 -type of Sweep= Linear.
 -start value=0,
 -stop value =V<sub>DD</sub>=1.8 V.
 -increment=0.1.

find the V<sub>in</sub> from the vtc curve  
5. DC Analysis:put the appropriate V<sub>in</sub> value. go to the Simulate option and select Edit Simulation Command.Click on DC Analysis, then press OK.Click on Run in the tab menu to obtain the DC operating point V<sub>out</sub> .Set the Length as constant and determine the Width such that I<sub>D</sub> = 55.4uA .

6. Transient Analysis:Modify the  V<sub>in</sub> voltage source to a sine wave input with:
     - DC level= 0.9 V 
     - Amplitude= 50 mV 
     - Frequency= 1 kHz 
     
     In LTSpice, go to Edit Simulation Command, select Transient Analysis. Set the Stop Time as 5ms, then click OK.
7. AC Analysis:In Edit Simulation Command, select AC Analysis.Set the Type of Sweep to Decade.Set Points per Decade to 10.Set the Frequency Range from 0.1 Hz to 1 THz.Click OK. Determine the gain and frequency response of the circuit.

### Calculation

 I<sub>D</sub> = 55.4 uA, V<sub>DD</sub> = 1.8 V 

Length M1= 3 um\
Width= 5.6 um(found by keeping the Length of M1 constant)\
Length M2= 3 um\
Width= 5.6 um(found by keeping the Length of M2 constant)\

## Results:
1.**DC Sweep Analysis:**
![image](https://github.com/user-attachments/assets/52aec740-6f43-412a-9922-38a3bbd4fbff)

 the value of the V<sub>in</sub> is selected as 0.8V as it is present in the middle of the saturation region of the VTC Curve.\
2.**DC Analysis:**
![image](https://github.com/user-attachments/assets/8bbc6ae0-f633-4ef3-97ab-3d0fdba93a5f)

drain current I<sub>d</sub>=55.3 uA
V<sub>out</sub>=1.52 V \
Length M1= 5.6 um,Width= 3um for M1.\
Length M2= 5.6 um,Width= 3um for M2.\


3.**Transient Analysis:**
![image](https://github.com/user-attachments/assets/2e7e7191-eeb9-41d2-8ab7-e493947335f2)

There is 180 degree phase shift between input and output 

4.**AC Analysis:**

![image](https://github.com/user-attachments/assets/f8338e45-919f-46b6-8a55-ffbfca5c8c68)

Gain=0.612 dB

## Inference:
1.The Width of the MOSFET directly effects the Drain durrent.\
2.By changing the dimensions of the MOSFET
 -M1 -when varying the width of PMOS there is not a lot of change in the drain current(ie, I<sub>d</sub> doesn't get effected much).\
 -M2 -when varying the width of NMOS there is drastic change in the drain current.\
3.If width is increased it leads to a higher gain
4.180 degree phase shift between the input and output waveform.\
5.The CMOS amplifier has gain =5.5 dB.(ie, the ouput signal is almost 6 times larger then the input signal)\
