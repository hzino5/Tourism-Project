hamza and Kamal
# Design

## User Interface design
TODO: Specify and develop a user interface mockup using a wireframe.

!![alt text](wireframes.png)(images/wireframe.png)
TODO:
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tourteller - Explore the World</title>
  <style>
    /* Importing Calibri font */
    @import url('https://fonts.googleapis.com/css2?family=Calibri&display=swap');

    /* Main Container */
    body {
      font-family: 'Calibri', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #fff;
      color: white;
    }

    /* Main Navigation Container */
    .nav-container {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background-color: #000;
      padding: 10px 20px;
      border-radius: 8px;
      box-shadow: 4px 4px 10px rgba(0, 0, 0, 0.1);
    }

    /* Logo Section */
    .logo-container {
      display: flex;
      align-items: center;
    }

    .logo {
      font-family: 'Calibri', sans-serif;
      font-size: 2.2em;
      font-weight: 700;
      color: #ffb703;
      text-decoration: none;
      letter-spacing: 1px;
      margin-right: 10px;
      cursor: pointer;
    }

    .logo-img {
      height: 40px;
    }

    /* Navigation Buttons */
    .nav-btn {
      font-family: 'Calibri', sans-serif;
      font-size: 1em;
      font-weight: 600;
      color: white;
      text-decoration: none;
      padding: 8px 16px;
      border-radius: 8px;
      background-color: #003b5c;
      transition: background-color 0.3s ease;
    }

    .nav-btn:hover {
      background-color: #0288d1;
    }

    /* Top Right - Log In/Sign Up */
    .auth-buttons {
      display: flex;
      gap: 10px;
    }

    /* Auth Buttons Styling */
    .auth-btn {
      font-size: 0.9em;
      padding: 7px 15px;
      background-color: #ffd700;
      color: #003b5c;
      border-radius: 5px;
      font-weight: 700;
      transition: background-color 0.3s ease;
    }

    .auth-btn:hover {
      background-color: #ffcc00;
    }

    /* Content Section */
    .content {
      text-align: center;
      margin: 40px 15px;
    }

    /* Title (Welcome to Tourteller) */
    .title {
      font-family: 'Calibri', sans-serif;
      font-size: 2.5em;
      color: black;
      font-weight: 700;
      letter-spacing: 1px;
    }

    /* Subheading (Embark on a journey...) */
    .subheading {
      font-family: 'Calibri', sans-serif;
      font-size: 1.4em;
      color: black;
      margin-top: 15px;
      margin-bottom: 30px;
      font-weight: 600;
      letter-spacing: 1px;
    }

    /* Image Styling */
    .hero-image {
      width: 100%;
      max-height: 400px;
      object-fit: cover;
      border-radius: 10px;
      margin-top: 20px;
      box-shadow: 4px 4px 12px rgba(0, 0, 0, 0.1);
    }

    /* Explore Destinations Content */
    .explore-content {
      display: none;
      padding: 20px;
    }

    /* Tabs */
    .tab-buttons {
      display: flex;
      justify-content: center;
      margin-bottom: 20px;
    }

    .tab-button {
      font-size: 1.2em;
      padding: 10px 20px;
      margin: 0 10px;
      background-color: #003b5c;
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .tab-button:hover {
      background-color: #0288d1;
    }

    /* Categories Content */
    .category-content {
      display: none;
    }

    /* Hotel Card Styling */
    .hotel-card {
      background-color: white;
      border-radius: 8px;
      padding: 15px;
      margin: 15px 0;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      color: black;
      text-align: left;
    }

    .hotel-header {
      margin-bottom: 10px;
    }

    .hotel-header h4 {
      margin: 0 0 5px 0;
      font-size: 1.2em;
      color: #003b5c;
    }

    .hotel-rating {
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .stars {
      color: #ffb703;
      font-size: 1.1em;
    }

    .rating {
      font-weight: bold;
    }

    .reviews {
      color: #666;
      font-size: 0.9em;
    }

    .hotel-info {
      display: flex;
      gap: 15px;
      font-size: 0.9em;
      color: #666;
      flex-wrap: wrap;
    }

    .hotel-info span {
      display: flex;
      align-items: center;
    }

    .hotel-info span:before {
      content: "•";
      margin-right: 5px;
    }

    .hotel-info span:first-child:before {
      content: none;
    }

    /* Hotel Comparison Section */
    .hotel-comparison {
      display: flex;
      gap: 20px;
      margin-top: 20px;
      justify-content: space-between;
    }

    .hotel-column {
      flex: 0 0 calc(33.33% - 15px);
      background-color: white;
      border-radius: 8px;
      padding: 15px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }

    /* About Us Section */
    .about-us {
      font-family: 'Calibri', sans-serif;
      font-size: 1.3em;
      color: #000;
      max-width: 750px;
      margin: 40px auto;
      line-height: 1.7;
      text-align: left;
    }

    .about-us h2 {
      font-size: 2em;
      color: #003b5c;
    }

    .about-us p {
      margin-bottom: 15px;
    }

    /* Form Styling for Login/SignUp */
    .form-container {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }

    .form-box {
      background-color: white;
      padding: 30px;
      border-radius: 8px;
      width: 350px;
      box-shadow: 4px 4px 12px rgba(0, 0, 0, 0.1);
      text-align: left;
      color: black;
    }

    .form-box h3 {
      color: #003b5c;
      text-align: center;
      margin-bottom: 20px;
      font-size: 1.5em;
    }

    .form-box input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
      box-sizing: border-box;
    }

    .form-box button {
      width: 100%;
      padding: 12px;
      background-color: #003b5c;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-weight: bold;
      margin-top: 10px;
    }

    .form-box button:hover {
      background-color: #0288d1;
    }

    .form-footer {
      text-align: center;
      margin-top: 15px;
      font-size: 0.9em;
    }

    .form-footer a {
      color: #003b5c;
      text-decoration: none;
      font-weight: bold;
    }

    .form-footer a:hover {
      text-decoration: underline;
    }

    /* Error message styling */
    .error-message {
      color: #d32f2f;
      font-size: 0.9em;
      margin-top: 5px;
      display: none;
    }

    /* Responsive Design */
    @media (max-width: 768px) {
      .nav-container {
        flex-direction: column;
        align-items: flex-start;
      }
      .auth-buttons {
        flex-direction: column;
        gap: 8px;
      }
      .content {
        margin: 20px;
      }
      .section {
        flex-direction: column;
        align-items: center;
      }
      .section div {
        width: 80%;
        margin-bottom: 20px;
      }
      .form-box {
        width: 90%;
        padding: 20px;
      }
      .hotel-comparison {
        flex-direction: column;
      }
      .hotel-column {
        flex: 0 0 100%;
      }
    }
  </style>
</head>
<body>

  <!-- Top Navigation -->
  <nav class="nav-container">
    <div class="logo-container">
      <a href="javascript:void(0);" class="logo" onclick="goHome()">Tourteller</a>
      <img src="https://files.oaiusercontent.com/file-28XqmYbjZknVxM8SyeJv2L?se=2025-03-21T14%3A02%3A40Z&sp=r&sv=2024-08-04&sr=b&rscc=max-age%3D604800%2C%20immutable%2C%20private&rscd=attachment%3B%20filename%3Dd31fc49f-61bc-4214-8707-2551a5e2d710.webp&sig=yXlOUR/sWC0g2CRRwQWbyHkEnunw6gnZpL/IvBbC9HU%3D" alt="Tourteller Logo" class="logo-img">
    </div>
    <a href="javascript:void(0);" class="nav-btn" onclick="showExploreContent()">Explore Destinations</a>
    <div class="auth-buttons">
      <a href="javascript:void(0);" class="nav-btn auth-btn" onclick="showLoginForm()">Log In</a>
      <a href="javascript:void(0);" class="nav-btn auth-btn" onclick="showSignUpForm()">Sign Up</a>
    </div>
  </nav>

  <!-- Main Content Section -->
  <div class="content">
    <h1 class="title">Welcome to Tourteller</h1>
    <p class="subheading">Embark on a journey of discovery, adventure, and unforgettable moments.</p>
    <img src="https://dynamic-media-cdn.tripadvisor.com/media/photo-o/0b/b5/9b/ea/clifton-suspension-bridge.jpg?w=900&h=500&s=1" alt="Clifton Suspension Bridge" class="hero-image">
  </div>

  <!-- About Us Section -->
  <div class="about-us">
    <h2>About Us</h2>
    <p>
      At Tourteller, we are passionate about creating unforgettable travel experiences for adventurers of all kinds.
      Founded with the mission to make travel accessible, immersive, and memorable, we offer bespoke itineraries,
      guided tours, and exclusive experiences around the globe. Our team of travel experts is dedicated to curating
      journeys that will leave you with lifelong memories.
    </p>
    <p>
      Whether you're seeking a peaceful retreat in nature, an action-packed adventure, or a cultural journey to
      explore the world's most fascinating destinations, Tourteller has something for you. We work closely with local
      guides and experts to provide you with authentic experiences that connect you to the heart and soul of each
      location. Our commitment to sustainability means we prioritize eco-friendly practices and support local communities,
      ensuring that your travels have a positive impact.
    </p>
    <p>
      Join us as we explore the world together. From exotic beaches to majestic mountains, vibrant cities to serene
      countryside, the world is full of incredible places waiting to be discovered. At Tourteller, we help you experience
      them in the most meaningful way possible. Let's make memories that last a lifetime!
    </p>
  </div>

  <!-- Explore Destinations Content -->
  <div class="explore-content">
    <div class="tab-buttons">
      <button class="tab-button" onclick="showCategory('hotels')">Hotels</button>
      <button class="tab-button" onclick="showCategory('activities')">Activities</button>
      <button class="tab-button" onclick="showCategory('restaurants')">Restaurants</button>
    </div>

    <!-- Category Contents -->
    <div id="hotels" class="category-content">
      <h3>Hotels</h3>
      <p>Find the best places to stay during your travels.</p>
     
      <div class="hotel-comparison">
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Travelodge Bristol Abbey Wood</h4>
              <div class="hotel-rating">
                <span class="stars">★★★★★</span>
                <span class="rating">4.5</span>
                <span class="reviews">55 Google reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">Hotel</span>
              <span class="hotel-website">www.travelodge.co.uk</span>
              <span class="hotel-phone">0871 984 6626</span>
            </div>
          </div>
        </div>
       
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Mercure Bristol Grand Hotel</h4>
              <div class="hotel-rating">
                <span class="stars">★★★★</span>
                <span class="rating">4.2</span>
                <span class="reviews">1,245 Google reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">4-star hotel</span>
              <span class="hotel-website">www.mercure.com</span>
              <span class="hotel-phone">0117 929 1035</span>
            </div>
          </div>
        </div>
       
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Radisson Blu Hotel, Bristol</h4>
              <div class="hotel-rating">
                <span class="stars">★★★★</span>
                <span class="rating">4.3</span>
                <span class="reviews">3,169 TripAdvisor reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">4-star hotel</span>
              <span class="hotel-website">www.radissonhotels.com</span>
              <span class="hotel-phone">0117 934 9500</span>
            </div>
          </div>
        </div>
      </div>
     
      <!-- New hotels added here with the same structure as the first line -->
      <div class="hotel-comparison">
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Bristol Marriott Royal Hotel</h4>
              <div class="hotel-rating">
                <span class="stars">★★★★</span>
                <span class="rating">4.3</span>
                <span class="reviews">2.4K reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">4-star hotel</span>
            </div>
          </div>
        </div>
       
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Arnos Manor Hotel</h4>
              <div class="hotel-rating">
                <span class="stars">★★★</span>
                <span class="rating">3.7</span>
                <span class="reviews">1.2K reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">3-star hotel</span>
            </div>
          </div>
        </div>
       
        <div class="hotel-column">
          <div class="hotel-card">
            <div class="hotel-header">
              <h4>Village Hotel Bristol</h4>
              <div class="hotel-rating">
                <span class="stars">★★★★</span>
                <span class="rating">4.3</span>
                <span class="reviews">2.1K reviews</span>
              </div>
            </div>
            <div class="hotel-info">
              <span class="hotel-type">4-star hotel</span>
            </div>
          </div>
        </div>
      </div>
     
      <ul>
        <li>Travelodge Bristol Filton</li>
        <li>Delta Hotels Bristol City Centre</li>
        <li>Travelodge Bristol Emersons Green</li>
        <li>Premier Inn Bristol Parkway</li>
        <li>Premier Inn Bristol City Centre</li>
        <li>The Regency, Lodge at Bristol</li>
        <li>Mollie's Motel and Diner Bristol</li>
        <li>Mercure Bristol Grand Hotel</li>
      </ul>
    </div>
    <div id="activities" class="category-content">
      <h3>Activities</h3>
      <p>Discover fun and exciting things to do.</p>
    </div>
    <div id="restaurants" class="category-content">
      <h3>Restaurants</h3>
      <p>Explore local cuisine and dining experiences.</p>
    </div>
  </div>

  <!-- Form for Log In and Sign Up -->
  <div class="form-container" id="login-form">
    <div class="form-box">
      <h3>Log In</h3>
      <input type="text" placeholder="Username" required>
      <input type="password" placeholder="Password" required>
      <button onclick="submitForm('login')">Log In</button>
      <div class="form-footer">
        <span>Don't have an account? <a href="javascript:void(0);" onclick="showSignUpForm()">Sign Up</a></span>
      </div>
    </div>
  </div>

  <div class="form-container" id="signup-form">
    <div class="form-box">
      <h3>Sign Up</h3>
      <input type="text" placeholder="Username" required>
      <input type="email" placeholder="Email" required>
      <input type="password" placeholder="Password" required>
      <button onclick="submitForm('signup')">Sign Up</button>
      <div class="form-footer">
        <span>Already have an account? <a href="javascript:void(0);" onclick="showLoginForm()">Log In</a></span>
      </div>
    </div>
  </div>

  <script>
    function showExploreContent() {
      document.querySelector('.content').style.display = 'none';
      document.querySelector('.about-us').style.display = 'none';
      document.querySelector('.explore-content').style.display = 'block';
      showCategory('hotels'); // Show hotels by default
    }

    function goHome() {
      document.querySelector('.content').style.display = 'block';
      document.querySelector('.about-us').style.display = 'block';
      document.querySelector('.explore-content').style.display = 'none';
    }

    function showCategory(category) {
      const categories = document.querySelectorAll('.category-content');
      categories.forEach(categoryContent => {
        categoryContent.style.display = 'none';
      });
      document.getElementById(category).style.display = 'block';
    }

    // Show login form
    function showLoginForm() {
      document.getElementById('login-form').style.display = 'flex';
      document.getElementById('signup-form').style.display = 'none';
    }

    // Show sign-up form
    function showSignUpForm() {
      document.getElementById('signup-form').style.display = 'flex';
      document.getElementById('login-form').style.display = 'none';
    }

    // Simulate form submission
    function submitForm(type) {
      alert(type === 'login' ? 'Logging in...' : 'Signing up...');
      document.getElementById('login-form').style.display = 'none';
      document.getElementById('signup-form').style.display = 'none';
    }
  </script>

Kamal Nur (Student)
​
<!DOCTYPE html>
<html lang="en">
<head>
<title>Bristol Tourism</title>

<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v3.1.2/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v3.1.2/mapbox-gl.js"></script>
<style>
#map { position: absolute; top: 1; height: 60%; width: 60%; }
</style>

<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="https://www.w3schools.com/w3css/4/w3.css">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css"/>
<link rel="preconnect" href="https://fonts.gstatic.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@600&family=Roboto:wght@500&display=swap">
<script src="script.js"> // mapping functions </script>
<script>
const MY_TOKEN = "pk.eyJ1Ijoic3RldmViYXR0bGUiLCJhIjoiY2xzcWQxZzBiMHExZTJxbmpnN2hqbHMwZyJ9.hIauJCmUD0AzB4Uwru49QQ";

// see: https://docs.mapbox.com/mapbox-gl-js/example/geojson-polygon/

function addGeoJSON(json) {
let features = json.features;
for (i=0; i<features.length; i++) {
let p = features[i].properties;

// Add GeoJSON data source.
map.addSource("data-"+p.OBJECTID, {
type: 'geojson',
data: features[i]
});

// Add polygon fill
map.addLayer({
'id': "fill-"+p.OBJECTID,
'type': 'fill',
'source': "data-"+p.OBJECTID, // reference the data source
'layout': {},
// blue fill, 50% opacity
'paint': { 'fill-color': '#0080ff', 'fill-opacity': 0.5 }
});

// Add polygon outline
map.addLayer({
'id': "line-"+p.OBJECTID,
'type': 'line',
'source': "data-"+p.OBJECTID,
'layout': {},
'paint': { 'line-color': '#000', 'line-width': 1 }
});
}
}

function query() {
let url="https://maps2.bristol.gov.uk/server2/rest/services/ext/ll_leisure_and_culture/MapServer/17/query?outFields=*&where=1%3D1&f=geojson";
fetch(url, { method: 'GET', headers: { 'Accept': 'application/json' }})
.then (response => response.json())
.then(addGeoJSON);
}
</script>
</head>
<body>
<div class="grid-container">
<header>
<span class="heading"><a href="https://maps2.bristol.gov.uk/server2/rest/services/ext/ll_leisure_and_culture/MapServer/17/query?outFields=*&where=1%3D1&f=geojson">Tourist Information</a></span>
</header>
<nav class="w3-container w3-margin">
<button onclick="getLocation('ward.html')" class="w3-button w3-block w3-blue w3-margin-top">Find on Map</button>
</nav>
<main>
<div id="map"></div>
</main>
</div>
<script>
// get query string parameters lat, lon
// var urlParams = new URLSearchParams(location.search);
// var lat = urlParams.get('lat');
// var lon = urlParams.get('lon');
var lat = 51.454514;
var lon = -2.587910

mapboxgl.accessToken = MY_TOKEN;
var map = new mapboxgl.Map({
container: 'map', // container ID
center: [lon, lat], // longitude, latitude
zoom: 10 // zoom level
});

map.on('load', () => { query(map); });
</script>
</body>
</html>
</body>
</html>
