FreeCAD-CAM-Macro_EngraveCurves is a custom FreeCAD macro designed to create a CAM engraving operation for selected edges or curves in a 3D model. It allows users to generate precise, depth-controlled engraving paths for CNC machining directly within FreeCAD's CAM Workbench.
How It Works:

Select a Path Job: Choose the CAM job where the operation will be added.
Select a Tool: Pick a tool controller (e.g., an end mill or engraving bit) for the operation.
Select Edges/Curves: Use Ctrl+Click to select multiple edges or curves in your model that you want to engrave.
Run the Macro: The macro generates a custom G-code path for engraving, following the selected curves at specified depths and feed rates.
Key Features:

Depth Control: Set the total engraving depth (TOTAL_DEPTH) and step-down per pass (STEP_DOWN).
Surface-Following: The tool follows the Z-height of the selected curves, ensuring consistent engraving depth relative to the surface.
Safe Retraction: The tool retracts to a safe height (SAFE_HEIGHT) between passes to avoid collisions.
Feed Rate Control: Adjust feed rates for both cutting (FEED) and plunging (PLUNGE).
Curve Sampling: The macro samples curves at a specified resolution (STEP_RES) for smooth toolpath generation.
CAM Simulator Compatibility: The operation is fully visible and editable in FreeCAD's CAM simulator.
