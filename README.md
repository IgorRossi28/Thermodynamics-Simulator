# **Vapor Compression Refrigeration Cycle Simulator**
A Python-based graphical application for thermodynamic simulation of a vapor compression refrigeration cycle, including water cooling load, external heat exchanger effects, and complete cycle visualization. This tool was developed to support engineering analysis, preliminary design, and educational studies of refrigeration systems.

## **Features**
• Interactive graphical user interface (GUI) built with Tkinter
• Complete vapor compression refrigeration cycle modeling
• Support for any refrigerant available in CoolProp
• Thermal load calculation including:
    - Water tank cooling inertia
    - External heat exchanger contribution
• Real compressor modeling with isentropic efficiency
• Automatic calculation of:
    - Refrigerant mass flow rate
    - Compressor power
    - Evaporator thermal load
    - Condenser heat rejection
• Full thermodynamic state table:
    - Temperature
    - Pressure
    - Enthalpy
    - Entropy
    - Vapor quality (title)
• Classical thermodynamic diagrams:
    - T–s (Temperature–Entropy)
    - P–h (Pressure–Enthalpy)

## **Thermodynamic Model**
The simulator follows the standard vapor compression refrigeration cycle:
1. Evaporator outlet
    - Saturated vapor at evaporation temperature
2. Compressor (real process)
    - Compressor (real process)
3. Condenser outlet
    - Isentropic efficiency applied
4. Expansion Valve
    - Isenthalpic expansion
Thermophysical properties are obtained using CoolProp, ensuring high accuracy and consistency.

## **Inputs**
**Refrigeration System:**
  • Refrigerant selection (CoolProp-compatible)
  • Compressor isentropic efficiency
  • Evaporator and condenser temperature approaches (ΔT)
**Water Cooling System**
  • Water Volume
  • Water Density
  • Initial and target water temperature
  • Cooling time
**External Heat Exchanger**
  • Heat Exchanger effectiveness
  • Hot and cold fluid mass flow rates
  • Specific heat of hot fluid
  • Mean temperature difference between hot and cold fluid in the Heat Exchanger

## Outputs
**Thermodynamic State Table**
  • For states 1 to 4:
      - Temperature [°C]
      - Pressure [MPa]
      - Enthalpy [kJ/kg]
      - Entropy [kJ/kg·K]
      - Vapor quality (when applicable)
  • Energy Balance Summary
  • Refrigerant mass flow rate [kg/s]
  • Compressor power [W]
  • Evaporator thermal load [W]
  • Condenser heat rejection [W]
**Diagrams**
  • T–s diagram (cycle visualization)
  • P–h diagram (log-pressure scale)

## **Installation**
  pip install numpy matplotlib CoolProp
  Note: Tkinter is included by default with standard Python distributions.
  Others requirements is Numpy and matplotlib.

## Applications and Motivations
This code is applied to any type of specificity where the user wants to obtain thermodynamic data from a review cycle with steam variations. This solution has something specific that takes into account a heat exchange that steals heat from the water that is cooled by the refrigeration system, as this simulator is based on a medical device design that cools water to be able to send the cold water to a thermal heat exchanger and thus cool the patient's blood. The heat exchange calculation is estimated considering:
Q = e * Cmin * DeltaT
Where "e" is the efficiency of the heat exchanger, and DeltaT is the average temperature difference between water and blood at the heat exchanger inlets.

## License
This project is released under the MIT License.
It uses CoolProp, which is also distributed under the MIT License.

## Author
Igor R. Rossigali
Mechanical Engineer
Brazil

## Disclaimer
This software is intended for engineering analysis and educational purposes.
Results should be validated before use in safety-critical or commercial applications.
