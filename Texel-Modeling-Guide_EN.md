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
	> todo
12. What are the Texel guidelines?
	> todo
13. What should I avoid when modelling in Texel?
	> todo
14. How can you make accurate wires?
	> todo
15. Do these Texel rules apply to RoW's Texel rules?
	> todo
