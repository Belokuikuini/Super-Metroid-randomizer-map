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
	
 Also, a few tiles have been edited from vanilla to make randomizer more acessible :
 
	- In red Brinstar, the bottom of red tower now has a platform to allow wall-jumping to escape from Norfair
	- In Norfair, the Cathedral entrance has been modified to allow wall jumping to acess Cathedral without Hi-jump
	
----------------------------------------------------------------------------------------------------------------------------------------

 After some thought and planning, and using VARIA's tracker, I have decided that just making a map would be kinda useless, since the tracker takes care of the aforementionned problems in a case by case fashion.
 Therefore, I will instead write a beginner's guide to Super Metroid Randomizers, illustrated with said maps. It seems elusive at first, because of the random nature of the games.
 However, there remain a few constants when playing, such as getting started on the seed, passing certain rooms, tricks to be used, and finally, the most important skill that comes into playing a randomizer, being able to analyse your current
 items and what next checks they give you access to. Besides, a glossary containing most of the vocabulary used wouldn't hurt either
 
 As for the maps, I have decided that they should stay, but more as an illustration tool than the main gig. I have also realized rather quickly that PHP would be very impractical for the purpose of an interactive map, so I will have to teach
 myself some javascript for my map. It might also be best to use images for tiles instead of html blocks, because some of them are way too finneky.
 The base framework still stands though, and hopefully will be taken into account by javascript if it can do OOP.
 
 For this new goal, I will have to get started on creating a base site that will contain the articles and maps. I'm still undecisive on how to split guides, maps and tricks, and how to weave them together in some sort of coherent guide, but i can
 already get started on the main aspect of the site, how it will look, function, and how an user can navigate through pages, articles, zones, etc...
 I might also be able to write a few articles on practical advice, like how to randomize a ROM, what emulators to choose from, how to hook a controller to the emulator, etc... Although a lot of it will be refering to my personnal experience,
 I can link external tutorials on the subjects.