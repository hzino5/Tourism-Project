# Implementation

## Introduction
TODO: The Tourist Information Website system has been implemented as a comprehensive platform for travelers to discover and explore destinations, accommodations, activities, and dining options. The system primarily utilizes data from the Bristol Open Data API, supplemented with manually curated content for businesses not covered by the API.
Issues:
1-Some business listings may have incomplete information if not available in the open dataset
2-User review functionality is currently limited to display only (no submission capability in initial release)
3-Mobile responsiveness needs further optimization for some edge cases.

## Project Structure
TODO: tourist-info-website/
├── assets/               # Static assets
│   ├── css/              # Stylesheets
│   ├── images/           # Image resources
│   └── js/               # JavaScript files
├── data/                 # Data files and API handlers
│   ├── api.js            # Bristol Open Data API interface
│   ├── businesses.json   # Local business data cache
│   └── locations.json    # Destination information
├── index.html            # Main entry point
├── about.html            # About us page
├── destinations/         # Destination-specific pages
│   ├── bristol.html
│   └── bath.html
└── README.md             # Project documentation

JSLint Report:

Module	          Warnings	      Errors
api.js	            2	            0
main.js	            1	            0
validation.js	    0	            0
ui-components.js	3	            0

## Software Architecture
TODO: Describe the major components of your architecture. Are any particular architectural styles being used?

Our code shows a client-side-only implementation without backend servers or API integrations.
Down Below is Our Major components of the architecture and any particular architectural styles.
Major Components:
1-Presentation Layer (UI Components)
   - Navigation system (nav-container, auth-buttons)
   - Content display system (explore-content, category-content)
   - Hotel/activity cards (hotel-card templates)
   - Modal forms (form-container for login/signup)
   - Responsive design implementation (media queries)
2-Application Logic Layer
   - Tab management (showCategory() function)
   - view switching (showExploreContent(), goHome())
   - Form handling (showLoginForm(), showSignUpForm())
   - Basic DOM manipulation for dynamic content
3-Data Layer
   - Hardcoded data in HTML structure (hotel listings)
   - No external API integration (despite plans for Bristol Open Data)
   - No persistent data storage (session/local storage not used)
Architectural Styles Used:
1-Single-Page Application (SPA) Pattern 
   - Content dynamically shown/hidden via JavaScript
2-Component-Based Architecture
   - Modular CSS styling for each component
3- Client-Side Rendring
   - Pure HTML/CSS/JavaScript implementation

![Insert your component Diagram here](images/component.png)

## Bristol Open Data API
TODO: 
1. Main Tourist Information Query
URL:
https://maps2.bristol.gov.uk/server2/rest/services/ext/ll_leisure_and_culture/MapServer/17/query?outFields=*&where=1%3D1&f=geojson
Parameters:
   - outFields=*: Returns all available fields for each feature

   - where=1%3D1: A SQL WHERE clause that returns all records (1=1 is always true)

   - f=geojson: Specifies the output format as GeoJSON
. This query retrieves tourist information data from Bristol's Leisure and Culture map service (Layer 17). The data includes various points of interest, attractions, and cultural sites in Bristol.
Layer Details:
  - Service: ext/ll_leisure_and_culture
  - Layer: 17 (Tourist Information)
  - Data Type: Polygon features representing tourist areas/sites
The response is processed as GeoJSON and added to the Mapbox GL map with:
 . Blue fill (50% opacity)
 . Black outline (1px width)

2. Map Initialization Parameters
Center Coordinates:
 - Latitude: 51.454514 (Bristol city center)
 - Longitude: -2.587910 (Bristol city center)

Zoom Level:
 . 10 - Shows Bristol and surrounding areas at a reasonable detail level


![UML Class diagrams representing JSON query results](images/class1.png)
TODO: We didnt use a UML tool but our json response would be something like:
"id": 1,
  "name": "Travelodge Bristol Abbey Wood",
  "type": "hotel",
  "rating": 4.5,
  "reviews_count": 55,
  "website": "www.travelodge.co.uk",
  "phone": "0871 984 6626"

# User guide
TODO: Explain how each use-case works by providing step-by-step screenshots for each use-case. This should be based on a tested scenario.

Me and Partner tested this ourselves and this is how a tourist would use it. We have given scenarios in each case showing how they would be able to find what they were looking for and although the website is not fully done, this is how a Tourist would use it.

Case 1: Browsing Hotel Listings
Scenario: A tourist wants to find hotels in Bristol.

Step 1: Navigate to the Website
Open the browser and visit the website.

The homepage displays a welcome message and an image of a popular attraction.

Homepage

Step 2: Click "Explore Destinations"
Click the "Explore Destinations" button in the navigation bar.

Navigation Bar

Step 3: Select "Hotels" Tab
The system displays a list of available categories (Hotels, Activities, Restaurants).

Click the "Hotels" tab.

Category Selection

Step 4: View Hotel Listings
The system loads a list of hotels with details (name, rating, contact info).

Hotel Listings

Case 2: Searching for Restaurants
Scenario: A tourist wants to find nearby restaurants.

Step 1: Click "Restaurants" Tab
From the Explore Destinations section, select the "Restaurants" tab.

Restaurants Tab

Step 2: list of different resturant 
The system displays a list of restaurants with ratings, cuisine types, and locations.

Restaurant Listings

Case 3: Viewing Destination Details on Map
Scenario: A tourist wants to see attractions on an interactive map.

Step 1: Click "Find on Map"
The website loads an embedded map with markers for hotels, restaurants, and attractions.

Map View

Step 2: Click a Location Marker
Clicking a marker displays details (name, rating, contact info).

Map Popup

