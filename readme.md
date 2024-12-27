# Cultural Event Finder 🎉🗺️

Welcome to the **Cultural Event Finder** web app! This application helps you discover cultural events happening around the world, all displayed on an interactive map. 🌍✨

## Features 🎯

- **Interactive Map** 🗺️: Click on any location on the map to discover cultural events happening in that area. You can explore events from cities across the globe.
- **Radius Filter** 📍: Adjust the search radius to find events within a specified distance from your selected location.
- **Date Filter** 📅: Specify a date range to see events happening on a particular day or during a specified period.
- **Event Details** 🎟️: Once you click on a location, the app retrieves detailed information about the events such as name, date, time, venue, and more.

## How It Works 🔧

### Data Retrieval from Ticketmaster API 🌐
The app retrieves cultural event data by making requests to the **Ticketmaster API**. Here’s how it works:

1. **User Input**: The user clicks on a location on the interactive map and can set the desired **radius** (distance from the location) and **date range** (specific date or range of dates).
   
2. **Location Coordinates** 📍: The app uses the latitude and longitude of the clicked location on the map to query the Ticketmaster API for events in that area. 

3. **API Request**: The app makes an API request to Ticketmaster with the selected coordinates, radius, and date filters. The request is formatted to get the most relevant cultural events, ensuring that only the events within the radius and date range are returned.

4. **Event Data** 📊: Once the data is fetched from Ticketmaster, the app processes the event details and displays them to the user, highlighting key event information such as:
   - Event name
   - Date & time
   - Venue name & location
   - Ticket purchase links

5. **Results Display** 🎉: The app shows the retrieved events on the map and in a list format, making it easy for the user to find the perfect event to attend.

## Technologies Used 💻

- **React**: For building the interactive and dynamic UI components.
- **Mapbox**: For displaying the interactive map.
- **Ticketmaster API**: To fetch event data based on location and date filters.
- **CSS/SCSS**: For styling the app to make it visually appealing and responsive.

## Running the App 🏃‍♂️

To run the **Cultural Event Finder** web app, click on given link:
https://iridescent-clafoutis-ada50f.netlify.app/

