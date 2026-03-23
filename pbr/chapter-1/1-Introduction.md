## Photorealistic rendering and the ray tracing algorithm
Though light is a very complicated subject in modern physics, especially quantum physics, for our purposes we'll use the equations developed between the 16th and 19th century that model light as a particle that travels along rays. 
This leads to a more efficient computational model based on the key concept on *ray tracing*.
<r>
The main idea of **Ray tracing** is simple, we'll simply follow each light ray as it bounces across the scene when intercating with objects. There are many ways to write a raytracer but it always needs to take into consideration:
- Cameras
- Ray-object intersections
- Light sources
- Visibility
- Light scattering at surfaces
- Indirect light transport
- Ray propagation

## Cameras and film
<img width="821" height="338" alt="imagen" src="https://github.com/user-attachments/assets/9aae713b-3756-4602-9aba-9cd5004ae250" />

Now we have a critical issue in rendering: at each point in the image, what color does the camera record? This question is partially answered by what is visible in the camera, above there is a diagram of the pinhole camera model, where we can see that only vectors that travel through the pinhole are "rendered" in the scene. We will go on detail about this later.

## Ray-Object Intersection
Each time the camera generates a ray, the first thing the renderer does is determine which object (if any) the ray intersects with. To find the intersection we must test the intersection of the ray with every object in the room and pick the first one. This will be done with the following equation:

Given a ray $r$, we'll start writing it in it's parametric form:
```math
r(t) = o + t\mathbf{d}
```
where $o$ is the ray's origin, $\mathbf{d}$ is the direction vector and $t$ is a parameter such that $t \in [0,\infty)$



