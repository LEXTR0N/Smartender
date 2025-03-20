# Smartender

Smartender (Smart Bartender) is a complete drink mixing system developed for the "Mobile Applications" course. It combines hardware controls with a mobile app interface to create automated cocktail preparation.

## Project Overview

The Smartender project consists of three main components:

1. **Mobile App (Flutter)** - A user-friendly interface for controlling the bartender, managing recipes, and user authentication
2. **Backend Server (Go)** - Handles user authentication, recipe storage, and device communication
3. **Hardware Control (Raspberry Pi)** - Controls the physical drink dispensing system

## Features

- User account management with secure authentication
- Drink recipe creation and management
- Remote control of the Smartender device
- Dark/Light mode support in the mobile app
- Secure JWT-based authentication system

## Repository Contents

This repository contains all components of the Smartender system:

- `/App` - Flutter mobile application
- `/Server` - Go backend server with RESTful API
- `/Hardware` - Hardware control code for Raspberry Pi
- `/CAD-Files` - Design files for the physical components
- `/Docs` - Project documentation

## Setup Instructions

### Mobile App

1. Install Flutter SDK (see [Flutter installation guide](https://flutter.dev/docs/get-started/install))
2. Navigate to the `App/smartender_flutter_app` directory
3. Run `flutter pub get` to install dependencies
4. Run `flutter run` to start the app in debug mode

### Backend Server

1. Install Go (see [Go installation guide](https://golang.org/doc/install))
2. Navigate to the `Server` directory
3. Create a `.env` file with the following variables:
   ```
   APP_PORT=8080
   APP_DB_USERNAME=postgres
   APP_DB_PASSWORD=postgres
   APP_DB_NAME=smartender
   ```
4. Run using Docker:
   ```
   docker-compose up --build
   ```
   Or run directly with Go:
   ```
   go run main.go
   ```

### Hardware Setup

*Hardware setup instructions and configuration details will be added in future updates.*

## API Endpoints

The backend server provides the following API endpoints:

### Authentication
- `POST /client/register` - Register a new user
- `POST /client/login` - Login and receive authentication token

### User Management
- `GET /user/{user_id}` - Get user details
- `PUT /user/{user_id}` - Update user details
- `DELETE /user/{user_id}` - Delete a user

### Device Control
- `GET /status` - Check system status
- `GET /smartender/register` - Register a new Smartender device

## Mobile App Structure

The Flutter app follows a clean architecture pattern with:
- Authentication handling
- Local storage for preferences
- TomTom Map API integration for location features
