# BGR_workshop
Bandgap Reference (BGR) design using SKY130 PDK — schematic, SPICE verification, and Magic layout implementation.

## Overview
A bandgap voltage reference is a voltage reference circuit widely used in integrated circuits. It produces an almost constant voltage corresponding to the particular semiconductor's theoretical band gap, with very
little fluctuations from variations of power supply, electrical load, time, temperature.The design and implementation of a CMOS Bandgap Reference (BGR) circuit based on the open-source SKY130 PDK are documented in
this repository. By adding up the CTAT and PTAT currents via a self-biased circuit, the design seeks to generate a temperature-insensitive reference voltage.

Starting with transistor-level SPICE simulations, start-up circuit analysis, and hierarchical layout development in Magic VLSI, the design process encompasses the full analogue design chain. PTAT/CTAT current
modelling, bias stabilisation, device matching, and design methodology are among the main subjects discussed.

## Tools Used
- Ngspice
- Magic VLSI
- SKY130 PDK

## Architecture
<img width="752" height="490" alt="image" src="https://github.com/user-attachments/assets/c3846e5e-7412-4dca-affc-ccc13fd5a3fa" />
