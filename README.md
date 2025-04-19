# Weather---App

Name: ROOP SAGAR S L  

Reg no: 212223040175

Build a Weather App using React

# Objective

Create a simple weather application using React that allows the user to enter a city name and view simulated weather data such as temperature, wind speed, and sky condition.

# Task Description
Develop a weather app that:

Accepts a city name from the user

Displays weather information (temperature, wind speed, sky condition) only for predefined cities

Shows an error message for cities not in the mock data

# Requirements
React functional component (WeatherApp)

Text input to enter city name

A button or "Enter" key to trigger search

Display of weather data (if city is valid)

Error message for invalid cities

Basic styling using external or inline CSS

# PROGRAM:
```
index.js

import React from 'react';
import ReactDOM from 'react-dom/client';
import './App.css';
import App from './App';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

App.js

import React, { useState } from 'react';
import './App.css';

const mockWeather = {
  bienhoa: {
    day: 'Monday',
    date: 'Aug 8th',
    location: 'Bien Hoa, VN',
    temperature: 27,
    condition: 'Overcast clouds',
    cloudiness: '100%',
    humidity: '90%',
    wind: '2.4 m/s',
    feelsLike: '31°C',
    maxTemp: '27°C',
    minTemp: '27°C',
    hourly: [
      { time: '3:00 AM', temp: '27°C', icon: '🌧️' },
      { time: '6:00 AM', temp: '26°C', icon: '🌧️' },
      { time: '9:00 AM', temp: '25°C', icon: '⛅' },
      { time: '12:00 PM', temp: '24°C', icon: '🌧️' },
      { time: '3:00 PM', temp: '22°C', icon: '🌧️' },
    ],
  },
};

function App() {
  const [city, setCity] = useState('');
  const [data, setData] = useState(null);

  const handleSearch = () => {
    const cityKey = city.toLowerCase().trim();
    setData(mockWeather[cityKey]);
  };

  return (
    <div className="app">
      <h1>Weather Forecast</h1>
      <div className="search-bar">
        <input
          type="text"
          placeholder="Enter city..."
          value={city}
          onChange={(e) => setCity(e.target.value)}
        />
        <button onClick={handleSearch}>🔍</button>
      </div>

      {data ? (
        <div className="weather-container">
          <div className="card">
            <h2>{data.day}</h2>
            <p>{data.date}</p>
            <p>📍 {data.location}</p>
            <div className="weather-image"></div>
            <h3>{data.temperature}°C</h3>
            <p>{data.condition}</p>
          </div>

          <div className="details">
            <p>Cloudiness <span>{data.cloudiness}</span></p>
            <p>Humidity <span>{data.humidity}</span></p>
            <p>Wind <span>{data.wind}</span></p>
            <p>Feels Like <span>{data.feelsLike}</span></p>
            <p>Max Temp <span>{data.maxTemp}</span></p>
            <p>Min Temp <span>{data.minTemp}</span></p>
          </div>

          <div className="forecast">
            {data.hourly.map((h, idx) => (
              <div key={idx} className="forecast-item">
                <div>{h.icon}</div>
                <p>{h.time}</p>
                <p className="hour-temp">{h.temp}</p>
              </div>
            ))}
          </div>
        </div>
      ) : (
        city && <p className="no-data">No data found for "{city}"</p>
      )}
    </div>
  );
}

export default App;

App.css

body {
  margin: 0;
  padding: 0;
  font-family: 'Segoe UI', sans-serif;
  background-color: #0a043c;
  color: white;
}

.app {
  max-width: 900px;
  margin: auto;
  padding: 40px 20px;
  text-align: center;
}

h1 {
  color: #c084fc;
  font-size: 2.5rem;
  margin-bottom: 20px;
}

.search-bar {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 30px;
}

.search-bar input {
  padding: 10px 15px;
  font-size: 16px;
  border: none;
  border-radius: 10px;
  width: 250px;
}

.search-bar button {
  background-color: #1e1b4b;
  color: white;
  font-size: 20px;
  padding: 10px 14px;
  border: none;
  border-radius: 50%;
  cursor: pointer;
}

.weather-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 30px;
}

.card {
  background: linear-gradient(to top, #0f2027, #203a43, #2c5364);
  border-radius: 20px;
  padding: 20px;
  width: 300px;
  text-align: center;
}

.card .weather-image {
  height: 150px;
  background: url('https://images.unsplash.com/photo-1506744038136-46273834b3fb?fit=crop&w=500&q=80') center/cover no-repeat;
  border-radius: 10px;
  margin: 15px 0;
}

.card h3 {
  font-size: 2rem;
  margin: 10px 0;
}

.details {
  flex: 1;
  text-align: left;
  padding: 20px;
}

.details p {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #ffffff1a;
  padding: 10px 0;
  margin: 0;
}

.forecast {
  display: flex;
  gap: 15px;
  padding: 20px;
  background-color: #1f1b4b;
  border-radius: 20px;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 20px;
}

.forecast-item {
  text-align: center;
  width: 80px;
}

.forecast-item .hour-temp {
  color: #c084fc;
  font-weight: bold;
}

.no-data {
  color: #f87171;
  font-style: italic;
  margin-top: 20px;
}

```

# Output

![image](https://github.com/user-attachments/assets/0fd7e208-175c-4be1-8d35-323f50650e42)

# Result
The given task had been implemented.
