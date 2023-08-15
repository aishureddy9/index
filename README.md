# Project Title

React Map Interface for Visualizing the Geographic Data

# Overview

This application contains a React component that displays a map with markers using the [react-map-gl] library. It fetches marker data from an API and displays them on the map, with popups providing additional information about each location.

## Prerequisites

- Node.js and npm installed on your machine.
  npm install

## Features

1. Displays geographical data as markers on a dynamic map using the 'react-map-gl' library.

2. Render an interactive map using the react-map-gl library.

3. Utilizing the Axios to retrieve geographic data from remote API.

4. Displayed markers on the map for each geographic location.

5. Show popups with information when markers are clicked.

6. Enabled various controls such as Navigation, Scale, Geolocation, and Fullscreen controls.


### Marker Customization

The `Pin` component takes two props: `type` and `size`. The `type` prop specifies the marker type, and the `size` prop specifies the size of the marker. The color of the marker is determined by the `colorEnum` object based on the `type` prop.


## Configuration and Execution

1. Obtained the Mapbox Access Token from the Mapbox account dashboard.

2. Replace "YOUR_MAPBOX_ACCESS_TOKEN" in the MapComponent.js file with our Mapbox access token.

3. Adjusted the 'api_url' to point to the API endpoint which is provided with geographical data

4. After rendering the MapComponent 

   run the react application
   Rename the `.env.example` file to `.env` and provide the Mapbox access token.       

   npm install // install all the necessary node modules //

   npm run start //starts the development server // 

   open another terminal and navigate to backend  
   
   nodemon server.js
   
   open the browser and navigate to localhost:8080 to see the component
   in action.


## API Integration

The application is fetching the location data from a remote API using Axios and displays markers on the map. The API integration is handled using Express on the backend. 

-- The frontend component initiates a request to the backend API endpoint to fetch location data.

-- The Express server fetches location data from API using Axios and returns it to the front.

-- front end processes the received data and displays markers on the map.


## Dependencies

React and React DOM:

React and React DOM are used to create and render the map component and other UI elements in the application.

react-map-gl:

The `react-map-gl` library provides the tools to display an interactive map within a React application. It includes components like `Map`, `Marker`, and various controls for navigation, scaling, and more.

Axios:

Axios is used to make HTTP requests to fetch location data from a remote API. The fetched data is then used to display markers on the map.

Express and CORS:

Express is used to set up a simple backend server that serves as an intermediary between the front end and the remote API. CORS middleware is implemented to handle cross-origin requests.

For the backend, the Express server provides an API endpoint that fetches data from the third-party API using Axios. The fetched data is then forwarded to the front end for rendering on the map.


## Contributing

git init // create a new repo

git clone repo // create a copy of remote repo

git status // check the status

git add . // add all changes to the file

git commit -m 'code changes' // commit changes

git push 



## Deploying the application to an EC2 instance

ssh -i keygen - generated an ssh key in the local machine

ssh -i path/of/key.pem ec2-username@instance-public-ip

sudo apt install nodejs
sudo apt update
sudo npm install // install the essential packages and dependencies


// Setup a Systemd service to manage react application

sudo systemctl start/stop/status my-frontend.service 

// enabling administrators to manage the status of the service

path : /etc/systemd/system/frontend.service

[Unit]
Description=My React Frontend Service
After=syslog.target
 
[Service]
User=your_username
WorkingDirectory=/path/to/your/frontend
ExecStart=/usr/bin/npm start
Restart=always

RestartSec=10
 
[Install]
WantedBy=multi-user.target

// set-up reverse proxy nginx to revert the port:3000 to port:8080

nginx server:

sudo systemctl start/stop/status nginx


path: /etc/nginx/sites-available/map


sudo ln -s /etc/nginx/sites-available/myapp /etc/nginx/sites-enabled/   
//Link configuration 

sudo nginx -t    //test nginx command


server {
  listen 8080;
  server_name 3.328...... (IP address);

  location / {
    proxy_pass http://localhost:3000/;
  }
}   


Access the application at https:EC2_ip_address:8080
