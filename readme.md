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

## Code Example 📜

Here’s a code snippet showing how to integrate the **Ticketmaster API** and retrieve events based on a specific location and date range.

### 1. **Fetching Event Data from Ticketmaster API** 🚀

```javascript
import React, { useState, useEffect } from 'react';

const EventFetcher = ({ location, radius, startDate, endDate }) => {
  const [events, setEvents] = useState([]);
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    const fetchEvents = async () => {
      setLoading(true);
      try {
        const response = await fetch(`https://app.ticketmaster.com/discovery/v2/events.json?latlong=${location.lat},${location.lng}&radius=${radius}&startDateTime=${startDate}&endDateTime=${endDate}&apikey=YOUR_TICKETMASTER_API_KEY`);
        const data = await response.json();
        setEvents(data._embedded.events);
      } catch (error) {
        console.error('Error fetching events:', error);
      } finally {
        setLoading(false);
      }
    };

    if (location) {
      fetchEvents();
    }
  }, [location, radius, startDate, endDate]);

  if (loading) return <div>Loading...</div>;

  return (
    <div>
      {events.length > 0 ? (
        <ul>
          {events.map((event) => (
            <li key={event.id}>
              <h3>{event.name}</h3>
              <p>{event.dates.start.localDate} - {event._embedded.venues[0].name}</p>
              <a href={event.url} target="_blank" rel="noopener noreferrer">View Event</a>
            </li>
          ))}
        </ul>
      ) : (
        <p>No events found.</p>
      )}
    </div>
  );
};

export default EventFetcher;


Running the App 🏃‍♂️
To run the app locally, follow these steps:

Clone the repository:

bash
Copy code
git clone https://github.com/your-repository-link.git
Install dependencies:

bash
Copy code
npm install
Start the development server:

bash
Copy code
npm start
Open your browser and visit http://localhost:3000 to view the app in action.


