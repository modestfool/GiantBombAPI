# GiantBombAPI
Search Engine for games supported on a given list of platforms.

## About
Switch is getting ready to make our office a little more fun by buying some vintage video games. We’re partial to old school Nintendo games, and we’d like to build a search engine to help us find old NES, SNES, and N64 games we love.
Giant Bomb API


You should use the Giant Bomb video game api as your data source for listings:
http://www.giantbomb.com/api/documentation#toc-0-15


Here’s a sample api call to get NES games:
http://www.giantbomb.com/api/games/?api_key=84e4fdf8957ddf84247c3ea012a4773ffead8156&format=json&offset=300&platforms=21


We want to be able to search for NES, SNES, and N64 games by title. You can use the offset and platforms parameters to fetch games in batches.
Functionality


You should create a program that fetches the data from the Giant Bomb api, indexes the entries (by name) and lets a user perform keyword queries to find the best matching video game listings. 


Your search engine should look up games by keywords, and return the corresponding name  and any other fun or useful information for the user, such as the description, site_detail_url, or an image_url.


Example Queries:
If our games include “Mario Tennis,” “Mario Party 4”, “Dr. Mario”, “Big Party: Super Mario Fun Time” and “Tetris Party”, these queries should return these games:


Input: ‘mario’
Output: ‘Mario Tennis’, ‘Mario Party 4’, ‘Big Party: Super Mario Fun Time’ and ‘Dr. Mario’,


Input: ‘party’
Output: ‘Mario Party 4”, ‘Tetris Party’, and ‘Big Party: Super Mario Fun Time’


Input: ‘mario party’
Output: ‘Mario Party 4’, ‘Big Party: Super Mario Fun Time’


Since we currently use Python3 for our backend, a solution written in Python is preferred.


The program could be a web app, a REST API, or even a simple command line program that accepts queries and prints the best matching results.


You should be able to demo your program against several real queries, describe the algorithm / data structures used, and walk through your code.


Imagine your project has to search over 1,000,000 results, how would your approach scale?
Requirements


Please do not use the Giant Bomb search endpoint (what fun would that be?) 


Please do not throw the results into SOLR / Elasticsearch, imagine those tools didn’t exist and you had to build a simple version on your own.


After initially downloading the data from the api feed, your solution should work without making any other external network requests. Your program should operate in two phases, one step where you download and index all of the game data from the API, and a second phase where your program is able to accept search queries and returns the matching games.


A good, scalable solution should NOT require a linear scan over all of the documents in response to each request.


You do not need to store the data in a database, a solution that creates an in-memory index is actually preferred. We’re looking for the data structures you choose for indexing and querying.


Your solution should support compound queries with multiple terms, i.e. “mario party.”
Bonus


For bonus points, implement a method for ranking the matching games to show most relevant games first.
