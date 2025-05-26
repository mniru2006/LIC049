# Monostable Multivibrator Using 555 Timer IC
### 1. AIM
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.

### 2. THEORY
The NE555 timer is a highly adaptable integrated circuit commonly used in various timing-based circuits. It functions in three main modes:

**Astable Mode**: The timer does not remain in any fixed state; it continuously oscillates between HIGH and LOW, generating a square wave output.

**Monostable Mode**: The timer stays in a single stable state (LOW) and generates a one-time output pulse when triggered by an external signal.

**Bistable Mode**: The timer maintains two stable states and switches between them based on external input signals.

In monostable mode, when a falling edge is detected on the Trigger (Trig) pin, the output switches to HIGH for a duration determined by an external resistor (R) and capacitor (C), then automatically returns to LOW.

The duration of the output pulse (T) is calculated using the formula:

T = 1.1 × R × C

Where:

R is the resistance in ohms (Ω)

C is the capacitance in farads (F)


### <ins>Key Features
Generates precise pulses of 0.5 milliseconds duration for each trigger input.
While the pulse is active, any additional triggers are ignored, making it non-retriggerable.
It can be triggered externally using digital signals or by another 555 timer configured in astable mode.
Commonly used in digital timing circuits, pulse generation tasks, and signal conditioning applications.

### 3. CIRCUIT DESIGN AND CALCULATION
![WhatsApp Image 2025-05-26 at 23 06 53_7db1124a](https://github.com/user-attachments/assets/b01bcb0f-209b-4182-8d78-ba66f8437bc0)


#### Target pulse width:
![WhatsApp Image 2025-05-26 at 23 26 18_1d6fd133](https://github.com/user-attachments/assets/c78344c8-b9cf-4e5f-a958-94de414e76af)



### 4. SIMULATION ANALYSIS
### <ins>Transient Analysis
Used to verify timing behaviour of the output signal in response to various trigger signals

### <ins>Procedure 
1) Launch LTspice and start a new schematic. Build the circuit according to the provided circuit diagram.

2) Choose the resistor (R) and capacitor (C) values based on the specified requirements.

To set up the simulation:

Navigate to Simulate → Edit Simulation Cmd

Select the Transient analysis option and specify the simulation time as required for the experiment.


### 5. OUTPUT WAVEFORMS AND RESULTS
### <ins>Case 1: Properly Spaced Triggers
- Trigger Pulse Source:
  VTrig PULSE(5 0 0.05m 0 0 0.01m 3m)

