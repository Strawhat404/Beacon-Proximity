# BeaconX Pro W6 API

This project provides a robust API for real-time communication and management of MOKOSmart BeaconX Pro W6 wristband beacons. It leverages Django, Django REST Framework, and Django Channels to deliver real-time proximity tracking and notification features.

## Features

-   **Device Management**: Complete CRUD operations for BeaconX Pro W6 devices.
-   **Proximity Tracking**: Real-time tracking of distance between users and beacons.
-   **Real-time Notifications**: Instant alerts triggered by beacon interactions and proximity events.
-   **WebSocket Integration**: Live updates for proximity events and notifications via WebSockets.
-   **Swagger Documentation**: Interactive API documentation using Swagger UI.

## Technology Stack

-   **Backend Framework**: Django & Django REST Framework (DRF)
-   **Real-time Capabilities**: Django Channels & Redis
-   **Database**: SQLite (Default for development)
-   **API Documentation**: drf-yasg (Swagger/Redoc)

## Prerequisites

-   Python 3.8+
-   Redis Server (Required for Django Channels)

## Installation

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd Beacon-Proximity
    ```

2.  **Create and activate a virtual environment:**

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4.  **Apply database migrations:**

    ```bash
    python manage.py migrate
    ```

5.  **Start the Redis server:**
    Ensure you have Redis installed and running on your machine (default port 6379).

6.  **Run the development server:**

    ```bash
    python manage.py runserver
    ```

## API Documentation

The API endpoints are fully documented using Swagger UI. Once the server is running, you can access the documentation at:

-   **Swagger UI**: `http://127.0.0.1:8000/swagger/`
-   **Redoc**: `http://127.0.0.1:8000/redoc/`

## WebSocket Usage

Real-time updates are available via WebSocket connections.

-   **Endpoint**: `ws://<host>/ws/beacon/`
-   **Authentication**: Requires an authenticated user session.

### Events

-   **Proximity Update**: Received when a beacon proximity event is recorded.
-   **Notification**: Received when a new notification is generated.

## Project Structure

-   `beacon_project/`: Main Django project configuration.
-   `Realtime/`: Core application containing models, views, consumers, and routing logic.
-   `manage.py`: Django's command-line utility.