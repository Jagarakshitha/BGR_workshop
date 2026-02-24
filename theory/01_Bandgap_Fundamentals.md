# Bandgap Reference Fundamentals

## 1. Introduction

A Bandgap Reference (BGR) is a fundamental analog circuit used to generate a temperature-independent reference voltage. In modern integrated circuits, stable reference voltages are essential for biasing analog blocks such as LDO regulators, ADCs, DACs, PLLs, and sensor interfaces. 

Unlike simple resistor dividers or Zener-based references, a bandgap reference compensates for temperature variations by combining two opposing voltage characteristics: CTAT and PTAT.

---

## 2. Why Reference Voltage Circuits Are Needed

Integrated circuits operate across wide temperature and process variations. Without a stable reference:

- Bias currents drift with temperature
- Amplifier offsets increase
- Analog accuracy degrades
- Supply variations affect performance

Early reference techniques included:

- Resistor dividers → supply dependent
- Zener diodes → high voltage requirement and large noise
- Threshold-referenced MOS circuits → strong process dependence

Bandgap references became the industry standard because they provide:

- Temperature stability
- Supply independence
- CMOS compatibility
- Low power operation

---

## 3. Basic Bandgap Principle

The core idea of a bandgap reference is to combine:

- **CTAT voltage** (Complementary To Absolute Temperature)
- **PTAT voltage** (Proportional To Absolute Temperature)

### 3.1 CTAT Component

The base-emitter voltage \(V_{BE}\) of a BJT decreases with temperature:

\[
V_{BE} \approx V_{G0} - \alpha T
\]

This creates a negative temperature coefficient.

---

### 3.2 PTAT Component

By using two BJTs with different emitter areas, a voltage difference is generated:

\[
\Delta V_{BE} = V_T \ln(N)
\]

Where:

- \(V_T = kT/q\) (thermal voltage)
- \(N\) = emitter area ratio

This voltage increases with temperature, creating a PTAT behavior.

---

### 3.3 Combining CTAT and PTAT

The bandgap voltage is formed by adding a scaled PTAT voltage to the CTAT voltage:

\[
V_{REF} = V_{BE} + k \cdot \Delta V_{BE}
\]

By carefully choosing the scaling factor \(k\), the temperature dependence cancels out, producing an approximately constant reference near **1.2 V**, close to the silicon bandgap voltage.

---

## 4. Why Self-Biased Architecture Is Used

Traditional bias circuits require external current references. A self-biased bandgap generates its own operating current internally.

Advantages:

- Reduced dependence on external bias
- Better process portability
- Lower power consumption
- Fully integrated design

However, self-biased circuits can have a zero-current equilibrium point, which requires a **start-up circuit** to ensure proper operation.

---

## 5. Role of Matching in Bandgap Design

Bandgap accuracy strongly depends on device matching:

- BJT area ratios define PTAT slope
- Resistor matching defines scaling factor
- MOSFET matching affects bias currents

Layout techniques such as common-centroid placement and dummy devices are used to minimize mismatch.

---

## 6. Summary

A bandgap reference works by combining opposing temperature-dependent voltages to produce a stable reference. The key design challenges include achieving proper biasing, ensuring device matching, and maintaining stability across process and temperature variations.

In this project, the bandgap reference is implemented using the SKY130 PDK, with transistor-level simulation and hierarchical layout design to demonstrate a complete analog design workflow.
