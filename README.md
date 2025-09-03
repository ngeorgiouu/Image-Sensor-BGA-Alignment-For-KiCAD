🧩 Image-Sensor BGA Alignment for KiCad

BGA Alignment Footprint Generator.
This repository contains a Python tool with a PyQt5 GUI to automatically generate KiCad BGA package footprints for image sensor devices.
It eliminates the need for manually placing pads, optical frames, and mounting holes by generating a complete .kicad_mod footprint file from user-defined parameters.

✨ Features:


🔹 GUI Input Fields for package geometry:

    * Number of BGA pads along X and Y
  
    * Pitch values for both axes
  
    * Package dimensions
  
    * Optical offsets (µm → mm conversion)
  
    * Inner & outer optical frame sizes
  
    * Mounting hole spacing, size, and drill diameter
  
🔹 Automatic Footprint Generation:
BGA pad array (smd circle) with proper naming (A1, B1, …)

    * Fabrication & courtyard outlines
  
    * Inner/outer optical frame markers
  
    * Keepout zones around the optical window
    
    * Mounting holes with silkscreen and fab indicators
  
    * Reference & value text labels

📦 Output: a ready-to-use .kicad_mod footprint file.
