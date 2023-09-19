# Introduction to MOSFETs

MOSFET stands for Metal Oxide Semiconductor FIeld Effect Transistor

<p align="center">
    <img src="./MOSFET.png" alt="MOSFET circuit symbol" width="200"/>
</p>

A MOSFET is a 4-terminal analogue switch. The voltage at the gate (G) controls the current flow between the drain (D) and the source (S). The body or bulk terminal (B) is part of the MOSFET substrate and influences the threshold voltage. This is often connected directly to the source by the MOSFET manufacturer.

>**Note:** If the bulk connection is not shown in a circuit diagram assume it is connected to the source

The following shows the internal structure of an N-channel MOSFET:

<p align="center">
    <img src="./N-MOSFET-Structure.png" alt="N-channel MOSFET internal structure" width="400"/>
</p>

As you can see it resembles the structure of 2 back-to-back diodes. It is called N-channel as it has N-type semiconductors used as the source and drain terminal material. When switched on by applying a sufficient $V_{GS}$ voltage as the gate, a N-type channel of electrons forms below the gate, allowing current to flow between the source and drain terminals. The P-channel is the complement of the N-channel MOSFET:

<p align="center">
    <img src="./P-MOSFET-Structure.png" alt="P-channel MOSFET internal structure" width="400"/>
</p>

>**Note:** The $+/-$ symbols (as in: P+/P-) refer to doping strength/concentration not charge

Important properties pertaining to the device functionality are the channel length $L$ and channel width $W$. These properties affect the device's behaviour and thus are often included in mathematical models describing operation:

<p align="center">
    <img src="./MOSFET-Dimensions.png" alt="Important MOSFET internal dimensions" width="500"/>
</p>

## MOSFET Operation

The N-Channel MOSFET switches on allowing current to flow between the drain and the source $I_{DS}$ (can also be stated as $I_{D}$), when the gate voltage $V_{GS}$ is more than the threshold voltage $V_{TH}$.

$$
On: V_{GS} > V_{TH}
$$

$$
Off: Otherwise
$$

As, to simplify calculations we define the overdrive voltage as $V_{OD} = V_{GS} - V_{TH}$. Thus, the above operating conditions can be restated as:

$$
On: V_{OD} > 0
$$

$$
Off: Otherwise
$$

### Cutoff

When the N-channel MOSFET is switched off it is said to be operating in the cutoff region. The MOSFET at the circuit level appears as a very high impedance between the source and the drain, thus stopping current flow $I_{DS} = 0$.

### Linear

When the N-Channel MOSFET is switched on ($V_{GS} > V_{TH}$), if the voltage between the source and drain is small:

$$
V_{DS} < V_{GS} - V_{TH} = V_{OD}
$$

The MOSFET is said to be in the linear operating region, and thus follows the following linear relationship between the drain current and drain source voltage (output characteristics):

$$
I_{DS} = \mu_{n} C_{OX} \frac{W}{L} \left((V_{GS} - V_{TH}) - \frac{V_{DS}}{2} \right) V_{DS}
$$

As mentioned above, MOSFETs have process parameters related to their manufacture. It is thus useful to define a device characteristic parameter $\beta$ as:

$$
\beta = \frac{\mu_{n}C_{OX}W}{L} = k^{\prime}_{n} \frac{W}{L} \qquad k^{\prime}_{n} = \mu_{n} C_{OX}
$$

>**Note:** Process parameters are subject to manufacturing variation, thus, a major challenge in MOS circuit design is robustness in design with respect to these parameters

The above linear output characteristic equation can be simplified as:

$$
I_{DS} = \beta (V_{OD} V_{DS} - \frac{V_{DS}^{2}}{2})
$$

For $V_{DS} << V_{OD}$ this becomes:

$$
I_{DS} = \beta V_{OD} V_{DS}
$$

### Saturation Region

When the N-Channel MOSFET is switched on ($V_{GS} > V_{TH}$), if the voltage between the source and drain $V_{DS}$ is sufficiently large, saturation occurs. 

<p align="center">
    <img src="./N-MOSFET-PinchOff.png" alt="N-Channel MOSFET Pinch-Off saturation condition" width="400"/>
</p>

In this case the voltage between the gate and the substrate at the drain is smaller than the threshold voltage and thus the channel thickness becomes zero at that point. This phenomena is called "pinch-off":

$$
V_{GD} = V_{GS} - V_{DS} \le V_{TH}
$$

Therefore, saturation occurs when:

$$
V_{DS} \ge V_{GS} - V_{TH} = V_{OD}
$$

The MOSFET is said to be in the saturation operating region, and thus follows the following relationship drain current output characteristic relationship (constant with respect to the drain source voltage):

$$
I_{DS} = \frac{\beta}{2} V_{OD}^{2}
$$
