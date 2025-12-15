# Pixelated Shader

## Godot's Document
Just lemme read through real-ly fast. Treasure hunting time.

Read Intro is good enough (too much knowledge!):
https://docs.godotengine.org/en/stable/tutorials/shaders/index.html


https://docs.godotengine.org/en/stable/tutorials/shaders/introduction_to_shaders.html#shader-types

### Done
> Balanced input-output is the best.

### Leart (useful) 

### Leart (just curious) 
- https://www.youtube.com/watch?v=2ZK527cQbeo
- Ray casting:[ Möller-Trumbore algorithm](https://www.youtube.com/watch?v=fK1RPmF_zjQ)
    1. For each triangle, shoot a ray from the light source to the triangle
    2. Check if there are other triangles that intersect with the ray. Get the one with the minimal distance to the origin of the ray (i.e. the light source).
    3. Illuminate the one with the minimal distance (set shaded = false for the triangle)
    
    https://stackoverflow.com/questions/45896293/reducing-the-on%C2%B2-time-complexity-of-a-ray-casting-algorithm
    - $O(n^2)$ in step 2.
    - but with (1. Octrees, 2. Boundary-Volume Hierarchies (BVH), and 3. K-d-trees, ascending with implement complexity and execution speed) reduce search complexity to $O(\log(n))$, complexity can reduce to $O(n\log(n))$
      - p.s. Binary-Space Partition (BSP) is fastest but constructing BSP tree is too costly for one-off ray tracing renders

### Misc
[Back to Main Page](../index.md)