Can we measure sexism by analyzing lyrics?
==========================================================
Presentor: Julie Lavoie
Author: Dan Hoizner

#The Data

* 32 Artists
* 50-150 songs each

#East vs West

* East
    - NY: birthplace of hip-hop
    - verbal cleverness, virtuosity
    - beat is repetitive, lyrics are the focus
* West Coast
    - started in NY, spread to LA
    - jealousy, rap feuds
    - crack, gangsta rap
    - aggressive, violent lyrics
* Dirty South
    - crunk/trap
    - most recent
    - club-oriented
    - emphasis on beat, high energy, lyrics secondary

#Let's Get Some Lyrics

1. download HTML
2. extract lyrics
3. count

Each artist has an index page with a list of songs.
Each song has a page of lyrics.
View source -> 1500 lines of HTML, care about 40.

`BEAUTIFUL SOUP + URLLIB + `!!

**NOPE**!
only get 20 files for each artist :(.
*99 problems, autoscroll is the first one*. As events trigger, more songs get loaded via ajax...figure out where the request is going.

important: perfect vs done
writing scraper vs getting rap lyrics
**FIREFOX PLUGIN \o/!**

#Turning HTML into Lyrics

* for each artist, we have a directory with a bunch of html files
* tools
    - beautiful soup
    - pattern
* getting things out of a div

# Counting B****

* re.findall
* average over number of songs

Is this a good metric for sexism?
Artists like Biggie and Eminem, with very violent lyrics towards women score low compared to the average.
They have more vocabulary to describe worse things.

HALP!
not sure what to do next...play with data, look for useful patterns.

Look at the 20 most common words.

#Issues in parsing rap vs other text
* stop words = common words we don't care about
* rap has a lot of slang, so we need new stop words
    - ya
    - dem
    - yo
    - huh
    - cmon
    - dat
* nicknames
    - need to be added to stop words
* guest rappers
    - common to have guest rappers or many different rappers
    - name attached to each verse
    - wu-tang top 20 was all names
* stemmers and slang
    - counting "apple" with "apples"
    - problem with slang

#What makes one artist different?

* Are there words only one rapper say? Exclude the top 20 words in all of rap.
* Socially conscious rappers all have 'people' as their top word.

#Where to take it?

* proximity search with n-grams
    - splitting text in windows on `n` words
    - does a word for 'women' occur within `n` words of violent word?
    - Note: this is super depressing
