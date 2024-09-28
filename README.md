<!DOCTYPE html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Unique Interactive Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <!-- Navbar -->
    <nav id="navbar">
        <div class="container">
            <a href="#" class="logo">Muhammad Anas Rifa'i</a>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section with 3D Animation -->
    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1 data-text="Rifa'i">Rifa'i</h1>
                <p>Ini aku nyoba ngotak atik hehe</p>
                <a href="#cards" class="btn">maaf ya kalau biasa aja I*_*I</a>
            </div>
        </div>
    </section>

    <!-- Cards with Interactive Hover 3D Effect -->
    <section id="cards" class="cards-section">
        <div class="container">
            <h2>Sayang Kamu</h2>
            <div class="grid">
                <div class="card">
                    <h3>Asisten Statistika</h3>
                    <p>Muhammad Anas Rifa'i</p>
                </div>
                <div class="card">
                    <h3>Suka Sama</h3>
                    <p>kamu, iyaa kamuu</p>
                </div>
                <div class="card">
                    <h3>Asisten Ilmu Ukur Tanah</h3>
                    <p>Putri Cahya Widhi Utami</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Parallax Scrolling Section -->
    <section class="parallax-section">
        <div class="parallax-content">
            <h2>Scroll to Explore</h2>
            <p>Rumah caca dan fafa</p>
        </div>
    </section>

    <script src="script.js"></script>
</body>

<head>
	
	<!--sisipkan kode pemuatan disini -->
<link rel="stylesheet" href="leaflet/leaflet.css"/>
<script src="leaflet/leaflet.js"></script>

	<!--Menambahkan layer leaflet group--> 
<link rel="stylesheet" href="leaflet/leaflet.groupedlayercontrol.css"/> 
<script src="leaflet/leaflet.groupedlayercontrol.js"></script>

	<!--Menambahkan mouse position-->
<link rel="stylesheet" href="leaflet/L.Control.MousePosition.css"/> 
<script src="leaflet/L.Control.MousePosition.js"></script>

	<!--Menambahkan mouse position-->
<link rel="stylesheet" href="leaflet/Control.MiniMap.css"/> 
<script src="leaflet/Control.MiniMap.js"></script>

	<!--Menambahkan mouse position-->
<link rel="stylesheet" href="leaflet/Leaflet.LinearMeasurement.css"/> 
<script src="leaflet/Leaflet.LinearMeasurement.js"></script>

    </head>
   <body>
<!-- peta akan ditampilkan disini -->
         <div style="height:800px" id="mapid"></div>
    </body>
	
		<script src="faicahya.js"></script>
		
		
	<script>
var mymap = L.map('mapid').setView([-7.569437, 110.825272], 13);

//Menambahkan basemaps pada layer
var GoogleMaps = new L.TileLayer('https://mt1.google.com/vt/lyrs=m&x={x}&y={y}&z={z}', { 
     opacity: 1.0, attribution: 'PEMBELAJARAN WEBSIG RIFAI'
}).addTo(mymap);
var GoogleSatelliteHybrid = L.tileLayer('https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}', { 
     maxZoom: 22, 
     attribution: 'PEMBELAJARAN WEBSIG RIFAI' 
});

var baseLayers = {
     'Google Satellite Hybrid': GoogleSatelliteHybrid,
     'Google Maps': GoogleMaps,
}; 

//Menambahkan polygon dan titik pada layer
L.control.groupedLayers(baseLayers).addTo(mymap);
var polyg2 = L.geoJson(polygons.features).addTo(mymap);
var marker = L.marker([-7.521649, 110.734806]).addTo(mymap);
var marker = L.marker([-7.603220, 110.810109]).addTo(mymap);

//Menambahkan nama pada titik pada layer
marker.bindPopup("<b>Informasi</b><br>Rumah Mas Fai – E100220111");
marker.bindPopup("<b>Informasi</b><br>Rumah Mba Cahya – E100220071");

//Menambahkan scale bar
	L.control.scale( {
		position:'topleft',
		maxWidth:300,
		metric:true,
		imperial:true
		}  ).addTo(mymap);

	L.control.mousePosition({ 
		position:'bottomleft',
		numDigits:8,
		prefix:"Koordinat"
		}).addTo(mymap);
		
		var north = L.control({position: "bottomleft"});
north.onAdd = function(mymap) {
    var div = L.DomUtil.create("div", "info legend");
    div.innerHTML = '<img src="northarrow.png" width="50%" height="50%">';
    return div;
}
north.addTo(mymap);

var osmUrl='http://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png';
		var osmAttrib='Map data &copy; OpenStreetMap contributors';
		var osm = new L.TileLayer(osmUrl, {minZoom: 5, maxZoom: 18, attribution: osmAttrib});

		mymap.addLayer(osm);
		mymap.setView(new L.LatLng(-7.603220, 110.810109),14);
		
var osm2 = new L.TileLayer(osmUrl, {
		minZoom: 0, 
		maxZoom: 13, 
		attribution: osmAttrib 
		});
		
		var miniMap = new L.Control.MiniMap(osm2, {
		position:"bottomright",
		toggleDisplay: true 
		}).addTo(mymap);
		
		mymap.addControl(new L.Control.LinearMeasurement({
        unitSystem: 'imperial',
        color: '#f5ed0a',
        type: 'line',
		unitSystem:"matric"
    }));
  
	</script>


    </html>

