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

> Unlike vertices, the number of triangles is simply equal to that of the six faces combined. It doesn't matter whether they use shared vertices or not.

**Doesn't this require more draw calls?**
```
Indeed it does, three instead of one. So what is more important to you, 
less vertices or less draw calls? It's useful to have a choice.

You typically want as few draw calls as possible. But it only matters if
 draw calls are the bottleneck. Dynamic batching can help you out as well.

Not having any duplicate vertices can be an advantage when you use them 
in expensive calculations, in which case less is better. Not having to 
deal with duplicates and seams makes algorithms a lot easier too.
```

**Why use the vertex colors?**
```
Using UV channels might make more sense, but we can only put 2D vectors 
in them while we need to store a 3D vector. We could use both the first 
and second UV channels, but then we have to split our data between two 
channels, which we rather avoid.

But tangent vectors are 4D and we're not using those anyway. Why not put
 the data in the tangent channel? The problem is that tangents – like 
 positions and normals – are defined in object space. This means that 
 they are almost guaranteed to be changed by Unity when any form of 
 batching is used, because batching combines multiple objects into a 
 single one. It might appear to work at first, but strange things will 
 happen once you have more than one rounded cube in your scene.
```

## 3. Cube Sphere ##

## 4. Mesh Deformation ## 