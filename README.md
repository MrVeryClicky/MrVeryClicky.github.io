<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Display a map on a webpage</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v3.3.0/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v3.3.0/mapbox-gl.js"></script>
<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
#overlay {
    position: absolute;
    top: 70px;
    right: 10px;
    background-color: bisque;
    padding: 10px;
    border-radius: 5px;
	z-index: 1;
}
#overlay2 {
	position :absolute;
	top: 10px;
	right: 10px;
	background-color: bisque;
	padding: 8px;
	border-radius: 5px;
	z-index: 1;
	font: 18/24px 'Helvetica Neue'
}
</style>
</head>
<body>
<style>
	.mapboxgl-popup {
	   width: 500px;
	   border-radius: 15px;
	   background-color: #923d1e;
	   font:
		12px/18px 'Helvetica Neue',
		Arial,
		Helvetica,
		san-serif; 
}
.mapboxgl-popup #amusement-park {
	color: red;
}
	.mapboxgl-popup-content img {
		width: 220px;
		height: auto;
	}


</style>
<div id="map">
	<div id="overlay"> <a href="Gallery fixed.pdf" target="_blank" title="opens in a new window">  Extra Images Gallery</a> </div>
	<div id="overlay2" <p> <strong>Forgotten History of Canberra </strong> </p> </div>
</div>

