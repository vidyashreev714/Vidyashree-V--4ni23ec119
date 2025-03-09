## Differential amplifiers
A differential amplifier is an electronic circuit designed to amplify the difference between two input signals. It has two inputs: the inverting input and the non-inverting input. The amplifier amplifies the voltage difference between these two inputs and outputs a corresponding voltage. The key feature of a differential amplifier is its ability to reject common-mode signals, which are signals that are present in both inputs. This rejection helps to minimize noise or interference that might be shared by both inputs, making it ideal for situations where you need to isolate weak signals from unwanted noise. Differential amplifiers are often used in applications like instrumentation, sensor readings, and audio systems, where the accuracy of the difference between signals is crucial.


## Aim: 

### ***Design a Differential Amplifier for the following specifications Vdd = 2.5V, P <= 3mW, Vicm = 1.3V, Vocm = 1.4V, Vp = 0.6V. Perform DC Analysis, Transient Analysis and Frequency Response also extract the Required Parameters.***

![image]
- Iss = P/V = (2.8mW)/(3.2V) = 0.875mA

- Id1 = Id2 = Iss/2 = 0.437mA

- Rss = Vp/Iss = 0.6V/0.875mA = 685.71 Ohms

- Rd1 = (Vdd-Vocm)/Id1 = (3.2-1.7)/(0.437mA) = 3.432K Ohms

- Rd2 = (Vdd-Vocm)/Id2 = (3.2-1.7)/(0.437mA) = 3.432K Ohms

***As all the required parameters for the design are found out , therefore we can design the circuit in the ltspice.***

### Procedure

- *Open LTspice
- *import the tsmc018.lib file before building up the circuit.*
- *Make sure that the file must be in the same folder as the experiment file*
- *Use the (.t) option in the toolbar and type **.lib tsmc018.lib** to import the library of that file*
- *Select the Rd and Rs with accurate Values and Select NMOS4*
- *Rename the MOSFET's as CMOSN* 
- *To perform the DC analsyis we must select the **Configure Analysis** Option in toolbar and select **DC op pnt** find the **Id** by adjusting the length and width of the CMOSN*
- *To perform the Transient analsyis we must select the **Configure Analysis** Option in toolbar and select **Transient** set the operating point such as Stop time **5ms** find the **Gain** by finding out the **Vin** and **Vout** from the waveform*
- *To perform the AC analsyis we must select the **Configure Analysis** Option in toolbar and select **AC analysis** select the operating points like Type of sweep as **decade**, Number of points per decade as **20**, Start and Stop Frequency from **0.1 to 1T Hz***

## Circuit 1 

![image]

***After the desin of the circuit is completed, then perform 1.DC analysis, 2.Transient Analsyis and 3.AC analysis find the frequency response***
## DC Analysis
- *After setting the voltage source as specified we must find the appropriate W and L values for CMOSN**
- *The Value of L is **180nm***
- *The Value of W is **3.5333445337um***
- *The Value of Id for these specification is **0.5995mA***
- *The Value of Iss for this specification is **1.2mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.4V***
  
![image]

## Transient Analysis

*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by,***

*Select the probe at **output node** for output waveform and at **1.3V Voltage source** for input waveform*

![image]

- Vout = V
- Vin = V
- Gain = (Vout)/(Vin) = ()/() =
- Vmax = 2.5V
- Vmin = 2.5 +  = V

***After the simulation from the graph of the transient analysis we can observe the 180 degree phase shift(i.e. input is 180 degree out of phase with output)***

## AC Analysis

***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep: **decade***
- *Number of points per decade: **20***
- *Start Frequency: **0.1 Hz***
- *Stop Frequency: **1T Hz***

***To obtain the graph of the ac analysis we must keep the probe at the output node***

![image]

## Circuit 2
![image]

*** In this circuit replace the Resistor Rss by a current source Iss***
*The value of ISS as we already found out ,asssign the value of ISS=**1.2mA***

***After building up the circuit perform the DC analysis, Transient Analsyis and AC analysis find the frequency response***

## DC Analysis 

- *The Value of L is **180nm***
- *The Value of W is **3.5333445337um***
- *The Value of Id for these specification is **0.5995mA***
- *The Value of Iss for this specification is **1.2mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.4V***

![image]

## Transient Analysis
*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **-50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by:***

*Select the probe at **output node** for output waveform and at **1.3V Voltage source** for input waveform*

![image]
- Vout = V
- Vin =V
- Gain = (Vout)/(Vin) = ()/() = 

***After the simulation from the graph of the transient analysis we can observe the 180 degree phase shift(i.e. input is 180 degree out of phase with output)***


## AC Analysis
***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep: **decade***
- *Number of points per decade: **20***
- *Start Frequency: **0.1 Hz***
- *Stop Frequency: **1T Hz***

  ***To obtain the graph of the ac analysis we must keep the probe at the output node***
![image]

## Circuit 3

![image]

*** In this circuit replace the Resistor Rss by NMOS(M3) MOSFET.***
- *The value of L is **180nm***
- *The value of W is **3.5333445337um***
- *The value of gate i.e Vb is **1.7447***

***After building up the circuit perform the DC analysis, Transient Analsyis and AC analysis find the frequency response***
## DC Analysis 
- *The Value of L is **180nm**(M1 and M2)*
- *The Value of W is **3.5333445337um**(M1 and M2)*
- *The Value of Id for these specification is **0.5995mA***
- *The Value of Iss for this specification is **1.2mA***
- *The Value of Vocm1, Vocm2 for this specification is **1.4V***

![image]

## Transient Analysis
*The First voltage source near gate of M1 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

*The Second voltage source near gate of M2 should be changed from DC to sine wave source with **DC Offset** as **1.3V** and **Amplitude** as **50m** and **Frequency** as **1K Hz***

***To perform Transient Analysis we must set the stop time for 5ms and the appropriate waveform is given by:***

*Select the probe at **output node** for output waveform and at **1.3V Voltage source** for input waveform*

![image]

- Vout = V
- Vin = V
- Gain = (Vout)/(Vin) = ()/() =
  
 ***After the simulation from the graph of the transient analysis we can observe the 180 degree phase shift(i.e. input is 180 degree out of phase with output)***


## AC Analysis

***To perform AC analysis we must set the operating point first they are shown below***
- *Type of sweep: **decade***
- *Number of points per decade **20***
- *Start Frequency: **0.1 Hz***
- *Stop Frequency: **1T Hz***

 ***To obtain the graph of the ac analysis we must keep the probe at the output node***

![image]


## Conclusion
### *In Circuit 1,* 
- *It is difficult to maintain stable current and it is highly dependent on supply voltage variations*
### *In Circuit 2,* 
- *Instead of using a resistor, a dedicated current source can be used to provide a constant current*
- *A constant current source ensures that the differential pair maintains better common-mode rejection*
- *The current becomes independent of supply voltage variations*
- *Since the impedance at the tail node is increased, the gain of the differential amplifier improves*
### *In Circuit 3,*
- *Instead of using a current source, an NMOS transistor operating in saturation (acting as a current source) can be used to generate the current*
- *An NMOS transistor in saturation has a much higher output resistance compared to a resistor or simple current source, improving gain*
- *An active current source can be designed to consume minimal power while maintaining a stable current*
- *Unlike resistors, NMOS-based current sources work well at low supply voltages, making them ideal for modern low-power applications*
