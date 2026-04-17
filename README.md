Engrave Curves – FreeCAD CAM Macro
A FreeCAD macro that generates engraving toolpaths along selected edges and curves, with full control over depth, direction, and edge linking.

Requirements
 FreeCAD 1.1.1 with the CAM workbench
 An existing CAM Job in the document
 At least one Tool Controller defined in the job

Installation
 1. Download EngraveCurve.FCMacro
 2. Place it in your FreeCAD macros folder (Edit → Preferences → General → Macro path)
 3. Run it via Macro → Macros... → Execute

Usage
 1. Job & Tool Controller
Select your CAM Job and the Tool Controller (engraving bit) to use from the dropdowns at the top.

2. Adding Edges
 1. Click Select Edges to enter selection mode
 2. Click one or more edges/curves in the 3D viewport
 3. Click Add Selected to add them to the list
 4. Repeat as needed — duplicate edges are ignored automatically

Use ▲ Move Up / ▼ Move Down to reorder the edges. The tool will follow them in listed order.

3. Edge Options
Each edge in the list has two checkboxes:

Column   Effect
Reverse  Flips the milling direction — the tool enters from the opposite end of the edge
Link     Connects this edge to the previous one without lifting the bit — the tool feeds directly from the end of the previous edge to the start of this one

Tip: Use Link on consecutive edges that share an endpoint or are very close together to avoid unnecessary retracts and improve cycle time.

4. Parameters
Parameter          Description
Total              DepthTotal engraving depth in mm
Step Down          Depth increment per pass in mm
Safe Height        Height above the work surface for rapid moves in mm
Feed Rate          Cutting feed rate in mm/min
Plunge Rate        Vertical plunge feed rate in mm/min
Curve Resolution   Maximum chord length when sampling curves in mm — lower values give smoother arcs

5. Generating the Path
Click OK to generate the toolpath. A Custom CAM operation will be added to your job containing the generated G-code. Click Cancel to abort without changes.

Notes
 The macro samples all curves into linear G1 segments — there are no G2/G3 arc moves
 Z values from the edge geometry are preserved, so the macro works on non-planar surfaces
 If an edge appears with the wrong direction, use the Reverse checkbox rather than reselecting it
