# Defold Spite Lines

This project was created from the "basic 3D" project template.

The simple aim of this method of rendering is to allow for a large number of drawn lines with a shader. 

The initial version of this uses Defold's game objects and makes many sprites. The sprites are rotated, colored and moved (and length provided) to position a quad (squashed to be a line). This method is simple and allows for a large amount of control for the lines. 

A new version (which I will put in another branch) will do all of the line drawing by populating a texture with data and rendering the lines entirely in the shader, in a single mesh call. This is a little more complex (since we need to know bounds and so on) but it should allow for very large numbers of lines to be drawn - Id expect in the 100's of thousands and maybe millions. 

## Why

The main use for this if for my own worldbuilder system that renders real world roads onto realworld landscape and urban data. I wanted something that could allow large 3D vistas across landscapes of a country, that included the urban areas and the roads. Doing this using traditional line drawing is _slow_. 

## Post Render method

I will be examining another method potentially, that uses a post render line drawing technique (a little like a software renderer) where the shader draws the lines over the whole screen (scene) and includes distance fogs, landscape occlusion etc. 

This method will probably only be tried of the above method fails to be decent performance. The benefits of a post render method is that the lines can be clipped and a bare minimum camera view of lines can be rendered. I expect I will be doing some of this in the above shader. This method tho, may be developed for web based rendering, because controlling the road rendering distance, quality and style in the web might be more performant. 





