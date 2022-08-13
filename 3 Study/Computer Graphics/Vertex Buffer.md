# Vertex Buffer
Everything is a triangle 

## Definition 
Just a buffer of memory that holds vertex data. It's on the GPU (VRAM). Contains way more data then just vertex positions.

Draw Call from CPU to GPU 

# Shader
## Definition
Way to tell the GPU how to use vertex data to draw. Run on GPU
Everything in OpenGL is have an ID.  
Two different shader can talk to each other.

1. Vertex Shader
	- Called for each vertex.
	- Tells OpenGL where to put the vertex on the screen space according to camera if it exist.
	- 5*5 
2. Fragment Shader (Pixel Shader)
	- Runs for each pixel.
	- Main Purpose is to define color of pixel.
	- very important for Lighting.
3. Geometry Shader
4. Compute Shader 
	- Heavy computing needs

First **vertex Shader** will be called then **Fragment Shader** will be called then rasterizations 

Use https://docs.gl 
# Vertex Attributes
## Definition
Tells how to use vertex buffer to draw the geometry.

# Index Buffers
[[3 Study/Computer Graphics/Drawing 2022-07-09 20.53.27.excalidraw]]

# Links
- [Where Do I Start? A Very Gentle Introduction to Computer Graphics Programming (A Gentle Introduction to Computer Graphics (Programming)) (scratchapixel.com)](https://www.scratchapixel.com/lessons/3d-basic-rendering/get-started)
- [Eric Arnebäck (erkaman.github.io)](https://erkaman.github.io/posts/beginner_computer_graphics.html)
- [Learning Modern 3D Graphics Programming (paroj.github.io)](https://paroj.github.io/gltut/)
- [3D Graphics with OpenGL - The Basic Theory (ntu.edu.sg)](https://www3.ntu.edu.sg/home/ehchua/programming/opengl/CG_BasicsTheory.html#:~:text=OpenGL%20adopts%20the%20Right%2DHand,counter%2Dclockwise%20(CCW).)
