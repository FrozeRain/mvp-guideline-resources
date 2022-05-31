## How do you start modelling in Texel?
1. How do you change the settings and what should the settings be changed to allow the optimal way of modelling in Texel?
	> To start modeling in texel you need to set up the scene in Blender. As we know that 1 m in Blender = 16 texels in MC, we need to use _Scale_ value = 1 / 16 = 0.0625 m
	> 
	> ![_Scale 0.0625_](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/scale_0.0625.jpg)
	> 
	> Or we could use _Scale_ value = 1m to easily determinate edge / polygon length. (_I'm prefer this method_)
	> 
	> ![_Scale 1_](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/scale_1.jpg)
	> 
	> **But before export final model we should downscale entire model on 0.0625**
2. What kind of tools should be used when modelling in Texel?
	> For texel modeling, you only need to know all the basic Blender tools, i.e. select, extrude, scale, knife, etc.
3. How can I make my Texel model snap to the grid and be as accurate?
	> Since we set the _Scale_ value in our scene, in order to snap the move tool to the grid, we need to use the **Snap** option with _Increment_ parameter.
	> 
	> ![Snap option](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/snap.jpg)
	> 
	> It allows to move any objects in your scene on static value which you set up in _Scale_ field.
4. What breaks Texel rules, even if you're modelling it in that style (other than the wheels)
	> The first thing you should be take care of is **Edge length**.
	> to check out edge length on any object select any edge with specific checkbox enabled:
	> 
	> ![Edge length](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/edge_length.jpg)
	> 
	> It uses to avoid incorrect mesh unwrapping with _snap to corner_ UV option. Here are some examples of bad practice:
	> 
	> ![Wrong texel](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/wrong_texel.jpg)
	> 
	> In this case the edge length could be round to 2 on UV map, but more efficient to stretch edge on mesh itself.
	> 
	> ![Possible OK](https://cdn.discordapp.com/attachments/882193338483220521/973923309798453258/unknown.png)
	> 
	> Next case in Blender's made curve parts like that:
	> 
	> ![Blender's curve](https://cdn.discordapp.com/attachments/882193338483220521/973916915514875945/unknown.png)
	> 
	> **Note:** It's ok when you are trying to round an object that has previously been polygonized into 1x1 texels, such as hoses, wires, etc. 
	> Solution: **Do not use Blender's method** . To round any parts you can manually split it on _rotation element_ with correct edge length and then rotate each of it:
	> 
	> ![Correct round](https://cdn.discordapp.com/attachments/882193338483220521/976201781363216464/unknown.png)
	> 
	> Also you could use a half of texel for some small details, decorations, cab's control elements:
	> 
	> ![Half texel](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/half_texel.jpg)
	> 
	> It is also allowed to use a 0.1 texel height plane for those specific and rare cases where even half of the texel is very tall / wide:
	> 
	> ![Texel plane](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/plane.jpg)
	> 
	> **TODO**
5. Is there a way to accurately see the height and width of your model?
	> todo
6. How can I scale a picture to be just right for Texel modelling?
	> todo
7. How can you use pictures of the train's/wagon's blueprints in order to accurately model?
	> todo
8. How do you connect the bogies and other parts to the train to the main body without it looking too messed up or floating?
	> todo
9. Can you stick to a certain accurate grid when modelling? How?
	> todo
10. What do you absolutely need to know before starting to model in Texel? 
	> todo
11. How can you accurately unwrap and texture? (I know, it can be done after watching some tutorials, but if you feel like it then answer, if you want.)
	> Unwrapping is both the simplest and the most time-consuming part of modeling.
	>
	>  Let me explain on this example. We have cube with 2x2x2 texel sides:
	> 
	> ![Unwrap 1](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap1.jpg?raw=true)
	> 
	> First, we need to select the edges along which we will cut this cube. (I guess youtube very help with it ( ͡° ͜ʖ ͡°) )
	> 
	> ![Unwrap 2](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap2.jpg?raw=true)
	> 
	> After selection go to [UV] -> [Mark Seam] to notify Blender about our cut edges.
	> 
	> Then create new _Material_ for your object and now we can create new texture and assign it on our _Material_
	>
	> ![Unwrap 3](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap4.jpg?raw=true)
	>
	> Also it very helps if you change type of new image on _Color Grid_:
	>
	> ![Unwrap 4](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap5.jpg?raw=true)
	>
	> Then, when you are ready to unwrap, select entire object in edit mode and go to [UV] -> [Unwrap] (ye, it's really so simple ¯\\\_(ツ)_/¯):
	>
	> ![Unwrap 5](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap3.jpg?raw=true)
	>
	> It's also recommended to set up Unwrap method as _Conformal_ to achive best proportions:
	>
	>![Unwrap 6](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap6.jpg?raw=true)
	> 
	> And **Woooah!** Your cube is **UNWRAPPED** \\(ᵔᵕᵔ)/
	>
	>  ~~But wait, it has wrong scale!~~
	>
	>![Unwrap 7](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap7.jpg?raw=true)
	>
	> To fix that i've use _TexTools_ Blender addon. It allow you to specify **Texel size** (Pixels per 1 unit ratio). I'm set **1.0** here, because on 3D scene settings i've set _Scale_ value as **1.0** (by default 1 Blender unit = 1m). 
	>
	>  **NOTE:** If you modeling with common Minecraft scale (_Scale_ value set as 0.0625) then you should use Texel size = **16.0**, coz 0.0625 * 16 = 1 !
	>
	>  After set up correct **Texel size** you can select all UV islands click _Apply_ button:
	> 
	> ![Unwrap 8](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap8.jpg?raw=true)
	>
	> Now it looks perfect! **UwU**
	>
	>  To move your new UV island by pixels use _Snap to Pixels_ UV option:
	>
	>![Unwrap 9](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap9.jpg?raw=true)
	>
	> ***Congratulations!!!*** 
	>
	>  Now you learn how to unwrap texel-style objects! 
	>
	>![Unwrap 10](https://github.com/FrozeRain/mvp-guideline-resources/blob/main/unwrap10.jpg?raw=true)
	> 
	> However, the time-consuming is that it is a long monotonous process that requires more attention. It depends on how smoothly the textures will lie and how they will look in the game.
	> ![Unwrap 11](https://preview.redd.it/lr5kdzqr0ve31.jpg?auto=webp&s=ccc7304f5775de75c893cb1b7cfe6384e08ee5b6)
12. What are the Texel guidelines?
	> - No free movement / scale objects
	> - Move / Extrude / etc objects only on **Increment** value
	>   - For uncommon _Move_ cases:
	>     + 0.5 texel (1/2 texel);
	>     + 0.25 texel (1/4 texel);
	>   - For uncommon _Extrude_ cases:
	>     + 0.5 texel (1/2 texel);
	>     + 0.1 texel (1/10 texel);
	> - Rotate existing texel objects as you want.
	> - Think in advance how each texel of the mesh will unwrap on each pixel of the texture.
	> - Try to use the most common shapes such as:
	>   - Plane
	>   - Cube / Parallelepiped
	>   - Triangle
	>   - Trapezoid
	> - Use your imagination within limits. =D
13. What should I avoid when modelling in Texel?
	> todo
14. How can you make accurate wires?
	> To make wires or any flexible parts you could use Blender's _Bezier_ object as modifier. Just place _Bezier_ as you need and apply to object to be bent. [See how do it!](https://www.youtube.com/watch?v=oHkzyH9dpv4&ab_channel=GamemakerGameProgrammingCourse)
	> 
	> ![Bezier](https://raw.githubusercontent.com/FrozeRain/mvp-guideline-resources/main/bezier.jpg)
	> 
	> **NOTE: Your object must be pre-divided into 1x1x1 texel polygons!**
15. Do these Texel rules apply to RoW's Texel rules?
	> Of course, RoW's Texel rules applicable to the MVP, just as the MVP rules applicable to the ROW. But in MVP we trying to avoid _voxel-like_ parts, except wheels.
