# 3D Animation (Blender) to Godot 

Comprehensive intro:  
https://www.youtube.com/watch?v=a0_JVEY7sbY

1. Godot 3D Animation Structure:
![alt text](3d_animation_to_godot/godot_structure_illustration.png)
    - **Rig Data**: how much mesh point transform from a bone (weight: 0-1, usually support 4 bones per vertex)
2. `Import Script` exists 
    - modify the source-file-to-imported-scene _before_ the scene is saved in `.godot/imported`


Export steps with Doucment: https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/importing_3d_scenes/available_formats.html
- [ ] 1. Enable Backface Culling in Blender's Materials tab
- [ ] 2. Export as `.glb` (or `.gltf` if want texture seperated from material)

Considerations for product-ready export:   
https://docs.godotengine.org/en/stable/tutorials/assets_pipeline/importing_3d_scenes/model_export_considerations.html#d-asset-direction-conventions