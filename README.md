# Common-Source (CS) Amplifier Analysis

## 1. Introduction An essential component of analogue circuit design is a Common-Source (CS) amplifier. Its high gain properties make it a popular choice for voltage amplification. Based on the provided specifications, we will examine a CS amplifier in this report and do **AC and transient analysis** to examine how it behaves across frequency and time.  

## 2.Given Parameters

| Parameter | Value | Length of Channel (L) |180 nm || Voltage Supply (Vdd) | 1.8V Voltage at the Gate (Vg) | DC offset of 0.6V P Power Budget | 50 µW Current Drained (Id) 27 µA 1.08 µm is the transistor width (W). Sinusoidal Input Voltage (Vg AC signal) | Frequency = 1 kHz, Amplitude = 50mV Decade Sweep || AC Sweep Points for each decade | 20 0.1 Hz is the start frequency. Frequency of Stop | 1 THz || Analysis of Transients

![image](https://github.com/user-attachments/assets/53f81607-433a-4d50-a2a6-735a03317feb)


 ## 3. DC Analysis 
The power equation is used to calculate the transistor width:  
P = Vdd*Id

Assuming  Vdd=1.8V  and  P=50µW:
"Id =P/Vdd= 50 *10^{-6}/{1.8}      aprox= 27mu

The MOSFET current equation in saturation is now used:
The formula is I_d = 1/2* unCoxW/L (Vgs - Vth)^2]

In this example, unCox  is the process-dependent constant,  W  is width,  L is length, Vgs is gate-source voltage (0.6V in this instance), and Vth is threshold voltage(usually approximately 0.3V).  

After calculating out W, we discover:  
W = 1.08 um

