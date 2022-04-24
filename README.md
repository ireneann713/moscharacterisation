# moscharacterisation

# CMOS Circuit Design and SPICE Simulation Synopsys Tool



### **_Brief Description of the course_**
This is a five-day workshop focused towards CMOS circuit design and SPICE simulation using Synopsys Tool organized by [VLSI System Design]( https://www.vlsisystemdesign.com/). The content of the workshop is divided across the five days in a smart way which allows the learner to grasp all the concepts if the workshop is attended dedicatedly. On the first day of the workshop the emphasis was on the basics of NMOS Drain current (Id), Drain-to-source Voltage (Vds) and the plot between the two of them. The second day focusses primarily on velocity saturation and basics of CMOS inverter VTC and the plots between Id and Vgs and the plot for determining the value of Vt. The third was concentrated on CMOS switching threshold and dynamic simulations, where a lot of equations were derived to find the relationships between the (W/L) ratios of the PMOS and NMOS and the switching threshold voltage (Vm). On the fourth day of the workshop, Noise margins and CMOS inverter robustness with respect to them was discussed. On the fifth and final day of the workshop the emphasis was on Power supply variation and Device variation. In the power supply variation, the effects of using various power supplies on the inverter were observed and we discussed the advantages and disadvantages of using small power supply and the reason that it is not used. In the device variation, the impact of manufacturing processes on a single inverter and inverter chain were discussed.

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

![1631113926996](https://user-images.githubusercontent.com/89193562/132697108-70c1704e-7389-4d04-84c3-189d945e04d5.jpg)

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

![1631196789430](https://user-images.githubusercontent.com/89193562/132702310-fe28f367-775f-4e17-b28a-a3716fde099b.jpg)

Figure 2. The snap shot of top view of the MOSFET showing the channel width 'W'

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

![1631198852969](https://user-images.githubusercontent.com/89193562/132708164-64f39d56-8289-4af0-96c7-1e8515bc53fe.jpg)

Figure 3. The snap shot of the NMOS showing the pinch-off region

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


![spice workflow](https://user-images.githubusercontent.com/89193562/132533155-7affa537-beb3-4aa4-8eab-b4ff3aaab64d.JPG)

-	SPICE netlist for our NMOS
![Screenshot (353)](https://user-images.githubusercontent.com/55539862/164980915-e6ce264c-4a58-4fea-84bc-36bc9688b5bc.png)



Figure 4. The snap shot of SPICE netlist of the above NMOS

- R1 resistance is added as it is not desired that the current from Vin would be directly fed to the gate of M1.

-	Definition of nodes and the method to identify them
    - A node is can be defined as a point connecting two termials. If two terminals of a single device are short circuited then the node is said to be in between these two terminals. But most of the times a node connects two different devices.
    - The method to identify nodes is to identify the SPICE netlist for the device and all the wires connecting different components have one node on them.

-	SPICE syntax

-	Method to save SPICE model

-	Method to write code for SPICE simulation

### **_Lab Activity:_**



- There are five types of process corners available for use:
    - tt -> Typical corner
    - sf -> Slow-fast corner
    - ff -> Fast-fast corner
    - ss -> Slow-slow corner
    - fs -> Fast-slow corner
- In the Lab activity, tt corner is used. The corner can be changed by changing the word 'tt' in the line `.lib "sky130_fd_pr/models/sky130.lib.spice" tt` with any valid process corner




![Screenshot (352)](https://user-images.githubusercontent.com/55539862/164980780-3f91f436-8a97-4f13-b7f9-fc054800ccf5.png)


Figure 6. The snap shot of the output window of the Day1 activity

- To observe the value of Id at any point on the curve, then left click on the point on the curve to be observed.
- Now on the terminal window, some values of x0 and y0 should appear.
- The value of Id corresponds to the value of y0 in ampere.

