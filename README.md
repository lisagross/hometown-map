# hometown-map
map of Evansville
<!DOCTYPE html>
<html>

<head>
	<meta charset=utf-8 />
	<title>Web Page Template</title>
	<meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />

	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/normalize/5.0.0/normalize.css" />
	<link rel="stylesheet" href="https://unpkg.com/leaflet@1.0.1/dist/leaflet.css" />
	<link href="https://fonts.googleapis.com/css?family=Noto+Sans" rel="stylesheet">
	<link href="https://fonts.googleapis.com/css?family=Lora" rel="stylesheet">

	<style>
		body {
			margin: 0;
			padding: 0;
			background: #f5f5f5;
			font-family: "Noto Sans", sans-serif;
			color: #3d3d3d;
		}

		section {
			width: 960px;
			margin: 20px auto;
		}

		h1 {
			width: 960px;
			margin: 20px auto;
			font-family: Lora, serif;
			letter-spacing: .04em;
		}

		h2 {
			font-family: Lora, serif;
			letter-spacing: .04em;
		}

		p {
			font-size: 1em;
			line-height: 1.5em;
		}

		a {
			color: #005daa;
			font-weight: bold;
			text-decoration: none;
		}

		a:hover {
			text-decoration: underline;
		}

		ul {
			padding-left: 20px;
		}

		li {
			margin: 10px 0
		}
		#map {
			width: 960px;
			height: 540px;
			margin: 10px auto;
			border: 2px solid #d3d3d3;
		}
	</style>
</head>

<body>

	<h1>Got it!</h1>

	<div id='map'></div>

	<section>
		<h2>about this map</h2>
		<p>Additional information about <a href="#">the data</a> and map goes here. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis urna magna, maximus nec laoreet sit amet, dictum ultricies nibh. Ut id auctor lacus. Nam a dolor et justo luctus luctus.</p>

		<ul>
			<li>See my projects on GitHub: <a href="https://github.com/newmapsplus">New Maps Plus</a></li>
			<li>Follow me on twitter: <a href="https://twitter.com/NewMapsPlus">@NewMapsPlus</a></li>
			<li>Visit my <a href='#'>mapping portfolio</a>.</li>
		</ul>
	</section>

	<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity="sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" crossorigin="anonymous"></script>
	<script src="https://unpkg.com/leaflet@1.2.0/dist/leaflet-src.js"></script>
	<script>

		// map options
		var options = {
			center: [38.0406, -84.5037], // lat/lon values
			zoom: 12
		}

		// create a Leaflet map in our division container with id of 'map'
		var map = L.map('map', options);

		// request some basemap tiles and add to the map
		var tiles = L.tileLayer('http://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}.png', {
			attribution: '&copy; <a href="http://www.openstreetmap.org/copyright">OpenStreetMap</a> &copy; <a href="http://cartodb.com/attributions">CartoDB</a>',
			subdomains: 'abcd',
			maxZoom: 19
		}).addTo(map);

		// write a custom message for the Leaflet tooltip
		var message = 'Lexington is awesome!';

		// add a marker to the center of the map and open the tooltip
		L.marker(map.getCenter())
			.bindTooltip(message)
			.addTo(map)
			.openTooltip();

	</script>

</body>

</html>
