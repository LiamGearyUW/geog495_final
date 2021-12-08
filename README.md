# GEOG 495 Final Project: Particulate Matter by County

### Project Description

This project is an interactive web map featuring the counties of the 50 United States and Puerto Rico, as well as data on the levels of particulate matter in each county where such data is applicable. Particulate matter is a form of pollution that includes fine inhalable particles. Such pollution can enter the lungs and bloodstream, causing health risks.

On the left-hand side of the page, a sidebar contains more detailed information than the choropleth could provide, including a title, a prompt that shows the exact amount of particulate matter in the county which the user's cursor is hovering over, a legend, information on the National Ambient Air Quality Standards (NAAQS), and acknowledgements. In the upper-right corner of the page, a search bar allows the user to search for a specific location within the United States and Puerto Rico.

![Sidebar screenshot](/assets/img/sidebar.png "Sidebar screenshot")

Above is the sidebar. Its opacity was lowered so that the user could see portions of the map that would otherwise be obscured. 

The data classification method used for the choropleth map was equal breaks, starting at 0 and going up by 1.9 until reaching 12, at which point all values of 12 and above have the same color. I chose equal breaks simply because the range appeared in the data and is by far the easiest for the average person to understand. The reason I made 12 μg/m<sup>3</sup> the cutoff for the darkest hue is explained in the note below the legend: the NAAQS considers 12 μg/m<sup>3</sup> to be the maximum acceptable level of particulate matter.

![Map screenshot](/assets/img/map.png "Map screenshot")

Above is the map. The basemap style is Mapbox Light, chosen because the map uses political borders in the form of counties, making satellite basemaps unviable, and street basemaps aren't useful in this scenario. Mapbox Light also simply looks nicer than Mapbox Dark. The choropleth map's colors were chosen to be as intuitive as could be. Because only particulate matter concentration were to be mapped, different shades ranging from pale yellow to dark red fit well. Any amount of particulate matter is undesirable, regardless of whether the levels are below the NAAQS-set standards, so calmer colors like blue or green for slight amounts would be inappropriate. Gray is the natural choice for "No or Insufficient Data."

The legend itself offers a little more insight on what exactly is being mapped, meant specifically to inform those unfamiliar with the topic. Though typically referred to through its shorthand of "PM<sub>2.5</sub>" in EPA documents, the legend tells of what this shorthand refers to: particulate matter with diameters of 2.5 μm or smaller. 

![Geocoder screenshot](/assets/img/geocoder-example.png "Geocoder screenshot")

Above is a screenshot of the geocoder being utilized, with "University of Washington" having been searched for. I chose the geocoder for this map because I was working with counties. Aside from the county in which they live, the average person has little knowledge on which counties are where. A Seattleite may know where King County is, but have no clue about any of the other counties on the map. As another example, I have friends in various places throughout the country, but finding the exact city they live in becomes a hassle without the geocoder, especially when state lines are technically there but difficult to make out. The geocoder and associated marker allows the user to pinpoint the exact county they're interested in viewing. 

### Project Goal

Initially, the goal for this project was simply to show the levels of particulate matter found in each county. However, as I came across the data for levels of particulate matter by county, what struck me the most was the lack of it. While one could theoretically piece together a national trend (by looking at the map, one can see high concentrations of particulate matter in the Pacific Northwest and the Midwest), but such connections would be loose at best. Entire states, such as California and Colorado, have no county data in the EPA's database. I shifted my goal accordingly: rather than showing just where particulate matter is, I also wanted to show where data on particulate matter levels isn't. The lack of county data makes spotting regional and state-wide trends difficult, and I wished to illustrate that through the use of the gray space indicating no or insufficient data, which takes up the overwhelming majority of the country's area. If there are two things I hope a user would take away from this project, it's the lack of data on particulate matter by county, and the worrying levels of particulate matter in certain areas. 

### Acknowledgements and Data Sources

Hosted on GitHub

Basemap is Mapbox Light, obtained from Mapbox: ["Styles"](https://docs.mapbox.com/api/maps/styles/)

Geocoding API obtained from Mapbox: ["Geocoding"](https://docs.mapbox.com/api/search/geocoding/)

Particulate matter information obtained from EPA: ["Particulate Matter (PM) Basics"](https://www.epa.gov/pm-pollution/particulate-matter-pm-basics)

Air quality data obtained from EPA: ["Air Quality - Cities and Counties 2020"](https://www.epa.gov/air-trends/air-quality-cities-and-counties)

NAAQS information obtained from EPA: ["National Ambient Air Quality Standards (NAAQS) for PM"](https://www.epa.gov/pm-pollution/national-ambient-air-quality-standards-naaqs-pm)

US counties obtained from US Census Bureau: ["Cartographic Boundary Files"](https://www.census.gov/geographies/mapping-files/time-series/geo/carto-boundary-file.html)