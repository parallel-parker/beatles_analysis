# beatles_analysis
An analysis of the Beatles as a band and as individual with data sourced from Spotify's API

SUMMARY:
This project seeks to uncover the answer to a question long debated in popular music: who is the most popular (or most important Beatle) - John Lennon or Paul McCartney.  With data analysis, we should be able to answer this question. Well… at least as far as Spotify listeners are concerned, that is, as we’ll be using data sourced from Spotify’s exhaustive and thorough API. Along the way, we will uncover insights such as how the Beatles’ music changes over time, how the Beatles’ solo careers measure in popularity and musical features to the bands’ catalog, and how musical decisions of the Beatles correlate to the music of their contemporaries, such as The Rolling Stones, The Beach Boys, and The Kinks.

MOTIVATION:
The Beatles are inarguably one of the most significant musical acts of the last century. Unlike most artists, who either perform music written by others or are guided by the songwriting of a single (or team) contributer, the Beatles are differentiated in that each of the four members - John Lennon, Paul McCartney, George Harrison, and Ringo Starr - contributed individually to the Beatles' collective catalog. While Harrison (and Ringo for the few songs he contributed) were rightfully credited for the songwriting credits, Lennon and McCartney famously credited all of their creations as simply 'Lennon/McCartney.' Fans of the Beatles recognize that despite this shared credit for the two primary members, each song is ultimately the primary creation of either one or the other. By sourcing insights from the superfans who have attempted to unpack this shared credit to its respective Beatle, we can build a dataframe that goes beyond the simple Lennon/McCartney credit, to attribute each item of the Beatles' catalog to a specific member.

This gets fun when we start to incorporate data from Spotify's API, which includes A.I.-generated metadata that attemps to measure musical features of the entire Spotify catalog. With this data in hand, we can evaluate the Beatles' individual contributions not only in terms of popularity, but also in terms of various musical features, to build character profiles of each member or track the development of these features over time.

DATA QUESTIONS:
To answer the guiding question - who is the more popular Beatle - we will rely simply on a popularity score average from Spotify, and we will also be able to offer extended answers to this question by considering the additional layer of the Beatles’ respective solo careers. In addition to this, metadata for Spotify tracks include such musical descriptors as tempo, liveliness, energy, valence (a variable to measure whether the song sounds happy or sad), acousticness, among other variables. These variables provide us with a lot of material to offer to discover the following: How do the Beatles' individually compare to each other in musical features; which musical features tend to correlate to greater popularity; how do these variable measures change overtime and fit with our understanding of the Beatles' history; how do these measurements correspond to the music of their peers.

DATA SOURCES: 
The primary song data is sourced from Spotify’s API (https://developer.spotify.com/documentation/web-api/). Additional data needed to assign each track to a specific bandmember is webscraped from a popular but unofficial Beatle's fan site: http://www.beatlesarchive.net/composer-singer-beatles-songs.html. The data from both sources will be combined into a single dataframe for easy analysis.

KNOWN ISSUES AND CHALLENGES:
The primary difficulty for this project is in selectively targeting, joining, and cleaning our data. Pulling specific albums and tracks we want in an organized manner from Spotify’s API proves tricky due to the multitude of different products available beyond the core discography. For instance, if our target is the album “Abbey Road”, we need methods to exclude the albums “Abbey Road - Deluxe Edition” and “Abbey Road - Extended Archive Collection”, not to mention all the varieties of greatest hits, live albums, etc. All of these non-essential albums would be undesirable and disruptive to our analytical goals, which is to examine only the key LP’s released during their existence as a band. The same precautions will be attempted for any additional catalog pulls, such as from the solo careers or contemporaneous musical groups, but we may not take as much pains to be as precise with these. 

Data cleaning will be needed to convey tidy results and more importantly to allow for the joining of data by using song names as our key. Due to how Spotify catalogs things, it is common to receive a result such as:

	Song name: “Yellow Submarine - Remastered 2015”
	Album: “Magical Mystery Tour (Remastered)”

We will need to remove the extra details from these titles to retain only the desired information to make joining our data possible:

	Song name: “Yellow Submarine”
	Album: “Magical Mystery Tour”

In addition to this essential cleaning, further cleaning can be done to provide presentable results. For instance, Spotify API data will list the key of a song, but lists it as a number value rather than standard musical notations. Our task would be to convert the “3” listed in key to something more understandable: “D Major”

Once the data is sourced and cleaned - the process of which can be followed in the attached Jupyter notebooks for Python 3 - the analysis will be faily standard.
