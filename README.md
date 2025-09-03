# Image-Sensor-BGA-Alignment-For-KiCAD
🧩 BGA Alignment Footprint Generator
This repository contains a Python tool with a PyQt5 GUI to automatically generate KiCad BGA package footprints for image sensor devices.
The script eliminates the need for manually placing pads, optical frames, and mounting holes by generating a complete .kicad_mod footprint file from user-defined parameters.
✨ Features
GUI input fields for package geometry:
Number of BGA pads along X and Y
Pitch values for both axes
Package dimensions
Optical offsets (µm → mm conversion)
Inner & outer optical frame sizes
Mounting hole spacing, size, and drill diameter
Automatic footprint generation:
BGA pad array (smd circle) with proper naming (A1, B1, …)
Fabrication & courtyard outlines
Inner/outer optical frame markers
Keepout zones around the optical window
Mounting holes with silkscreen and fab indicators
Reference & value text labels
Output: Generates a complete KiCad .kicad_mod footprint file ready for PCB layout.
📐 Example
The generator computes pad positions relative to optical offsets, ensuring correct alignment with the image sensor’s optical frame.
It also generates row/column labels automatically (A–Z, AA–AZ, …) for consistent BGA pad naming.
🚀 Usage
Install dependencies:
pip install pyqt5
Run the tool:
python BGA_Alignment.py
Enter package geometry values in the GUI.
Click Save Inputs + Generate Footprint.
The footprint file BGA_Footprint.kicad_mod will be created in the working directory.
Import this into KiCad via:
Preferences → Manage Footprint Libraries.
🖼️ GUI Layout
X-Axis group: pads, pitch, package size, optical offset, optical frame, MH distance
Y-Axis group: pads, pitch, package size, optical offset, optical frame, MH distance
General group: BGA ball size, mounting hole size, drill diameter
Button: generates and saves the footprint
📝 Code Description
The core script uses PyQt5 for the GUI and Python string templates to generate KiCad-compatible footprint text.
Main functions:
make_kicad_footprint(...): builds the full .kicad_mod text, including pads, frames, and keepouts
generate_arc(...) / generate_circle(...): helper functions to construct KiCad primitives in the correct format
save_inputs(): collects GUI inputs, validates them, and saves the generated footprint file
The result is a parameter-driven footprint generator tailored for BGA image sensors, removing tedious manual CAD work.
