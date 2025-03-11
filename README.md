# uhuehch.github.io
<!DOCTYPE html>
<html>
<head>
    <title>Peta OpenStreetMap</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
    <script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>
    <style>
        #map { height: 500px; }
    </style>
</head>
<body>
    <h2>Peta OpenStreetMap</h2>
    <div id="map"></div>
    <script>
        // Inisialisasi peta
        var map = L.map('map').setView([0.830871,109.485081], 10); // Jakarta

        // Tambahkan layer peta dari OpenStreetMap
        L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
            attribution: '&copy; OpenStreetMap contributors'
        }).addTo(map);

        // Data titik koordinat (latitude, longitude, nama)
        var locations = [
            { lat: 0.830871, lng: 109.485081, name: "kantor pln" },
            { lat: 0.830432, lng: 109.484887, name: "tiang listrik yang tidak bagus" },
            { lat: 0.830258, lng: 109.484776, name: "ditimpa oleh pohon" },
            { lat: 0.830074, lng: 109.484739, name: "kabel tergelupas" }
        ];

        // Loop untuk menambahkan semua titik ke dalam peta
        locations.forEach(function(location) {
            L.marker([location.lat, location.lng]).addTo(map)
                .bindPopup(`<b>${location.name}</b><br>
                <a href='https://www.google.com/maps?q=${location.lat},${location.lng}' target='_blank'>Buka di Google Maps</a>`);
        });

    </script>
</body>
</html>