<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoibXJjbGlja3kiLCJhIjoiY2xzanFvdXZtMmxpMTJqbzBlcDI4Z2NyeSJ9.MiEmeJjNgosNIi3Q5gMJJA';

	const bounds = [
		[148.69, -35.73],
		[149.36, -35.11]
 	];

   const map = new mapboxgl.Map({
        container: 'map', // container ID
	style: 'mapbox://styles/mrclicky/clvxhnyva01sc01rj28qlgvk8',
        center: [-210.9, -35.3], // starting position [lng, lat]
        zoom: 10, // starting zoom
	maxBounds: bounds // Set the map's geographical boundaries
  	  });

   map.on('load', () => {
	map.addSource('places', {
	'type' : 'geojson',
	'data': {
	'type' : 'FeatureCollection',
	'features' : [
	{
			'type' : 'Feature',
			'properties' : {
				'description':
			'<strong> Air Disaster Memorial</strong><p>The Air Disaster Memorial is located in a small clearing in a pine forest off Pillagio Avenue. It was built in 1952 to commemorate a plane crash that occurred in 1940. A Lockheed Hudson crashed before landing at Canberra Airport, killing all of its passengers.</p> <img src="Air Disaster Memorial/memorial.jpg" /> <p>The passengers included the Minister for the Air, and the Minister for the Army as well as multiple other influential figures of the time. The plane crash had an effect on the war (WWII) due to the loss of influential figures in the Australian government. The location felt abandoned, with rumors circulating online that it’s haunted if visited at night. Despite these rumors my visit seemed normal.</p>',
	'icon' : 'Air Crash'
	},
	'geometry' : { 
	'type' : 'Point',
	'coordinates' : [149.22931, -35.31852]
			}
	},
	{
			'type' : 'Feature',
			'properties' : {
				'description':
			'<strong> Duntroon Dairy </strong> <p> The Duntroon Dairy is the oldest still standing building in Canberra. Part of the Duntroon estate, it was built to supply dairy products to the people living on the Limestone plains. The dairy had a innovative design to keep its products cool, such as a cool well leading into a natural spring and a heat area funneling up into the ceiling. The building was still in use up until the mid to late 20th century. Interestingly enough, one of the inhabitants of the building is the only person who lived on the Mugga lane ruins that I could find.</p> <img src="Duntroon Dairy/IMG_2054.jpg" />',
	'icon' : 'Dairy'
	},
	'geometry' : { 
	'type' : 'Point',
	'coordinates' : [149.15637, -35.301194]
			}
	},
	{
			'type' : 'Feature',
			'properties' : {
				'description':
			'<strong> Canberra Glassworks</strong> <p>I’m sure most people who live around the southside of the city will know of this location. The Canberra Glassworks is a large, impressive building with a lively market at the nearby old bus depot every Sunday. Yet, despite this, few people understand the building’s historical significance in the early days of Canberra’s life. The Glassworks was one of the largest buildings when it was first constructed in 1915 and, using coal powered steam turbines, generated power for all 1,000 ACT residents when it first opened. By 1936, the station was connected to the NSW electricity grid, meaning that it was no longer solely responsible for Canberra’s electricity. </p> <img src="Eastlake Powerstation/power.jpg" /> <p> After shutting down from its original use in 1957 the building was converted into a glassworks. </p>',
	'icon' : 'Powerstation'
	},
	'geometry' : { 
	'type' : 'Point',
	'coordinates' : [149.14377, -35.31159]
			}
	},
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<strong> Orroral Valley Tracking Station </strong> <p> This location was a satellite tracking station opened in 1966, a year after the still standing Canberra deep space Communication complex. It was a fairly large complex that employed a large amount of staff and was used to track and communicate with satellites passing over the southern hemisphere, an area of the world with far less tracking technology than the northern hemisphere. </p> <img src="Orroral Valley/001_CB_ORR.jpg" /> <p> Photo Jim Thompson, 26m antenna, 					The station had roles in the space shuttle program as well as a range of other integral projects. All that remains today is concrete foundations. Further research can be found <a href="https://imgur.com/M9I7iMf" target="_blank" title="Opens in a new window"> here </a> </p>',
    'icon' : 'Dish'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [148.94677, -35.61714]
            }
    },
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<strong> Sound and Film Archive</strong> <p>A well known building near the centre of Canberra, many people know of the Sound and Film archive. The building itself however has a relatively unknown history. The Sound and Film Archive building was first built to be used as the Museum of Zoology. Within its construction you can find carved animals and pieces of australian history. Later, the museum changed its name to the Institute of Anatomy. A wide variety of pieces (e.g. skeletons) were stored in the Institute until it was converted to what it is today in 1984. For more click <a href="Sound and Media Archive/Archive pdf.pdf" target="_blank" title="Opens in a new window"> here </a></p> <img src="Sound and Media Archive/sound and media.jpg" />',
    'icon' : 'Film Archive'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [149.12138, -35.28323]
            }
    },
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<Strong> Mugga Lane Zoo </Strong> <p>The Mugga Lane zoo was a small zoo along Mugga Lane. It was first opened in 1979 as the first zoo in Canberra. The zoo was first intended to be like a natural garden park but, as its occupants became more diverse, this vision faded and eventually died. The zoo mostly held birds or Australian native animals, including wedge tailed eagles, monkeys and emus. After facing difficulties along its life, such as a drought in 1982 that required the construction of a small dam, nothing aside from a pile of rubbish remains today. The zoo was closed in 2002. The zoo has left a legacy that stays till today, with its closing, peacocks were released into parts of the suburbs Red Hill and Narrabundah. </p>',
    'icon' : 'zxee'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [149.13209, -35.35943]
            }
    },
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<strong> Mugga Lane Ruins </strong> <p>The rarely mentioned or researched location has puzzled many passers by. It lies just off the Mugga Lane, just before The Green Shed. It is an old stone construction that was estimated to have been built before 1878, although the little information I managed to find in my research process was possibly inaccurate.</p> <img src="Mugga Lane Ruins/IMG_2109.jpg" /> <p>The building was said to have been built as a outstation for employees of the Duntroon estate. A resident of the Duntroon Dairy, Elizabeth Mayo, lived their with her husband until his unfortunate death in 1880, when she moved to the Dairy.  </p>',
    'icon' : 'Air Crash'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [149.13481, -35.37743]
            }
    },
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<Strong> Belconnen former naval transmitting station </strong> <p>A former Naval Transmitter station used to stand in Belconnen. First built before the existence of the satellite city, the station finished its completion around the start of WW2. The station, once the most powerful satellite transmitter in the southern hemisphere, played a vital role throughout WW2, alongside the still standing HMAS Harman, its receiving counterpart.</p> <img src="Naval Transmitting Station/IMG_2130.jpg" /> <p>The building is a large red hall, with three 600ft tall radio towers on the site. The location has a long and interesting history until it closed in 2005. Click <a href="Naval Transmitting Station/Bels pdf.pdf" target="_blank" title="Opens in a new window"> here </a> to find out more. </p>',
    'icon' : 'Dish'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [149.090065, -35.21999]
            }
    },
	{
            'type' : 'Feature',
            'properties' : {
                'description':
            '<strong> Canberra Hyatt</strong><p>The Hyatt Hotel, originally Hotel Canberra or Hostel No.1 has made a mark on Canberra’s history as the Capital of Australia. The hotel opened in 1924, its construction undertaken by the workers of Westlake. It was an unlicensed venue in its early years as ACT was the only state or territory in Australia to enforce prohibition. The building has had extensions built over its lifespan but the original parts of it remain the same. I had the opportunity to go on a tour led by the Director of the Hotel and was allowed into the presidential suite, a room that has been visited by Obama, Shinzo Abe and a multitude of other world leaders. </p> <img src="The Hyatt/hyatt.jpg" />',
    'icon' : 'Dairy'
    },
    'geometry' : {
    'type' : 'Point',
    'coordinates' : [149.125, -35.299]
            }
    },
	{
			'type' : 'Feature',
			'properties' : {
				'description':
			'<strong>Westlake Settlement</strong><p>Westlake was a workers camp used in the early period of the construction of the capital. It began as a collection of tents, used to house unmarried labourers. Due to the length of the job, semi-permanent cottages were constructed by a local Canberra contractor known as Howie. These cottages were for married workers and their families. These workers built some of the central landmarks of the capitals inner south such as Hostel No.1 (The Hyatt) and the Old Parliament. Image: Rusted Axehead found on site of westlake</p> <img src="Westlake Workers Camp/IMG_2013.jpg" />',
	'icon' : 'Westlake'
	},
	'geometry' : { 
	'type' : 'Point',
	'coordinates' : [149.11443, -35.30127]
			}
		}
		]
	}
});
	map.addLayer({
	'id' : 'places',
	'type': 'symbol',
	'source': 'places',
	'layout' : {
		'icon-image' : ['get', 'icon'],
		'icon-allow-overlap' : true,
	'icon-size' : 0.25,
	}
});


map.on('click', 'places', (e) => {

const coordinates = e.features[0].geometry.coordinates.slice();
const description = e.features[0].properties.description;

while (Math.abs(e.lngLat.lng - coordinates[0]) > 180) {
	coordinates[0] += e.lngLat.lng > coordinates[0] ? 360 : -360;
     }

            new mapboxgl.Popup()
                .setLngLat(coordinates)
                .setHTML(description)
                .addTo(map);
        });

        // Change the cursor to a pointer when the mouse is over the places layer.
        map.on('mouseenter', 'places', () => {
            map.getCanvas().style.cursor = 'pointer';
        });

        // Change it back to a pointer when it leaves.
        map.on('mouseleave', 'places', () => {
            map.getCanvas().style.cursor = '';
        });
    });


</script>
</body>
</html>
