Learning tutorial from catlikecoding.com.

Tutorial: [https://catlikecoding.com/unity/tutorials/mesh-basics/](!https://catlikecoding.com/unity/tutorials/mesh-basics/)

## 1. Procedural Grid ##

> `What is a mesh?` Conceptually, a mesh is a construct used by the graphics hardware to draw complex stuff. It contains at least a collection of vertices that define points in 3D space, plus a set of triangles – the most basic 2D shapes – that connect these points. The triangles form the surface of whatever the mesh represents.

If you want to have a game object display a 3D model, it needs to have two components:
1. `Mesh filter`: This component holds a reference to the mesh you wish to show. 
2. `Mesh renderer`: You use it to configure how the mesh is rendered. Which material should be used, whether it should cast or receive shadows, and so on.

> `Why is there an array of materials?`
> A mesh renderer can have multiple materials. This is mostly used for rendering meshes that have multiple separate triangle sets, know as submeshes. These are mostly used with imported 3D models and won't be covered in this tutorial.

About UV
* Adding 2D texture coordinates to the vertices. The two dimensions of texture space are referred to as U and V, which is why they're know as UV coordinates
* These coordinates typically lie between (0, 0) and (1, 1), which covers the entire texture. Coordinates outside that range are either clamped or cause tiling, depending on the texture settings.

> `Why not use a single quad?`
> As we're creating a flat rectangular surface, we could suffice with just two triangles. This is absolutely true. The point of the more complex structure is that it allows more control and expression. Experiment!

## 2. Rounded Cube ##

## 3. Cube Sphere ##

## 4. Mesh Deformation ## 