# The Moon
============

A photorealistic 3D graphics demo of our Moon written in JavaScript and WebGL
featuring real high-resolution satellite maps. 

Dependencies
------------

This demo uses the following open source libraries:

 * [**`mrdoob/three.js`**][three.js] - JavaScript 3D Graphics Library - WebGL
 * [**`sindresorhus/screenfull.js`**][screenfull.js] - Cross-browser
   wrapper for native JS Fullscreen API w/ simpler interface.

Credit
------

In order to create a photorealistic demo I set out to find the highest quality
public domain maps of the Moon available. I found out that there is good data
published through the Map a Planet initiative and available on the
[**USGS PDS site**][USGS]. The best data we have for our Moon was actually
gathered by the [**Clementine spacecraft**][Clementine]. It is possible to
process a greyscale image of the entire surface of our Moon using this data,
and as far as I know the best maps of the lunar surface we have today were
derived from this data. I was delighted to know that all this great data
available from USGS is public domain.

The best map I could find was processed by [**Jens Meyer**][Jens Meyer] and
apparently also darkened up by [**Steve Albers**][Steve Albers]. It and other
high quality maps can be found on Steve Albers homepage and available free for
personal non-commercial use. I say this map is the _best_ in the sense that it
has the highest resolution and detail compared to other maps I could find.

The original resolution of the map found on Steve Albers' homepage is
`8192x4096`. I am using a version scaled down in both width and height by
50% giving a texture at resolution `4096x2048`. I find this size suitable for
my demo.

My scaled down version is shown here:

[![Scaled Moon Map][scaled_map_thumb]][scaled_map]

Technical
---------

This demo is an example of using WebGL with the Three.JS JavaScript library.
GLSL shaders are used to create a material which is applied to the moon in
order to simulate diffuse light calculated for each vertex on the Moon mesh.
This allows the effect of the Moon changing phases. 

I also generated 6 randomized star patterns in order to create the skybox
around the scene, as well as generating a tangent space normal map from the
original high resolution map. I generated normal maps at both the original size
and the scaled verison.



