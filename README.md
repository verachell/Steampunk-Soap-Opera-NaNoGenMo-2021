# Steampunk-Soap-Opera-NaNoGenMo-2021
Generates > 50000 words of soap opera style fiction in a steampunk setting  

## Steampunk Soap Opera
### Usage - how to run this program
Please note: This code requires that:   
- ```ruby``` is installed on your machine and  
- you have the ```yeetwords.rb``` file from the YeetWords repository (see below for where to get it and place it).  

To run this ad generator, first download the contents of this repository into your working directory. You will also need to download the ```yeetwords.rb``` file from the [YeetWords repository](https://github.com/verachell/YeetWords) (I used v 1.1.3 but any more recent version should also work) and place it at the same directory as ```soapopera.txt``` from this repository.

Then in your command line, type ```ruby yeetwords.rb soapopera.txt```

A file containing the > 50000 words story will be generated in markdown format.

### Features
- The story starts with the 5-6 main characters in one group, and then they split up into 2 groups where each group has a separate scene. Then the whole group gets back together to work on their invention.  

- Occasionally (every ~5000 words), one of the main characters dies. Then a new character arrives. Thus the group size remains constant. 

- Each character has their own job, item of dress, a quality (e.g. patience), and is carrying a mechanical part for the invention.

- Item/inventory tracking: the mechanical part carried by each character is "followable" - e.g. he/she may look at this item etc and it goes with that character, up until the point it is added to the invention. The typical pattern of adding an item to the invention is that a character will find a new mechanical part, but will decide to add his/her existing part to the invention, and will carry the new part for the subsequent occasion, and so on.

- Story-specific properties: each run of the program results in a different "biome" where 3 plants, 3 large animals, and 3 small animals feature predominantly (although not exclusively). The location of the invention is also story-specific. This location happens to be the last word in the story title, and tracks through the story with the group going there to work on their invention.

- At the end of the story, the characters board the invention and travel away with it.
