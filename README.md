# moscharacterisation

# CMOS Circuit Design and SPICE Simulation Synopsys Tool



### **_Brief Description of the course_**
This is a five-day workshop focused towards CMOS circuit design and SPICE simulation using Synopsys Tool organized by [VLSI System Design]( https://www.vlsisystemdesign.com/). The content of the workshop is divided across the five days in a smart way which allows the learner to grasp all the concepts if the workshop is attended dedicatedly. On the first day of the workshop the emphasis was on the basics of NMOS Drain current (Id), Drain-to-source Voltage (Vds) and the plot between the two of them. The second day focusses primarily on velocity saturation and basics of CMOS inverter VTC and the plots between Id and Vgs and the plot for determining the value of Vt. 
# **_INDEX:_** 
- [CMOS Circuit Design and SPICE Simulation using Synopsys Tool](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#cmos-circuit-design-and-spice-simulation-using-sky130-technology-workshop)
    - [Brief Description of the course](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#brief-description-of-the-course)
- [INDEX](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#index)
- [Day 1: Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#day-1-basics-of-nmos-drain-current-id-vs-drain-to-source-voltage-vds)
  - [Part 1: Introduction to Circuit Design and SPICE simulations](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#part-1-introduction-to-circuit-design-and-spice-simulations)
      - [What was learnt](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#what-was-learnt)
  - [Part 2: NMOS Resistive region and Saturation region of operation](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#part-2-nmos-resistive-region-and-saturation-region-of-operation)
      - [What was learnt](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#what-was-learnt-1)
  - [Part 3: Introduction to SPICE](https://github.com/VrushabhDamle/sky130CircuitDesignWorkshop/blob/main/README.md#part-3-introduction-to-spice)
      - [What was learnt](https://github.com/VrushabhDamle/sky130CircuitDesignWorkshop/blob/main/README.md#what-was-learnt-2)
      - [Lab Activity](https://github.com/VrushabhDamle/sky130CircuitDesignWorkshop/blob/main/README.md#lab-activity)


- [Day 2: Velocity Saturation and basics of CMOS inverter VTC](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#day-2-velocity-saturation-and-basics-of-cmos-inverter-vtc)
    - [Part 1: SPICE simulation for lower nodes and velocity saturation effect](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#part-1-spice-simulation-for-lower-nodes-and-velocity-saturation-effect)
        - [What was learnt](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#what-was-learnt-3)
        - [Lab Activity](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#lab-activity-1)
    - [Part 2: CMOS voltage transfer characteristics (VTC)](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#part-2-cmos-voltage-transfer-characteristics-vtc)
        - [What was learnt](https://github.com/ireneann713/moscharacterisation/blob/main/README.md#what-was-learnt-4)
# **Day 1: Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)**

On the first day the of the workshop, a basic introduction to MOSFETs and SPICE simulations was given. Basic terminologies of MOSFETs and the regions of operation were introduced. A few drain current (Id) equations were derived and the first SPICE simulation was successfully performed. The syntax for the simulation files was also explained and the method to create modules was also taught.

## **Part 1: Introduction to Circuit Design and SPICE simulations**

### **_What was learnt:_**

•	The importance of W/L ratio

•	Need of SPICE

•	NMOS design and specifications

- It is a four terminal deive
- It consists of a P-substrate body
- An isolation region created from SiO2 is present
- n+ diffusion region is present near the SiO2 layer
- It has a Gate oxide layer
- A Poly-Si or metal gate layer is added on top of the gate oxide layer
- There are a few abbreviations:
  - G means Gate
  - S means Source
  - D means Drain
  - B means Body or Bulk


![image](https://user-images.githubusercontent.com/55539862/166092546-afca8d50-dc20-4f42-a775-6478e68226e3.png)

Figure 1. The snap shot of an NMOS construction

•	Threshold Voltage (Vt)

  - The 'Vgs' voltage at which 'Strong Inversion' occurs is known as Threshold Voltage (Vt)

•	Concept of Strong Inversion

  - The phenomenon at which a part of the P-substrate becomes N-substrate (due to the high Vgs value) is called 'Strong Inversion'

•	Impact of Source-to-bulk Voltage (Vsb)

  - In presence of substrate bias voltage 'Vsb', an additional potential is required for strong inversion to occur

•	Threshold Voltage Equation

![Threshold voltage equation](https://user-images.githubusercontent.com/89193562/132532135-3de1b633-d02f-48b0-b9c6-030c40f2c30a.JPG)

where
  - Vto is the Threshold Voltage when Vsb = 0
  - Vto is a function of manufacturing voltage
  - ϒ is the body effect coefficient and it expresses the impact of changes in body bias 'Vsb' (unit of ϒ is V^0.5)
  - фf is the Fermi Potential

•	Body Effect Coefficient expression

![body effect coeffecient equation](https://user-images.githubusercontent.com/89193562/132532303-8b6fda87-3bc7-48ba-a99b-c7ffe5c4a969.JPG)

where
  - εsi is the relative permitivity of silicon (=11.7)
  - NA is the doping concentration
  - q is the charge of an electron
  - Cox is the oxide capacitance

•	Fermi Potential Equation

![fermi potential equation](https://user-images.githubusercontent.com/89193562/132532339-de5b4411-323e-48b2-bb3d-68b20e54dcef.JPG)

where
  - ni is the intrinsic doping parameter for the substrate


## **Part 2: NMOS Resistive region and Saturation region of operation**

### **_What was learnt:_**

•	Theory about Resistive region
  - It is also known as the Linear Region of operation
  - Since, Vgs=Vt, the changes that occur at different voltages of 'Vgs>Vt' are observed
  - In the channel, induced charge (Qi) α (Vgs-Vt)
  - The analysis is performed at Vgs=1V and a small (~0) Vds. Assume Vt=0.45V
  - In absence of Vds, the voltage across the n-channel was constant byt with application of Vds it is no more constant.
  - Let the effective channel length be L and 'x' axis be along the channel length and 'y' axis be perpendicular to the channel length
  - Let V(x) be the voltage at any point 'x' along the channel
  - Now, Vgs-V(x) is the gate-to-channel voltage at that point
  - Therefore, in the channel, induced charge at any point 'x' Qi(x) α - ((Vgs-V(x))-Vt)

•	Formula for charge induced at any point ‘x’

![induced charge at x](https://user-images.githubusercontent.com/89193562/132532646-03b38d68-de8d-45b1-92cf-7c240f922d2e.JPG)

•	First order analysis

•	Gate oxide capacitance formula

![gate oxide capacitance formula](https://user-images.githubusercontent.com/89193562/132532783-30c5d29d-4405-4833-a4b8-942d4787f50d.JPG)

where,
  - εox is the oxide permittivity = 3.97*εo = 3.5*10e-11 F/m
  - tox is the oxide thickness

•	The two kinds of current: Drift current and Diffusion current
  - Drift current is the current due to the potential difference
  - Diffusion current is the current due to difference in carrier concentration

•	The drift current (Id) = velocity of charge carriers * available charge over the channel width



•	Drift current (Id) formula

![drift current formula](https://user-images.githubusercontent.com/89193562/132532906-9238aba4-134e-4b1f-a00b-f7e126479071.JPG)

  - The term µn.Cox is denoted by kn' and kn' is known as process transconductance
  - kn'.(W/L) is denoted by kn and kn is also known as gain factor

•	Condition on Vds for the MOSFET to be in linear/resistive region or saturation/pinch-off region
  - When Vds <= (Vgs-Vt), the MOSFET is in linear region of operation
  - For this region, Id=kn.(Vgs-Vt).Vds as (Vds^2)/2 is a very small amount in this case
  - Vdds can be sweeped from 0V to (Vgs-Vt)V to make the device work in linear region of operation

•	Dependance of Id on Vds in pinch-off region
  - The chanel voltage is denoted with Vgs-Vds
  - Pinch-off condition is when Vgs-Vds=Vt
  - When the Pinch-off phenomenon is started, the channel begins to disappear. Basically, the channel starts to disappear only from the Drain side acquiring a triangular shape.
  - When Vgs-Vds<Vt, there is no channel present near the Drain terminal


  - Id becomes (kn/2).(Vgs-Vt)^2
  - It looks like a perfect current source i.e current is constant. It is not true because effective conductive channel length is modulated by applied Vds.
  - As Vds increases, the depletion region at the drain terminal increases and hence, the effective channel length decreases.
 
- Now the Drain current equation becomes:

![Id pinch off](https://user-images.githubusercontent.com/89193562/132710166-0b0c76d9-aeab-4a32-b56a-3ec5678c0fa6.JPG)

- Here, λ is the channel length modulation

## **Part 3: Introduction to SPICE**

### **_What was learnt:_**

- The spice waveforms can be used to calculate the delay of a cell. These delays are very close to the practical delays observed.

-	SPICE model parameters

-	SPICE simulation flow diagram



-	SPICE netlist for our NMOS
![Screenshot (353)](https://user-images.githubusercontent.com/55539862/164980915-e6ce264c-4a58-4fea-84bc-36bc9688b5bc.png)



Figure 4. The snap shot of SPICE netlist of the above NMOS

- R1 resistance is added as it is not desired that the current from Vin would be directly fed to the gate of M1.

-	Definition of nodes and the method to identify them
    - A node is can be defined as a point connecting two termials. If two terminals of a single device are short circuited then the node is said to be in between these two terminals. But most of the times a node connects two different devices.
    - The method to identify nodes is to identify the SPICE netlist for the device and all the wires connecting different components have one node on them.



### **_Lab Activity:_**



- There are five types of process corners available for use:
    - tt -> Typical corner
    - sf -> Slow-fast corner
    - ff -> Fast-fast corner
    - ss -> Slow-slow corner
    - fs -> Fast-slow corner
- In the Lab activity, tt corner is used. 

![Screenshot (355)](https://user-images.githubusercontent.com/55539862/164989664-ee2bdba9-eee5-447a-9cb7-225deb533324.png)
Figure 6. The snap shot of the Circuit of the Day1 activity

![Screenshot (352)](https://user-images.githubusercontent.com/55539862/164980780-3f91f436-8a97-4f13-b7f9-fc054800ccf5.png)


Figure 6. The snap shot of the output window of the Day1 activity


- To observe the value of Id at any point on the curve, then left click on the point on the curve to be observed.
- Now on the terminal window, some values of x0 and y0 should appear.
- The value of Id corresponds to the value of y0 in ampere.

# **Day 2: Velocity Saturation and basics of CMOS inverter VTC**

On the second day of the workshop SPICE simulation for lower nodes and the characteristics for long channel and short channel devices were observed. Also, the velocity saturation at lower and higher electric fields and velocity saturation drain current model were observed.

Finally MOSFET as a switch and the characteristics of CMOS inverter were taught.

## **Part 1: SPICE simulation for lower nodes and velocity saturation effect**

### **_What was learnt:_**

•	The distribution of various regions of operation of NMOS over the graph plotted between Ids and Vds.

![regions of operation](https://user-images.githubusercontent.com/89193562/132864852-2f667ae5-a71c-4e67-975a-e4c137843114.png)

Figure 7. The snap shot of various regions of operation of NMOS on graph plotted between Ids and Vds.

- The plot overlapping with the 'x' axis is at Vgs=0V and that is because there is 0 drain current at that point of time and the reason is that when Vgs=0V the nmos is not turned 'ON' so, there is no channel present.

-	The theory about cut-off region of NMOS.
    - When Vgs<Vt the region of operation of the NMOS is said to be the cut-off region
    - Cut-off region is a region where the device has been cut-off or it is 'OFF'

-	Short channel effect

-	Velocity Saturation effect
    - For the lower values of electric field, the velocity tends to be a linear function of the electric field. But, after a certain point (cut-off) the velocity just saturates. This point of saturation is represented by εc (critical electric field)
    - Vn(m/S) = linear for ε<=εc
    - Vn(m/S) = constant for ε>=εc

![velocity saturation equation](https://user-images.githubusercontent.com/89193562/132674315-002da47e-65d4-4976-b2c0-b309dee76df7.JPG)

![velocity saturation graph JPG](https://user-images.githubusercontent.com/89193562/132679374-baa32830-fcca-49c3-be54-10b5caf2c5d3.png)

Figure 8. The snap shot of the graph of velocity saturation effect

-	The modes of operation for long channel (>250nm) devices and short channel (<250nm) devices.
-	The modes of operation for long channel devices are:
    - Cut-off region
    - Resistive region
    - Saturation region
- The modes of operation for short channel devices are:
    - Cut-off region
    - Resistive region
    - Velocity Saturation region
    - Saturation region
 
- Let's call (Vgs-Vt)=Vgt

-	The equation of Id for long channel and short channel devices

![Id equation](https://user-images.githubusercontent.com/89193562/132674348-c1e9e289-f766-4750-94f1-eb4cfe5189eb.JPG)

- Vdsat is a technology parameter saturation voltage i.e voltage at which device velocity saturates and is independent of Vgs or Vds

-	The various modes when the value of Vmin is different
    - When Vgt is the minimum of Vgt, Vds, Vdsat the device is in saturation region.
    - When Vds is the minimum of Vgt, Vds, Vdsat the device is in resistive region.
    - When Vdsat is the minimum of Vgt, Vds, Vdsat the device is in velocity saturation region.
    - It looks like current should increase at lower nodes.

-	Velocity Saturation causes device to saturate early

### **_Lab Activity:_**



![Screenshot (356)](https://user-images.githubusercontent.com/55539862/166094579-eb67439a-d866-4316-afb1-ad55f6a10a69.png)

Figure 10. The snap shot of output window for plot between Ids and Vds for short channel device

- To observe the value of Id at any point on the curve, then left click on the point on the curve to be observed.
- Now on the terminal window, some values of x0 and y0 should appear.
- The value of Id corresponds to the value of y0 in ampere.





![Screenshot (358)](https://user-images.githubusercontent.com/55539862/166094550-4438a1f8-f38c-4a43-89eb-7ccd24603642.png)


Figure 12. The snap shot of output window for plot between Ids and Vds for short channel device without the sweep for vdd

- In order to calculate the Threshold voltage, the linear part of the plot must be extended. Now, the x intercept of this extended plot gives the value of the threshold voltage of the device that is being simulated.

## **Part 2: CMOS voltage transfer characteristics (VTC)**

### **_What was learnt:_**

-	Transistor as a switch
    - With infinite 'Off' resistance when |Vgs|<|Vt|
    - With finite 'On' resistance when |Vgs|>|Vt|

-	The working of CMOS inverter

-	What happens when Vin is ‘high’ and equal to ‘vdd’
    - PMOS turns 'OFF'
    - NMOS turns 'ON'
   
-  What happens when Vin is ‘low’ and equal to ‘0V’
    - PMOS turns 'ON'
    - NMOS turns 'OFF'

-	The flow of current when Vin is ‘high’ and when Vin is ‘low’
- When Vin=Vdd
    - Direct path exists between Vout and Vss resulting in Vout=0V
- When Vin=0V
    - Direct path exists between Vdd and Vout, resulting in Vout=Vdd

-	Defined terminologies in CMOS inverter

![1631186540042](https://user-images.githubusercontent.com/89193562/132681895-fe353e35-c49a-4fcf-a822-640a20898861.jpg)

Figure 13. The snap shot of the circuit diagram of CMOS inverter

-	By observation:
- For the NMOS voltage equations

![NMOS relations](https://user-images.githubusercontent.com/89193562/132678807-2bcbfa75-4081-46cb-899d-7b3915c62688.JPG)
    
- For the PMOS voltage equations

![PMOS relations](https://user-images.githubusercontent.com/89193562/132678852-68fd02e7-f396-45f5-8ea3-3b2645c71372.JPG)

- For the relationship between the currents

![current relations](https://user-images.githubusercontent.com/89193562/132678900-8087d81b-0588-46f8-8fc9-11e51725ebdd.JPG)

-	Load curve for PMOS transistor in CMOS inverter

![1631302325727](https://user-images.githubusercontent.com/89193562/132907643-9423cede-796e-40b7-a8bb-36fde16d533f.jpg)

Figure 14. The snap shot of load curve for PMOS transistor in CMOS inverter

-	Load curve for NMOS transistor in CMOS inverter

![1631302325723](https://user-images.githubusercontent.com/89193562/132907688-664d7f0e-da4e-4c36-9270-fca25f24b945.jpg)

Figure 15. The snap shot of load curve for NMOS transistor in CMOS inverter

-	Superimposing the load curve of NMOS on the load curve of PMOS and plotting Vin vs Vout from the graph obtained

![1631359704747](https://user-images.githubusercontent.com/89193562/132946435-09010251-dd7e-4af4-b791-ea5655dd171f.jpg)

Figure 16. The snap shot of superimposed load curve of NMOS and load curve of PMOS

![1631278404895](https://user-images.githubusercontent.com/89193562/132859275-865ad5a6-d174-4bb0-9615-77cc5deb9992.jpg)

Figure 17. The snap shot of the plot of Vout versus Vin

- Graphically, the Vin points from the intersection of corresponding load lines are picked-up.



# **Day 3: CMOS switching threshold and dynamic simulations**

On the third day of the workshop the emphasis was on Voltage Transfer Characteristics using SPICE simulations and later on CMOS Inverter Robustness. Many factors were told but only the switching threshold was discussed in depth. An equation relating switching threshold voltage (Vm) and (W/L) ratios of the PMOS and the NMOS was also derived and alternatively, an equation for (W/L) ratios of the PMOS and the NMOS if the Vm is preset was also derived.

## **Part 1: Voltage transfer characteristics and SPICE simulations**

### **_What was learnt:_**
- The various components of a SPICE deck:
    - Component connectivity
    - Component values
    - Identification of 'nodes'
    - Naming 'nodes'

- Let us consider the following SPICE netlist



### **_Lab Activity:_**

```
**  Generated for: PrimeSim
*  Design library name: pll
*  Design cell name: NOT_GATE_tb
*  Design view name: schematic
.option search='/home/skandha/Tools_SNPS/Downloads_temp/SAED32nm_PDK_09302020/hspice'


.option PARHIER = LOCAL
.option PORT_VOLTAGE_SCALE_TO_2X = 1
.option RUNLVL = 3

.option WDF=1
.temp 25
.lib 'saed32nm.lib' TT

*Custom Compiler Version S-2021.09-SP2
*Thu Apr 28 16:55:51 2022

.global gnd!
********************************************************************************
* Library          : pll
* Cell             : NOT_Gate
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
.subckt not_gate a vdd vss y
xm2 y a vss vss n105_hvt w=1u l=0.03u nf=1 m=1
xm3 y a vdd vdd p105_hvt w=2.5u l=0.03u nf=1 m=1
.ends not_gate

********************************************************************************
* Library          : pll
* Cell             : NOT_GATE_tb
* View             : schematic
* View Search List : hspice hspiceD schematic spice veriloga
* View Stop List   : hspice hspiceD
********************************************************************************
xi0 net5 net7 gnd! net1 not_gate
v1 net5 gnd! dc=0 pulse ( 1 0 0.1p 10p 10p 20n 40n )
v2 net7 gnd! dc=0.9625

.tran 0.1n 100n start=0
.dc v1 0 1 0.02
.option opfile=1 split_dp=1
.option probe=1
.probe tran v(*) level=1
.probe tran v(net1) v(net5)
.probe dc v(*) level=1
.probe dc v(net1) v(net5)





.end

```
Figure 18. The snap shot of the SPICE netlist considered


![Screenshot (361)](https://user-images.githubusercontent.com/55539862/166093452-ff8ad3b7-cfab-42a0-a35c-1367d21f2051.png)


Figure 20. The snap shot of the output window for plotting the Vtc characteristics of CMOS inverter

- To find the switching threshold voltage (Vm), it is known that Vout = Vin so zoom in on the plot where roughly Vout = Vin by selecting the area of the plot by right clicking on the screen and dragging it to select the area.
- Zoom twice or thrice until the point where Vm lies becomes almost certain.
- Left click roughly on the point on the curve where Vm should approximately lie.
- Values of x0 and y0 will now appear on the terminal window.
- Since we are finding Vm, therefore x0 ~ y0 and hence x0=y0=Vm.





![output window transient](https://user-images.githubusercontent.com/89193562/132863939-9f777f44-e10e-4bc3-a9a2-41e833dd465b.JPG)

Figure 22. The snap shot of the output window for performing the transient analysis

- To calculate the rise delay:
    - Zoom on the part of the curve having fall of the input pulse and rise of the output pulse around voltage of (Vdd/2) by right clicking on the screen and dragging it to select the area.
    - Now, left click on the rising edge of the output curve at (Vdd/2) to get a point x0,y0 on the terminal.
    - Similarly, get the point at (Vdd/2) for falling edge of the input curve.
    - The difference between the x-coordinate of the rising edge of the output curve and the falling edge of the input curve is the rise delay.
- To calculate the falling delay:
    - Zoom on the part of the curve having rise of the input pulse and fall of the output pulse around voltage of (Vdd/2) by right clicking on the screen and dragging it to select the area.
    - Now, left click on the falling edge of the output curve at (Vdd/2) to get a point x0,y0 on the terminal.
    - Similarly, get the point at (Vdd/2) for rising edge of the input curve.
    - The difference between the x-coordinate of the falling edge of the output curve and the rising edge of the input curve is the fall delay.

## **Part 2: Static Behavior Evaluation - CMOS Inverter Robustness: Switching threshold**

### **_What was learnt:_**

- CMOS inverter is a robust device because the shape of it's input versus output curve remains the same for all different values of (W/L) ratios.
- Static Behavior Evaluation: CMOS Inverter Robustness
    - Switching Threshold
    - Noise Margin
    - Power Supply Variation
    - Device Variation

- Switching Threshold (Vm)
    - It is the point where Vin = Vout
    - Graphical method to find Vm is to draw a line across the graph of output voltage to input voltage of a CMOS inverter starting at the origin and ending at the opposite diagonal of the plot (basically a line with a 45 degree inclination with the x-axis). Now, the x-coordinate of the point of intersection of this line and the curve is the switching threshold.
    - Vm when (Wp/Lp) is 1.5 is approximately equal to 0.98V and when (Wp/Lp) is 3.75 it is approximately equal to 1.2V
    - Wp and Lp in the above section are Width of PMOS channel and Length of PMOS channel
    - At Vm, both PMOS and NMOS are turned 'ON' because Vgs almost crossed the threshold region for both of them.
    - A few observations can be made from the information stated above,
    - Therefore, Vgs = Vds
    - IdsP = - IdsN which means that IdsP + IdsN = 0
    - We know the equations for IdsN and IdsP which are as stated below:
    
      ![Idsn and Idsp equations](https://user-images.githubusercontent.com/89193562/132867914-dc5b1ac9-a4d9-452b-9352-4872c94264fe.JPG)

We ignore the 1+λVds because the term is very small and it makes the equations very difficult for hand calculations.

Since, IdsP + IdsN = 0

Therefore, the equations can be re-written as:

![Idsn_plus_Idsp_is_zero](https://user-images.githubusercontent.com/89193562/132868215-8eb427a0-1a5a-4c3f-8cd5-76c41d49d947.JPG)

Let's consider this as equation 1

Solving the above equation for Vm,

![vm equation](https://user-images.githubusercontent.com/89193562/132869184-bd60ea34-e16f-4c7b-9be7-05386549329a.JPG)

- Alternatively, the required ratio of PMOS versus NMOS transistor size can be derived such that Vm is set.

Equation 1 must be taken in the form IdsN = - IdsP

Therefore,

![wp lp wn ln equation](https://user-images.githubusercontent.com/89193562/132872201-eba019d8-5a72-480a-a44d-f4d66f718da1.JPG)

- Here,
    - Wp is the width of the channel in PMOS
    - Lp is the length of the channel in PMOS
    - Wn is the width of the channel in NMOS
    - Ln is the length of the channel in NMOS
    - kn' is the process transconductance of the NMOS
    - kp' is the process transconductance of the PMOS
    - Vdsatn is the Vdsat of the NMOS
    - Vdsatp is the Vdsat of the PMOS
    - Vm is the switching threshold voltage
    - Vt is the threshold voltage
    - Vdd is the supply voltage

- We experimented with the sizes of the PMOS with respect to the sizes of NMOS and came up with the following conclusions

|(Wp/Lp)|x.(Wn/Ln)|Rise Delay|Fall Delay|Vm   |
|:---:  |:---:    |:---:     |:---:     |:---:|
|(Wp/Lp)|1.(Wn/Ln)|148pS     |71pS      |0.99V|
|(Wp/Lp)|2.(Wn/Ln)|80pS      |76pS      |1.2V |
|(Wp/Lp)|3.(Wn/Ln)|57pS      |80pS      |1.25V|
|(Wp/Lp)|4.(Wn/Ln)|45pS      |84pS      |1.35V|
|(Wp/Lp)|5.(Wn/Ln)|37pS      |88pS      |1.4V |

- We can make some conclusions from the above table:
    - When `(Wp/Lp) = 2.(Wn/Ln)`, there is an approximately equal rise-fall delay
    - Due to the equal rise-fall delay, `(Wp/Lp) = 2.(Wn/Ln)` create typical characteristics for a clock inverter/buffer
    - The conditions other than `(Wp/Lp) = 2.(Wn/Ln)` can still be used as regular inverters/buffers and these can be preferred for data path
    - Switching Threshold for `(Wp/Lp) = 2.(Wn/Ln)` and `(Wp/Lp) = 3.(Wn/Ln)` is very small. Similarly, switching threshold for `(Wp/Lp) = 4.(Wn/Ln)` and `(Wp/Lp) = 5.(Wn/Ln)` is also very small

- When Wp/Lp is increased, the rise delay is isgnificantly reduced because time required for the output capacitor to charge decreases significantly and the reason is the availability of a bigger area to charge the capacitor.
- Ron(PMOS) ~ 2.5\*Ron(NMOS)
