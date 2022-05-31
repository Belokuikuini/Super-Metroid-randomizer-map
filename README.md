# Super Metroid randomizer map
 An interactive Super Metroid map, designed specifically with randomizers in mind
 
 The aim of this project is still ambiguous for now. I had this idea at like 4 A.M during insomnia and it just stuck with me after I woke up, so it musn't be that bad.
 I have still searched the web for potential guides that may already exist on the topic, and I did find helpful resources for randomizers, that I will list below ;
 
	- The Super Metroid Speedrun wiki page about randomizers : https://wiki.supermetroid.run/Item_Randomizer
	- An interactive Super Metroid map with all item types, locations, room information, and any% PRKD route guide : https://bin0al.github.io/Super_Metroid_World_Map/leaflet.html

 With that in mind, I am using VARIA randomizer for reference, as it seems to be the most widespread and complete randomizer I could find. Here is a link to their homepage : https://randommetroidsolver.pythonanywhere.com/
 Their page has tons of useful information that I will mark on the map, while making it as readable as possible.
 I don't think this map will be detailed for each tile , because that would be beyond my abilities as a developper. It will use the regular Super Metroid map style, with a few adjustments for details such as :

	- Major / minor item distinction
	- The use of tricks, varying in difficulty
	- A different color for heated rooms, and if possible the minimum amount of E-tanks to cross hellruns (not accounting for crystal flashes)
	- Hard item requirements for certain passages / Items making the passage much easier
	
 To allow more prcision, the map will be split into several zones, according to the VARIA randomizer splitting, and not vanilla splitting ;
 Elevators themselves are not randomized, but their doors are if area randomization is enabled. That is also why I have split the world map.
 For instance, Brinstar has been split between these areas :
	- Blue brinstar is attached to Crateria
	- Green and pink Brinstar are one separate zone
	- Red Brinstar and Kraid's lair are standalone areas (The glass tube is still considered part of red Brinstar, but getting to Norfair elevator is considered a warp)	
 For more information about area splits, it is best to directly refer to the map : https://randommetroidsolver.pythonanywhere.com/tracker
 
 What I hope to bring to the table with this project is to ease the search of information for beginners. All of the sites that I have listed are extremely helpful, informative, and intuitive,
 but I fear someone with little experience with Super Metroid tricks may feel overwhelemed having to cross-reference several guides for help. That's where my map comes in.
 Hopefully, I can provide a tool for beginners to see what they can or cannot do given their situation, which items they have, and which tricks they know / need to learn how to use in order to progress.
 
 This tool will probably take the shape of a website, not only for accessibility, but also for technical reasons : html and css already provide a great graphical framework for GUI, and php can take care of the processing.
 Besides, I may not know Javascript at the moment I'm writing this, but it should be a great learning oppotunity. Although I think most of it can be done in PHP.
 Since the site should not require dynamic information updates, it shouldn't need a database, making hosting and developping much easier.
 That being said, I should still make a stable framework for map displays alone, not counting for iconography and supplementary notes.
 
 I already have a few ideas for the base map framework, that I am going to write down here ;
 
	- Each map will of course be a plane. It will be a discrete field of tiles, the origin being at the top left corner and plane vectors going right and down, same norm, and orthogonal. This will make the coordinate system, starting at 0.
	- Each tile will be a square whose side length total will amount to a fixed value in pixels
	- Tiles will have specific attributes to them ;
		> Right | up | left | down borders
		> Heat / No heat
		> No item / minor item / Major item / Several items (edge cases)
		> Associated room name and info, linking to speedrun wiki page
		> Associated trick, linking to speedrun wiki page
		> Transition destination (If there is one)
		> Unique coordinates
	- Elevator tiles will be a peculiar case, as their shapes aren't exactly square. I will have to get crafty with css...
	- All elevators will have a vertical corridor with a length of 3 tiles
	- Ideally, clicking on a zone transition tile will lead to the map of the next zone (elevator tiles will recieve the same treatment)