![image](https://github.com/user-attachments/assets/e803f52e-61be-4aa1-b2c4-cc8c832bc35c)


## 4. AC Analysis AC analysis aids in our comprehension of the amplifier's frequency response. We examine the output at the drain after applying a small-signal AC input at the gate.

The setup for the AC analysis is as follows:
Input Signal: ( Vg = 0.6V + 50mVsin(2pi*1000 t)   
The AC amplitude for small-signal analysis is 1V.  
Frequency Sweep:Decade
Points per Decade: 20
Range of Frequencies: 0.1 Hz to 1 THz  

The amplifier's gain is determined by:
Av = -gm*Rd
where,
Rd is the drain resistance 
gm is the  transconductance of the mosfet.

We can see the gain bandwidth, cutoff frequency and stability by charting the frequency response.

![image](https://github.com/user-attachments/assets/c9162a82-1358-4b69-80f3-88405e41aed7)


## 5. Analysis of Transience 
We may examine the amplifier's response to the sinusoidal input signal over time with the use of transient analysis.

The setup for the transient analysis is as follows:
Stop Time: 5 ms 
Signal Input:  Sinusoidal with a frequency of 1 kHz and an amplitude of 50 mV 
Two probes are located at the drain output and Vg.  

As we look at the amplified output waveform in the transient analysis to confirm that it accurately tracks the input with the expected phase shift.

![image](https://github.com/user-attachments/assets/43eb823f-a217-45c0-bfd6-addcf50a4e5d)


## 6.Results

### 6.1 Analysis of Frequency Response (AC) 
At low frequencies, the gain (Av) stays constant.  
Gain decreases by -3 dB at the cutoff frequency.  
The gain decreases at high frequencies because of parasitic capacitances.

### 6.2 Transient Analysis of Time-Domain Response)
The input is amplified to create the output signal.
A 180-degree phase shift is present


## 7.Inference
We successfully analyzed the Common-Source Amplifier based on the given parameters.
From dc analysis we get the dc operating point and confirms whether the mosfet is saturation
Transient analysis shows how the mosfet behaves for the time varying AC signal.
The drain current(Id) was found to be 27 µA, 
The required width was 1.08 µm.
Through AC analysis, we obtained the frequency response, while transient analysis verified the amplified sinusoidal output with expected phase shift. This analysis is crucial in designing low-power analog circuits where performance must align with power constraints.




## Inverted CS Amplifer Analysis

## 1. Introduction  
In this experiment, we explore the performance of a Common-Source (CS) Amplifier where the PMOS transistor replaces the traditional resistor used in the drain circuit. This design helps us observe the impact of using a PMOS in place of a passive element and to analyze the amplifier's performance through Transient and AC analysis.

## Question
The supplied supply voltage is 1.8V and the dissipation of power is 50 µW . Given a gate voltage (VG) of 0.9V,the target voltage is used to determine the the DC operating point(Id). Moreover, an AC analysis is carried out with a sinusoidal input voltage, and then analyzed using shifted transients todetermine the time domain.

Both NMOS and PMOS transistors have the same physical dimensions:
Channel Length (L) = 180 nm
Channel Width (W) = 0.61 µm

We will analyze the 
transistor characteristics
frequency response
time-domain behavior under the given parameters.

## 2. Circuit Diagram 
In this modified **CS amplifier**, a **PMOS transistor** is placed in place of the resistor in the drain path. The input signal is applied at the **gate** of the **NMOS transistor**, and the output is measured at the **drain**.  
![image](https://github.com/user-attachments/assets/8f4c9b6f-b8b5-4ed3-97bf-e48185cec46d)



## **3. Given Specifications**  

The following parameters define the conditions for the experiment:

| Parameter                               | Value                              |
| Channel Length (L)                      | 180 nm                             |
| Channel Width (W)                       | 0.61 µm                            |
| Voltage at Gate (Vg)                    | 0.6V (DC offset)                   |
| Power Budget (P)                        | 50 µW                              |
| Supply Voltage (Vdd)                    | 1.8V                               |
## 3. DC Analysis 
By perfoming the Dc analysis for the above circuit we find the quiescent operating point(Id) and the node voltages that are essential to operate the mosfet.
1.Supply voltage (Vdd) = 1.8V
2.Gate voltage(Vg) = 0.9V
3.Power Budget(P) = 50 µW

to find Id:
P=Vdd*Id
Id=P/Vdd
Id=50 µW/1.8V
I=27.7 µA  
![image](https://github.com/user-attachments/assets/7e9feda8-6b40-47b0-8e14-2dfd9b77d4bc)


## 4. Transient Analysis  
Drain Current (Id): 27.75 µA  
### Key Points of the Transient Analysis:
- The input signal is applied with a DC offset of 0.6V
-  an AC amplitude of 50mV with a frequency of 1kHz.
- The transient analysis simulates the circuit over time, showing how the output waveform responds to the input signal.
- The analysis shows how the output signal is amplified and  also phase shift expirenced by the CSamplifiers.


The waveform will show the input signal and the output signal at the drain, and we can also see the 180 degree phase shift
![image](https://github.com/user-attachments/assets/ddc52ffd-230b-42f5-b79a-e404bb6052e8)


## **5. AC Analysis**  
For AC analysis, our objective os to observe the frequency response of the amplifier. 
### **AC Analysis Setup**:
frequency sweep type:decade
sweeps per decade:20
frequency range:0.1Hz to 1THz
In this analysis, the gain of the amplifier is measured . The frequency response helps us understand:
- The low-frequency gain,
- The high-frequency roll-off due to parasitic effects,
- The cutoff frequencies of the amplifier.

We expect to see the gain of the amplifier remain less at low frequencies, then begin to increase at higher frequencies.with this analysis we can also identify the frequency response characteristics, including the cutoff frequency and the gain bandwidth.
![image](https://github.com/user-attachments/assets/dd36068f-aec9-4b40-bc01-abdbb71c3657)


## 6. Results & Observations 

### 6.1 Transient Analysis Waveform 
The transient analysis waveform reveals the amplified version of the input signal, with the expected 180-degree phase shift. It shows how the NMOS and PMOS transistors work together to amplify the input signal.
- Id (Drain Current): 27.75 µA
- The output signal correctly tracks the*input signal but with a larger amplitude.

### 6.2 AC Analysis Frequency Response
The AC analysis shows how the amplifier's gain behaves across different frequencies. The plot illustrates the frequency-dependent gain of the amplifier and helps us identify the cutoff frequency where the gain starts decreasing.


## 7. Infernce
In this experiment, we replaced the resistor in a Common-Source amplifier with a PMOS transistor, maintaining the same channel length (180 nm) and width (0.61 µm) for both NMOS and PMOS transistors. The transient analysis revealed a drain current of 27.75 µA and showed the amplified output with a 180-degree phase shift, which is typical for a CS amplifier. The AC analysis provided insight into the frequency response, showing the amplifier's gain behavior across a wide frequency range and identifying the cutoff frequencies. This experiment underscores the importance of PMOS substitution and its impact on amplifier performance, particularly in low-power analog designs.






