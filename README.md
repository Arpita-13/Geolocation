# Geolocation
Python+SQL project using the OpenStreetMap API with the database and data visualization on OpenStreetMap.
In this project, we use the free OpenStreetMap API (Nominatim service) to 
convert university names entered by users into geographical locations. Then we place the processed data on the OpenStreetMap map.

In terms of using the Nominatim service, there is an indication to agree to 
a maximum of one query per second. We divide our task into two phases.

In the first phase, we take our input from where.data and read it
them line by line while reading the server's geocoded response
Nominatim and store it in the database (opengeo.sqlite file). Before we use
Geocoding API, we check if we already have data for this particular one
line, so we won't be able to restart the program
they had to query the API a second time.

Run the geoload.py program. This program will read input lines from the file
where.data and check for each row to see if it's already in the database, and
if we do not have data for the location being processed, it will trigger an API query
geocoding to retrieve data and store it in SQLite.

After the data has been loaded into opengeo.sqlite, you can visualize it with
geodump.py. This program reads the database and writes the where.js file
containing locations, latitudes, and longitudes in the form
JavaScript executable. The ZIP file you downloaded already contains
where.js generated, but you can generate it again to check
operation of the geodump.py program.

To see the locations on the map, open the where.html file in your browser
website. You can hover over each map pin and click on it,
so as to find the location that the encoding API returned for the input
entered by the user. If you don't see the where.html file when you open it
no data, check if JavaScript is enabled in the browser or in
your browser's development console, check if there are any errors.


