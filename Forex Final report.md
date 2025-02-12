Task Background: 

We're arranging multiple cruising aircraft robots in the forests of Finland. They have functions of drawing topographic maps and identifying different types of trees and plants. They're mainly used to mark the location of bilberry and strawberry bushes on the map and help farmers locate picking spots. 



Task Overview: 

Due to the complex terrain of the forest, we need to first create a forest environment in gazebo to test whether the robot can accurately and efficiently perceive the terrain and draw a map of the entire forest while avoiding obstacles such as trees and rocks. To do so, we studied typical forest layout examples, created models of common forest elements with blender, and generated a forest terrain using a grayscale height map. Unfortunately, my laptop didn't work well enough to run the simulation test, but the next step should be to actually plant the models, according to the example forest layout pattern, on the terrain, and run the simulation. 



Steps:

1. Study the layout of typical forests

The forest terrain needs to be as realistic as possible for the drones to accurately operate in a real environment. Therefore, I studied from existing forest layouts to find simple patterns of how the forest environment should be:

	What are the various types of trees? How many regions would they occupy in the terrain? What would the density be in each region?
	Where could the bilberry bushes be located?
	Will there be any houses, rocks, water and other elements?


2. Using blender: create models of forest elements.

Then I used blender to make the models, which include several types and species of trees, a log cabin, rocks, grass, and most importantly, berry bushes. Although the original models were found on free sites, I unified all the format to .dae, modified them to be in correct scale and different height, able to represent various characteristics of my forest.

This was the blender plugin that I used: https://github.com/david0429/blender_gazebo


3. Generating terrain from a grayscale height map

I used this github code to generate the forest terrain from a grey-scaled heightmap I found online: 
https://github.com/MatthewVerbryke/gazebo_terrain

The parameters I applied were 513 pixels, length and width 100m (10000 square meters) , maximum height 8m, hopefully large enough to represent a real forest. But once I set the terrain in gazebo, processing speed on Virtualbox delays significantely. Changing the terrain to a smaller size didn't reduce the impact either, the problem could be Virtualbox not using nvidia graphics card, which was left unsolved. As a conclusion, I wasn't able to plant all the models and continue the task. I only managed to plant a small corner of the terrain (named as forest.world) before it shut down unexpectedly. 



What can be done after: 

Finish planting all the models on the terrain according to the previous studied pattern, and evaluate the multi-UAV collaborative mapping setup. There could also be possibility to extend the scenario with rendering engines for more photorealistic graphics. AI could also be adopted to determine forest patterns statistically and auto-generate terrains that are more realistic.
