# Smart School Bus Tracker

## Overview
The **Smart School Bus Tracker** is a comprehensive system that provides real-time location updates for school buses, allowing parents, students, and school administrators to track bus movement. This project integrates various technologies, including a Flutter-based mobile front-end, a backend server using Flask with a MySQL database, and Google Maps APIs to deliver a seamless tracking experience.

## Project Structure
The project comprises three main components:

1. **Front-end (Flutter Application):** The mobile app is responsible for user interactions, including sign-in, registration, and bus tracking on a map.
2. **Backend (Python Flask Server):** Handles user authentication, registration, and provides APIs for retrieving the latest bus locations and updating the bus location.
3. **Database (MySQL):** Stores user credentials, bus information, routes, and locations.

## Features
- **User Authentication:** Users can register and log in securely using hashed passwords.
- **Google Maps Integration:** The app integrates Google Maps to provide real-time location tracking of school buses.
- **Bus Route Visualization:** Users can view the route taken by the bus from the school to different stops.
- **Expandable Map Interface:** Users can expand and collapse the map interface for convenience.
- **Sign Out Feature:** Easy log out option for enhanced security.

## Technologies Used
- **Flutter (Front-end):** A cross-platform mobile app development framework.
- **Python & Flask (Backend):** For server-side logic and handling API requests.
- **MySQL (Database):** Stores user, bus, and route information.
- **Google Maps JavaScript API:** Provides visualization for bus location and routes.
- **SQLAlchemy:** Used as an ORM for interacting with the MySQL database.
- **CORS (Cross-Origin Resource Sharing):** Enabled for allowing the front-end to communicate with the backend.

## Setup Instructions

### Prerequisites
- Python 3.x
- Flutter SDK
- MySQL Server
- Android Studio (for running Flutter applications)

### Backend Setup
1. **Install Python Dependencies**:
   - Create a virtual environment: `python -m venv venv`
   - Activate the virtual environment:
     - On Windows: `venv\Scripts\activate`
     - On Linux/Mac: `source venv/bin/activate`
   - Install dependencies: `pip install -r requirements.txt`

2. **Database Configuration**:
   - Install MySQL Server and create a database called `bus_tracker_db`.
   - Import the provided SQL scripts to create tables (`user`, `bus_location`, `route`, etc.) and insert sample data.

3. **Run the Flask Server**:
   - Set environment variables for Flask (optional):
     ```bash
     export FLASK_APP=app.py
     export FLASK_ENV=development
     ```
   - Run the server:
     ```bash
     flask run --host=0.0.0.0 --port=5000
     ```

### Frontend Setup
1. **Install Flutter Dependencies**:
   - Navigate to the Flutter project directory and run:
     ```bash
     flutter pub get
     ```

2. **Run the Application**:
   - Open Android Studio and load the Flutter project.
   - Connect an Android device or start an emulator.
   - Run the app:
     ```bash
     flutter run
     ```

### Database Schema
- **User Table**: Stores user credentials (username, hashed password, email).
- **Bus Location Table**: Tracks the current location of buses (latitude, longitude, timestamp).
- **Route Table**: Stores information about the bus routes including start, end, and stops.
- **Bus Table**: Stores information about buses including bus number and route information.

## API Endpoints
- **POST /api/register**: Register a new user.
- **POST /api/login**: Authenticate user login.
- **POST /api/update_bus_location**: Update bus location in the database.
- **GET /api/get_bus_location**: Retrieve the current location of the bus.

## Usage Guide
1. **Registration and Login**
   - New users can register by providing a username, password, and email.
   - Existing users can log in to view the bus location and access the tracking features.

2. **Tracking Bus Location**
   - After logging in, users can view the bus route and track the live location of the bus.
   - The app shows an expandable map that displays the route along with the bus's current location.

3. **Updating Bus Location**
   - The backend receives updates about the bus's current location through the `/api/update_bus_location` endpoint, which is called periodically.

## Future Improvements
- **Push Notifications**: Notify users about bus arrival at their stop.
- **ETA Calculation**: Display the estimated time of arrival for each stop based on real-time traffic.
- **Admin Interface**: Allow school administrators to manage routes and buses.
- **Geofencing**: Alert users when the bus is approaching their stop.

## Troubleshooting
- **Connection Issues**: Ensure the backend Flask server is running, and the mobile app is pointed to the correct server IP.
- **Database Issues**: Check that MySQL server is running and configured properly with the right credentials.
- **Google Maps Not Loading**: Verify that the Google Maps API key is correctly set and enabled for required services.

## License
Please feel free to use and modify the code for personal or educational purposes.

## Contributors
- **[Sanchit Patel]**: Full-stack development and project management.
- **[Parth Patel]**: Front-End development.
- **[Dhruvesh Patel]**: BackEnd development and project management.

