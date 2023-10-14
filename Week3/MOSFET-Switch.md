# MOSFET as a switch

MOSFETs are very good switches. In an ideal MOSFET no current flows into the gate due to the oxide insulator. In the off state no current flows between the drain and source. In the on state channel resistance of an ideal MOSFET is very low.

>**Note:** MOSFET channel resistance is very important for power applications such as automotive as these lead to high power losses at high voltage.

Both N-channel and P-channel MOSFETs can be used as switches. In the simplest terms, the N-channel MOSFET is turned on when the gate is high, and turned off then the gate is low. This opposite is true in P-channel MOSFETs.

MOSFETs are generally symmetrical, conducting in either direction. This in not quite true for 3-terminal discrete MOSFETs where the source and drain are determined by the internal bulk to source connection. 

## Sample and Hold Circuit

The sample and hold circuit is an important building block in Analogue to Digital converters. The circuit uses a clocked input $Ck$. When the clock is high, the analogue input voltage $V_{in}$ is tracked by the output $V_{out}$. On the falling edge of the clock the circuit samples the input $V_{in}$. It then holds this voltage on the output $V_{out}$ till the next rising edge of the clock.

### N-channel Sample and Hold

TODO: Add image

### P-channel Sample and Hold

TODO: Add image


## Additional Reading

Design of Analog CMOS integrated circuits ($2_{nd}$ edition) - Sections 2.1.1 and 13.2
