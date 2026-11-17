# LTspice-Custom-Models
A growing collection of custom LTspice subcircuits and macro-models for electronic components that lack official manufacturer SPICE models.


# LTspice Custom Models Library

Welcome to the **LTspice Custom Models Library**! This repository contains a collection of custom-built SPICE macro-models and subcircuits for various electronic components that do not have official models provided by their manufacturers. 

These models are created based on official datasheet parameters and behavioral analysis. **Note:** The initial models in this repository were collaboratively developed and coded by an AI assistant (Google Gemini) and verified by me for functional switching and basic simulation purposes.

## Available Models

### 1. HCNW4503 (High-Speed Optocoupler)
- **Description:** A custom macro-model for the HCNW4503 single-channel, high-speed optocoupler (Avago/Broadcom). 
- **Configuration:** 5-Pin setup (`Anode`, `Cathode`, `GND`, `VO`, `VCC`).
- **Features:** 
  - Simulates basic switching behavior and propagation logic.
  - CTR (Current Transfer Ratio) is parametrized. By default, it is set to the typical value of `24%` (`CTR=0.24`). For worst-case design, you can easily change this parameter to `0.19` (19%) inside the `.sub` file.
- **Limitations:** This is a behavioral macro-model focused on switching logic. It does not perfectly model high-frequency parasitic capacitances or Common Mode Transient Immunity (CMR).

## How to Use These Models in LTspice

1. Download the desired `.sub` file (e.g., `HCNW4503.sub`) from this repository.
2. Open your LTspice schematic.
3. Add a generic component that matches the pinout (for example, a 5-pin optocoupler symbol).
4. `Ctrl + Right-Click` on the component in the schematic to open the Component Attribute Editor.
5. Change the **Prefix** to `X` (this tells LTspice it's a subcircuit).
6. Change the **Value** to the exact name of the subcircuit (e.g., `HCNW4503`).
7. Include the model in your schematic by adding a SPICE directive (press `S` on your keyboard) and typing:
   `.include HCNW4503.sub`
   *(Ensure the `.sub` file is in the same directory as your `.asc` file).*

## Contributing
Feel free to open issues if you spot any bugs in the models or submit pull requests if you want to contribute your own custom SPICE models to this library!

## Disclaimer
These are unofficial, behavioral models. They are provided "as-is" without any warranties. Always prototype and test your critical circuits in real life.