![image](https://github.com/user-attachments/assets/9685361c-cc9d-4168-94cb-698e2a820e78)


**Output Result**:
  -Every falling edge of the trigger signal activates the 555 timer.
  -The output voltage (VOUT) switches to HIGH for approximately 0.5 milliseconds with each trigger event.
  -As a result, multiple output pulses can be observed.


### 6. INFERENCE
- The 555 timer in monostable multivibrator mode successfully generates a precise 0.5 ms oulse in response to each valid falling-edge trigger.
- In **Case 1**, where the trigger pulse are well-spaced (every 2 ms), the circuit generates clean, distinct output pulses with accurate timing.
- In **Case 2**, where triggers occur faster than the pukse duration (every 0.2 ms), the timer ignores subsequent triggers during the HIGH output phase, demonstrating its **non-retriggerable** behaviour.
- The capacitor voltage waveform confirms correct charge and discharge behaviour during each phase cycle.
- Simulation results validate the theoretical design and show the circuit's reliabilityunder both slow and rapid triggering conditions.

### 7. CONCLUSION
The NE555 timer configured in monostable mode provides accurate, predictable timing pulses when triggered by clean falling edges. In this simulation, a 0.5 ms output pulse was reliably generated using selected resistor-capacitor values, and its response under different trigger scenarios was analysed. The circuit performs well in digital timimg applications and can be extended using external logic for automated triggering.

# Astable Multivibrator And Monostable Multivibrator Using 555 Timer ICs
### 1. AIM
Generate a waveform with pulse width of 0.5 ms under different trigger conditions using 555 timer IC.

### 2. THEORY
An Astable Multivibrator is a circuit that continuously oscillates between two unstable states on its own, without the need for any external trigger. It functions as a self-driven square wave generator, making it suitable for applications such as clocks, pulse generators, and frequency synthesizers.

The 555 timer IC is commonly used to build an astable multivibrator. In this configuration, the 555 operates by repeatedly charging and discharging a capacitor through resistors, producing a continuous square wave signal.

### <ins>Logic Structure Used
To achieve reliable and noise-free triggering of the monostable 555 timer, the following sequence of logic is implemented:

**Astable Multivibrator (Trigger Source)**: Generates continuous square wave pulses.

**Differentiator Circuit**: Transforms the edges of the square wave into sharp, narrow pulses.

**Clipper Circuit**: Filters the signal to allow only negative spikes to pass through, blocking the positive ones.

**Monostable Multivibrator (Main 555 Timer)**: Produces a fixed-duration output pulse (0.5 ms) in response to each valid trigger pulse.
   
### 3. WORKING PRINCIPLE OF THE ASTABLE MULTIVIBRATOR
### 1. Charging Phase:
- The capacitor charges via resistors R1 and R2.
- Once the voltage across the capacitor reaches two-thirds of the supply voltage (Vcc), the internal comparator activates and resets the flip-flop.
- As a result, the output switches to LOW.

### 2. Discharging Phase:
- The capacitor discharges solely through resistor R2 via pin 7.
- When the voltage across the capacitor falls to one-third of the supply voltage (Vcc), the internal comparator sets the flip-flop.
- This causes the output to go HIGH, and the cycle begins again.

This cycle of charging and discharging creates a continuous square wave.

### Output Characteristics:
- The oscillation frequency is determined by the values of R1, R2, and the capacitor C:

**Frequency** = 1.44 / ((R1 + 2 × R2) × C)

**Duty Cycle** = (R1 + R2) / (R1 + 2 × R2)


### 4. CIRCUIT DESIGN AND CALCULATION
### <ins> Calculations
### Astable Multivibrator
*ton = 0.69 (R1 + R2)C2*,   *toff = 0.69 x R1 x C2*

![WhatsApp Image 2025-05-26 at 23 53 58_44615058](https://github.com/user-attachments/assets/5a836706-de18-4a2b-af16-cb0beb9c763f)
![WhatsApp Image 2025-05-26 at 23 53 57_def090a4](https://github.com/user-attachments/assets/22e325ae-4f6c-476a-9490-cd8f64826c46)


### <ins>Circuit Diagram
![image](https://github.com/user-attachments/assets/d7b3b3ec-80f5-4761-ab49-e41ac0a8e9dd)


### 5. SIMULATION ANALYSIS
### <ins>Transient Analysis
It is used to examine the timing characteristics of the output signal when subjected to different trigger inputs.

### <ins>Procedure 
Launch LTspice and start a new schematic. Construct the circuit according to the provided diagram.
Determine appropriate resistor and capacitor values for the Astable section, Differentiator, Clipper, and Monostable blocks.
Observe and analyze the capacitor’s charging and discharging behavior over time.
To set up the simulation:

**Navigate to Simulate**→ Edit Simulation Cmd

Select the Transient option and enter the required simulation time based on the case.


### 6. OUTPUT WAVEFORMS AND RESULTS
## Waveform
### Case 1:
![image](https://github.com/user-attachments/assets/bdcbd7d8-b042-44d8-a02f-16989a367a90)

First wave is output of Astable Multivibrator, Second waveform is Output of Differentiator Circuit output, 3rd wave is the output of Negative Clipper circuit and fourth waveform is output of Monostable Multivibrator pulse width is 0.5ms.

### Case 2:
![image](https://github.com/user-attachments/assets/bb0dabe9-f63f-4be1-9e6b-fbbc78f23174)

First wave is output of Astable Multivibrator, Second waveform is Output of Differentiator Circuit output, 3rd wave is the output of Negative Clipper circuit and fourth waveform is output of Monostable Multivibrator pulse width is 0.5ms.
 cap value .1u

 ### Case 3:

 in case 3 the ton<toff which is not possible in astable Multivibrator , thus we can use an inverter to invert the pulse generated.
 
![image](https://github.com/user-attachments/assets/62330045-4a0a-422d-b977-9699a629bb00)


 ![image](https://github.com/user-attachments/assets/5974cd20-b140-48e9-b307-9e661e8e4906)



First wave is output of inverted Astable Multivibrator, Second waveform is Output of Differentiator Circuit output, 3rd wave is the output of Negative Clipper circuit and fourth waveform is output of Monostable Multivibrator pulse width is 0.5ms.




#### Transistor inverter circuit:

![image](https://github.com/user-attachments/assets/68467e1b-11da-4ff2-aa3f-8cb30a68d3c1)

### <ins>Output Waveforms

![image](https://github.com/user-attachments/assets/20bf1383-c7e0-41ae-8bf5-d7a9151dcd26)

**Output Result**:
  - Monostable is triggered at every 0.5 ms.
  - Monostable pulse width = 0.5 ms.
  - This results in continuous high output, as each new trigger occurs before previous monostable pulse finishes.
    
### 7. INFERENCE
- Controlling ON and OFF Times Can Be Tricky
While adjusting resistor and capacitor values allows control over how long the output remains HIGH or LOW, achieving specific timing values isn't always straightforward with the standard 555 timer configuration.

- The 555 Timer Has Certain Limitations
In some scenarios—such as when a longer OFF time is required compared to the ON time—the typical astable configuration of the 555 timer can't directly produce the desired result. That's why, in Case 3, an inverter was used to flip the signal.

- Using Inverters to Shape the Output
By adding a simple NOT gate (implemented with a transistor), we were able to invert the output signal, offering more flexibility to tailor the waveform to our needs.

- Short Duration Pulses Require Precision
In Case 2, we dealt with very brief pulses lasting only a fraction of a millisecond. This required the use of small resistor and capacitor values, highlighting the importance of precision and how component choice impacts the timing behavior.

- Edge Detection with a Differentiator
A differentiator circuit was used to detect the exact point where the signal transitions from LOW to HIGH. This method is effective when the goal is to respond only to the change, rather than to the entire pulse.

- Monostable 555 Produces Stable and Consistent Pulses
When triggered by those detected edges, the monostable 555 timer generated clean and consistent pulses. This is especially useful when a dependable output is needed, regardless of the input pulse width.



### 8. CONCLUSION
The experiment demonstrates that a 555 timer can be configured in both Astable and Monostable modes to generate and shape precise timing pulse. The combination of logic elements-differentiator, clipper and inverter-ensures clean and reliable triggering of the monostable multivibrator. The system is robust, versatile and suitable for a wide range of timing applications, including waveform generation, delay circuits and digital pulse shaping.

# Virtual Lab Simulation of Monostable Multivibrator
### 1. AIM
- To perform a Monostable Multivibrator using 555 Timer
- To observe and plot the Trigger Input Voltage.
- To observe and plot the Output Voltage.
- To observe and plot the Capacitance Voltage.

### 2. PROCEDURE
1. Connect the components as mentioned below:
L1-L12, L14-L12, L16-L12, L4-L9, L8-L9, L9-L10, L3-L17, L11-L13, L7-L11, L6-L13, L5-L15.(For eg. click on 1 and then drag to 12 and so on.)
2. Click on 'Check Connection' button to check the connections.
If connected wrong, click on the wrong connection. Else click on 'Delete all connection' button to erase all the connections.
3. Intially set R a=10 kΩ, C=1 µf, Vcc=5 V, Tin = 20 msec.
4. Click on "Calculate" button.
5. Now note the output voltage.
5. Click on "Plot" button to plot, Trigger Input Voltage, Output Voltage, Capacitance Voltage
6. Click on "Clear" button to clear the data.
7. Repeat the experiment for another set of resistance value and capacitance value.
8. Set the Resistance (R a) value (1 kΩ - 10 kΩ).
9. Set the Capacitance (C) value .
10. Set supply voltage (Vcc).


### 3. CIRCUIT DIAGRAM

![Screenshot 2025-05-21 220423](https://github.com/user-attachments/assets/a4eb0e00-9dff-442b-862d-c2406f4e2ff4)

### <ins>Output Waveforms
#### Trigger Input Voltage

![image](https://github.com/user-attachments/assets/6d6ccfc7-9d76-4d5a-a3e3-14b32460d009)

#### Output Voltage

![image](https://github.com/user-attachments/assets/e31368af-5f61-45b5-84d3-05d6090ad213)

#### Capacitor Voltage

![image](https://github.com/user-attachments/assets/8bec8876-7cee-4575-aef3-9e4e60491a70)

# Simulation in Virtual Lab Astable Multivibrator
## Procedure:
1) Connect the components as follows: L1 to L12, L14 to L12, L16 to L12, L4 to L9, L8 to L9, L10 to L19, L3 to L17, L11 to L13, L7 to L19, L6 to L13, L2 to L13, L5 to L15, and L18 to L9. (For example, click on point 1 and drag it to point 12, and continue similarly.)
2) Click the Check Connection button to verify the connections.
3)If there are any incorrect connections, click on the wrong connection to remove it; otherwise, click Delete all connection to clear all connections.
4)Initially, set the resistor Ra to 3.3 kΩ, resistor Rb to 6.8 kΩ, capacitor C to 0.1 µF, and supply voltage Vcc to 5 V.
5)Click the Calculate button.
6)Record the output voltage displayed.
7)Click the Plot button to graph the Output Voltage and Capacitor Voltage.
8)Click the Clear button to reset the data.
9)Repeat the experiment with different resistance values.
10)Adjust the resistance Ra within the range of 1 kΩ to 10 kΩ.
11)Adjust the resistance Rb within the range of 1 kΩ to 10 kΩ.
12)Adjust the capacitance C within the range of 0.1 µF to 10 µF.
13)Set the supply voltage (Vcc) as needed.
## Circuit Diagram
![image](https://github.com/user-attachments/assets/303eba91-66eb-4a6a-9dbc-12f03dbb176c)


## Otuput Waveform
Voltage Across the Capacitor: 
![image](https://github.com/user-attachments/assets/3894310a-e307-4e17-a570-e0371812d10f)


Output Waveform: -
![image](https://github.com/user-attachments/assets/df261aa6-19a1-41bf-82f9-d65b0f5742c9)
