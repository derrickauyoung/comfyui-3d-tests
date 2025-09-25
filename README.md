# comfyui-3d-tests
Exploring ComfyUI workflows.

# HunYuan3D Experiments (ComfyUI)
Exploring workflows to generate 3D assets from multi-view iPhone photos using the HunYuan3D Multiview to Model nodes in ComfyUI.  

**Why:** In production, fast turnaround for asset prototyping can save artists significant time.  
**What I tried:** Testing node graphs for multi-view reconstruction → mesh output.  

## Trials

### Attempt 1
<img width="1906" height="1086" alt="Screenshot 2025-09-23 at 12 12 45 PM" src="https://github.com/user-attachments/assets/5f81d681-1d1d-4ba0-8a8e-d04b8104b22f" />

### Attempt 2
 + Re-run with the same settings (better, learned result!)
 + The background monitors appear in the .GLB model
<img width="1899" height="1083" alt="Screenshot 2025-09-23 at 12 15 55 PM" src="https://github.com/user-attachments/assets/3610d77d-567d-4a6d-ba80-8c900a6d94a7" />
<br>
<img width="1905" height="1083" alt="Screenshot 2025-09-23 at 12 16 09 PM" src="https://github.com/user-attachments/assets/04a8b67f-a997-4835-af91-6ae6b2b9b1bb" />

### Attempt 3
 + Attempted to adjust KSampler "cfg" parameter to 8.0
<img width="1110" height="754" alt="Screenshot 2025-09-23 at 1 03 03 PM" src="https://github.com/user-attachments/assets/b4297641-88c5-48d3-83c8-6c01f4276615" />

### Attempt 4
 + Re-took picture with a clearer background
 + Attempted to adjust Ksampler sampler_name model to "dpm_2" with "cfg" set to 8.0 (worse results)
<img width="1901" height="1087" alt="Screenshot 2025-09-23 at 12 47 31 PM" src="https://github.com/user-attachments/assets/ff4cc933-5957-424a-804c-a0fab50d28d2" />

### Attempt 5
 + Added a painted "Mask" to the supplied images
 + Set KSampler "sampler_name" model back to "euler"
 + Set KSampler "cfg" back to 4.0
 + Improved, but still overall malformed (Appears that screenspace size of object was too small for the model to distinguish features - possibly from iphone photo compression)
<img width="1900" height="1090" alt="Screenshot 2025-09-23 at 1 10 10 PM" src="https://github.com/user-attachments/assets/57c9d685-b570-4e26-b626-4f5b080bd1cf" />

## Takeaway:
Promising results for small props taken up-close, with clean backgrounds and a user-defined mask; still limited fidelity for hero assets. Also, results appear to improve on subsequent re-runs.

### Notes:
 + Observed that defining a mask rotates source images 90 degrees CCW
 + Euler seemed like the best sampler model to use from limited trial set - further experimentation of the rest of the models is recommended
