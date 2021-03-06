# Note

This repo has been deprecated because I am rewriting the whole project from Go to JS. Because JS is more useful on the job market and I need NodeJS, React, and other JS things on my CV. Makes me sad.

The new version will be up soon.

# About

This project has been in development since March 2019.

On the surface, this project lets us have bots to explore the world.

What it also is, is a way for me to explore:

- what really is a bot
- how tech mediates between each of us and between us and the world, such as:
  - algorithmic bias
  - the collection and use of data
  - privacy and surveillance
- how I might contribute to open source software
- web development

While further off, I would like to explore if possible:

- how software is or should be priced
- the dynamics of the startup world

# Working details

This project is built with Golang 1.12, Leaflet, Mapbox, and SQLite (will switch to Docker + Postgres as the project matures).

Every 30 minutes, the program queries the OpenStreetMap (OSM) Overpass QL API for points of interests (limited to restaurants for now) within a limited radius of a bot. The bot picks one at random and moves to it. The bot's location is highlighted with a translucent green circle. The bot's next possible locations are highlighted as translucent red spots.

The program saves all visited points of interest to the database. It also refreshes the bots' next possible locations based on their GPS coordinates every 30 minutes.

Clicking on each point of interest shown on the map will display information about that point taken from OSM. This is meant to highlight what information is missing. At some point in future, I will work on how to encourage users to update missing information for OSM.

# Known problems

- Program is not deleting bot's next possible locations.
- Once bots land on the same spot, their next possible locations will be the same because they are using the same random seed. That's why it looks like there's only one bot now when there are actually two.
- Leaflet is not zooming into the bots' location.

# Directory structure

This project follows what I think is MVC, but also has a handlers part. Here are the main directories:

**root**

Contains main.go, which contains handlers. Handlers call the appropriate controller function for each page we visit.

**models**

Functions that interact with the database.

**views**

Functions that render templates.

**controllers**

Functions that combine models and views to produce application logic.

**static**

CSS, JS, and media files.

# Learning sources

## Leaflet
**Leaflet for maps**
https://leafletjs.com/

## Golang

**Intro to Golang templates**

https://www.calhoun.io/intro-to-templates/

**How to serve static files with Golang**

https://gowebexamples.com/static-files/

**How to interact with APIs with net/http**

https://medium.com/@masnun/making-http-requests-in-golang-dd123379efe7

**Replace vs. Replacer**

https://www.dotnetperls.com/replace-go

**User interface{} to quickly retrieve deeply nested JSON**

https://stackoverflow.com/questions/21268000/unmarshaling-nested-json-objects-in-golang

**Converting interface{} to other types**

https://tour.golang.org/methods/15

**Convert float to string**

https://yourbasic.org/golang/convert-int-to-string/

https://golang.org/pkg/strconv/#FormatFloat

**Concatenating strings**

http://herman.asia/efficient-string-concatenation-in-go

**Calculate distance between 2 GPS coordinates in km**

https://play.golang.org/p/MZVh5bRWqN

**json.Decoder vs. json.Unmarshal**

https://ahmet.im/blog/golang-json-decoder-pitfalls/

**Unmarshalling nested json into nested structs**

https://medium.com/@xcoulon/nested-structs-in-golang-2c750403a007

**Check if column exists in sqlite**

https://stackoverflow.com/questions/947215/how-to-get-a-list-of-column-names-on-sqlite3-iphone

**Update field if exists, else insert new row in sqlite3**

https://stackoverflow.com/questions/15277373/sqlite-upsert-update-or-insert/15277374

## MVC

**Example of MVC with Python**

https://www.tutorialspoint.com/python_design_patterns/python_design_patterns_model_view_controller.htm

## OSM

**API: Amenities**

https://wiki.openstreetmap.org/wiki/Key:amenity

**API: Around**

https://wiki.openstreetmap.org/wiki/Overpass_API#Around

**Query Overpass QL API from command line**

https://overpass-api.de/command_line.html

# About me

In this project, I present myself primarily as a new media artist. This is a convenient catchall term that associates me with a specific milieu.

For a little more detail, tongue-in-cheek: I am a new media artist working in the intersection of tech and the precarity of an unfortunately too often romanticised fully dystopian cyberpunk late capitalist neoliberal anthropocene.