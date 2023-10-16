# MOSFET as a switch

MOSFETs are very good switches. In an ideal MOSFET no current flows into the gate due to the oxide insulator. In the off state no current flows between the drain and source. In the on state channel resistance of an ideal MOSFET is very low.

>**Note:** MOSFET channel resistance is very important for power applications such as automotive as these lead to high power losses at high voltage.

Both N-channel and P-channel MOSFETs can be used as switches. In the simplest terms, the N-channel MOSFET is turned on when the gate is high, and turned off then the gate is low. This opposite is true in P-channel MOSFETs.

MOSFETs are generally symmetrical, conducting in either direction. This in not quite true for 3-terminal discrete MOSFETs where the source and drain are determined by the internal bulk to source connection. 

## Sample and Hold Circuit

The sample and hold circuit is an important building block in Analogue to Digital converters. The circuit uses a clocked input $Ck$. When the clock is high, the analogue input voltage $V_{in}$ is tracked by the output $V_{out}$. On the falling edge of the clock the circuit samples the input $V_{in}$. It then holds this voltage on the output $V_{out}$ till the next rising edge of the clock.

### N-channel Sample and Hold

TODO: Add image


>**Note:** In the examples below we will assume $V_{DD} = 3.3V$ and $V_{TH} = 1V$.

#### Falling Output Voltage

Consider the following situation. The input voltage $V_{in} = 0V$ and $V_{out} = V_{DD}$. The difference between the input voltage $V_{in}$ and the output $V_{out}$ is at a maximum. When the clock goes high $Ck = V_{DD}$, the MOSFET will switch on and current will flow from the capacitor to the input. In this situation the output $V_{out}$ is the drain, and input $V_{in}$ is the source.

TODO: Add situation image

At $t=0$, the MOSFET switches from the cut-off to the saturation region as $V_{DS} = V_{DD} > V_{GS} - V_{TH}$. At $t = T$ the MOSFET is in the linear region. The output capacitor discharges completely to match the input voltage.

TODO: Add graph image

#### Increasing Output Voltage

Now consider the case where the input voltage $V_{in} = 1V$ and $V_{out} = 0V$. When the clock goes high $Ck = V_{DD}$, the MOSFET will switch on and current will flow from the input $V_{in}$ to the output capacitor. In this situation the output $V_{out}$ is the source, and $V_{in}$ is the drain.

TODO: Add situation image

At $t=0$, the MOSFET switches from the cut-off to the linear region as $V_{DS} = 1V < V_{GS} - V_{TH} = 2.3V$. At $t = T$ the MOSFET remains in the linear region ($V_{DS} = 0V < V_{GS} - V_{TH} = 1.3V). The output capacitor discharges completely to match the input voltage.

Notice that the propagation of the increased input voltage $V_{in}$ to the output $V_{out}$ has led to a reduction in the overdrive voltage. Further increasing the input voltage $V_{in}$ will further reduce this until the MOSFET switches off. To show this consider the case where the input voltage $V_{in} = V_{DD}$ and $V_{out} = 0V$. As before, the output capacitor will charge up and the output voltage $V_{out}$ will try to match the input $V_{in}$. When the output reaches $V_{DD} - V_{TH} = 2.3V$ the overdrive voltage will be $V_{GS} - V_{TH} = 0V$ and thus the MOSFET will switch off. The output cannot pass the full $V_{DD}$. 

TODO: Add image

### P-channel Sample and Hold

TODO: Add image


## Additional Reading

Design of Analog CMOS integrated circuits ($2_{nd}$ edition) - Sections 2.1.1 and 13.2
