# Pixelated Shader

## Godot's Document
Just lemme read through real-ly fast. Treasure hunting time.

Read Intro is good enough (too much knowledge!):
https://docs.godotengine.org/en/stable/tutorials/shaders/index.html


https://docs.godotengine.org/en/stable/tutorials/shaders/shader_reference/shading_language.html

### Done
> Balanced input-output is the best.

> **Output always is the first.** 先鎖後鑰!
### Leart (useful) 

https://docs.godotengine.org/en/stable/tutorials/shaders/your_first_shader/your_first_2d_shader.html#your-first-vertex-function 

> All objects derived from a `CanvasItem` have a material property. They also have an option to *inherit their parent's material*. This can be useful if *you have a large number of nodes that you want to use the same material*.

Range of built-in variable:
- `COLOR`: $[0,1]$
- `UV`: $[0,1]$
### Leart (just curious) 
- https://www.youtube.com/watch?v=2ZK527cQbeo
  - 
- Ray casting: [Möller-Trumbore algorithm](https://www.youtube.com/watch?v=fK1RPmF_zjQ)
    - Barycentric Coordinate: describe a point by weight of trinagle vertices vectors
      - e.g. `(1, 0, 0)` is `vertex1 *1 + vertex2 *0 + vertex3 *0`, where `vertexi` are vertices' position 
    - Scalar Triple Product:
      $$
      (a \times b) \cdot c
      $$
      - $a \times b$: a,b parallelogram area
      - $(a \times b) \cdot c$: area $\times$ hight $c \cos \theta$ = volume of a,b,c
    - [Cramer's Rule](https://www.youtube.com/watch?v=jBsC34PxzoM)
      <!-- $$
      \begin{bmatrix}
          \cos \theta & -\sin \theta \\
          \sin \theta & \cos \theta \\
      \end{bmatrix}
      \begin{bmatrix} x \\ y \\ \\]end{bmatrix} =
      \begin{bmatrix} x' \\ y' \\ \end{bmatrix}       
      $$
      - can think as transforming `x,y` to `x',y'` (map every `x,y` in `(1,0)(0,1)` space to `(cos sin)(-sin cos)` space with values shown in `(1,0)(0,1)` space)
      $$
      x = \begin{bmatrix} \cos \theta \\ \sin \theta \\ \end{bmatrix} \cdot
          \begin{bmatrix} x' \\ y' \end{bmatrix} 
      $$
      - recover how much `(cos sin)` in `x',y'` aka `x,y` ONLY when `(cos sin)` $\perp$ `(-sin cos)` AND they are unit vectors. -->
      $$
      A\vec{x}=\vec{x'} \\
      \begin{bmatrix} \vec{a} & \vec{b} \end{bmatrix}
      \begin{bmatrix} x \\ y \\ \end{bmatrix} =
      \begin{bmatrix} x' \\  y' \\ \end{bmatrix} 
      $$
      - vectors in `(1,0)(0,1)` space transformed to $\vec{a},\vec{b}$ space ($A$'s column space)
      - [3b1b](https://www.youtube.com/watch?v=Ip3X9LOh2dk): it scales area(volume) by $|\det(A)|$
        - In 2D: $|\det(A)|=|\vec{a} \times \vec{b}|=|\vec{a}||\vec{b}|\sin\theta =$ area formed by new basis vectors
        - In 3D: $|\det(A)|=|(\vec{a} \times \vec{b}) \cdot \vec{c}|=|\vec{a}||\vec{b}|\sin\theta_{ab}|\vec{c}|\cos \theta_c =$ volume formed by new basis vectors
        - $\det(AB)=\det(A)\det(B)$: whole area change = $A$'s area scales on bases of $B$ (effectively $B$'s area scale) and scale area by new $B$'s scale  
      $$
      A\vec{x}=\vec{x'} \\
      x_x=\frac{\begin{vmatrix} \vec{x'}& \vec{b} & \vec{c} \end{vmatrix}}{\det(A)} \\
      x_y=\frac{\begin{vmatrix} \vec{a} & \vec{x'}& \vec{c} \end{vmatrix}}{\det(A)} \\
      x_z=\frac{\begin{vmatrix} \vec{a} & \vec{b}& \vec{x'} \end{vmatrix}}{\det(A)} \\
      $$
      $\begin{vmatrix} \vec{x'}& \vec{b} & \vec{c} \end{vmatrix}$ is volume of $\vec{x'}$ with new basis vector $\vec{b},\vec{c}$. Divide $\det(A)$ to get original volume of $\vec{x}$ with origin basis $(0,1,0)(0,0,1)$, which is $x_x$!

    https://stackoverflow.com/questions/45896293/reducing-the-on%C2%B2-time-complexity-of-a-ray-casting-algorithm
    1. For each triangle, shoot a ray from the light source to the triangle
    2. Check if there are other triangles that intersect with the ray. Get the one with the minimal distance to the origin of the ray (i.e. the light source).
    3. Illuminate the one with the minimal distance (set shaded = false for the triangle)

    - $O(n^2)$ in step 2.
    - but with (1. Octrees, 2. Boundary-Volume Hierarchies (BVH), and 3. K-d-trees, ascending with implement complexity and execution speed) reduce search complexity to $O(\log(n))$, complexity can reduce to $O(n\log(n))$
      - p.s. Binary-Space Partition (BSP) is fastest but constructing BSP tree is too costly for one-off ray tracing renders

### Misc
[Back to Main Page](../index.md)