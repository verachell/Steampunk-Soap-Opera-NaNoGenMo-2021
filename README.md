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

### Overview
The word data (in English) comes from 2 Gutenberg books:
- [Esperanto Self-Taught with Phonetic Pronunciation by William Mann](https://www.gutenberg.org/ebooks/23984) (using only the English words in there)  
- [Dolly Dialogues by Anthony Hope](https://www.gutenberg.org/ebooks/1203)  

The main words of the soap opera are from the English part of the Esperanto book mentioned above, while the dialogue is exclusively from Dolly Dialogues.

### Features
- The story starts with the 5-6 main characters in one group, and then they split up into 2 groups where each group has a separate scene. Then the whole group gets back together to work on their invention.  

- Occasionally (every ~5000 words), one of the main characters dies. Then a new character arrives. Thus the group size remains constant. 

- Each character has their own job, item of dress, a quality (e.g. patience), and is carrying a mechanical part for the invention.

- Item/inventory tracking: the mechanical part carried by each character is "followable" - e.g. he/she may look at this item etc and it goes with that character, up until the point it is added to the invention. The typical pattern of adding an item to the invention is that a character will find a new mechanical part, but will decide to add his/her existing part to the invention, and will carry the new part for the subsequent occasion, and so on.

- Story-specific properties: each run of the program results in a different "biome" where 3 plants, 3 large animals, and 3 small animals feature predominantly (although not exclusively). The location of the invention is also story-specific. This location happens to be the last word in the story title, and tracks through the story with the group going there to work on their invention.

- At the end of the story, the characters board the invention and travel away with it.

### Limitations
- The word groups used in this project did not necessarily have the same parts of speech, so sentences may not make a lot of sense.

- Although I have tried to minimize how much templating I was doing in this project, some level of it was necessary, particularly when removing or adding a character, and at the end.

### Credits
#### Dialogue
To extract the dialogue from [Dolly Dialogues by Anthony Hope](https://www.gutenberg.org/ebooks/1203), I used a shell script I created for this purpose which is available in [this gist](https://gist.github.com/verachell/c3497f6f29465b8346e9d0ee3ed0e721) which resulted in a file I called ```DialogAll.txt``` (not needed nor present in this repository). I then separated out that dialogue into 4 categories as follows:

- Separated questions with ```grep \?$ DialogAll.txt > DialogQ.txt```  
- Separated exclamations with ```grep \!$ DialogAll.txt > DialogE.txt```  
- Separated things that need to start "he/she said" with ```grep -E '\.$' DialogAll.txt > SaidDialog.txt```   
- Separated things that need to end "he/she said" with ```grep -E '\,$' DialogAll.txt > DialogSaid.txt```  

The 4 resultant files are placed in the ```Words```directory in this repository and these are the sole source of dialogue in the soap opera.

I've explained this process in case anyone wants to "play" with this repository and try it with a different source text for the dialogue, for example.

#### Words
Words were obtained from [Esperanto Self-Taught with Phonetic Pronunciation by William Mann](https://www.gutenberg.org/ebooks/23984). The first column was the English word, so I was able to simply grab these and ignore the Esperanto translation by using the Linux command cut. I was then able to put each category in a different file.

The ability of YeetWords to ignore leading and trailing blanks when doing auto-read-in of words was helpful, as the cut command left me with extra whitespace on each side that I didn't want to have to bother getting rid of.

#### Character names
Male and female character names were obtained from the [Top Names Over the Last 100 Years from the Social Security Administration of the USA](https://www.ssa.gov/OACT/babynames/decades/century.html), which at the time of downloading were from the years 1921-2020, and comprised the top overall 100 most popular names for each gender.

#### Sentences
I created the sentences myself, but I tried to minimize how many of my own words I was using in each sentence, with the idea that most of the words of the sentences would be substituted in from the word collection. Some sentences required extra templating, for eaxample removing a character, adding a character, and the ending.
