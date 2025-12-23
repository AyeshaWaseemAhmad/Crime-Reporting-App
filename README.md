# Crime Reporting App

An Android application that allows users to report crimes with location tracking, severity classification, and secure user authentication.

## Features

- **User Authentication**: Secure signup and login system
- **Crime Reporting**: Report crimes with detailed information including:
  - Crime name and description
  - Offense type
  - Severity level (Light, Moderate, Extreme)
  - GPS location coordinates
- **Location Services**: Integrated Google Maps for location tracking
- **Database Management**: SQLite database for storing user and crime data
- **Crime Management**: View and delete reported crimes

## Technology Stack

- **Language**: Java
- **Platform**: Android
- **Database**: SQLite
- **Maps**: Google Maps Android API
- **Minimum SDK**: Android API level (check `build.gradle`)

## Project Structure

```
Crime Reporting App/
├── java/com/example/madproject/
│   ├── MainActivity.java          # Login/Signup screen
│   ├── MainActivity2.java         # User registration
│   ├── MainActivity3.java         # User login
│   ├── MainActivity4.java         # Crime reporting form
│   ├── MainActivity5.java         # Crime list view
│   ├── MapsActivity.java          # Google Maps integration
│   ├── DatabaseHelper.java        # SQLite database operations
│   ├── Crimes.java                # Crime data model
│   ├── MyAdapter.java             # RecyclerView adapter
│   └── MyLocationListener.java    # Location services
├── res/
│   ├── layout/                    # XML layout files
│   ├── drawable/                  # App icons and images
│   └── values/                    # Strings, colors, themes
└── AndroidManifest.xml            # App configuration

```

## Database Schema

### User Table (`user_info`)

- `username` (Primary Key)
- `password`
- `email` (Unique)
- `uni_id` (Unique)

### Crimes Table (`crime_info`)

- `id` (Primary Key, Auto-increment)
- `crimename`
- `description`
- `offense`
- `severity`
- `latitude`
- `longitude`
- `username_foreign` (Foreign Key → user_info.username)

## Setup Instructions

### Prerequisites

- Android Studio (latest version)
- Android SDK
- Google Maps API key

### Installation

1. **Clone the repository**

   ```bash
   git clone <repository-url>
   cd Crime-Reporting-App
   ```

2. **Get Google Maps API Key**

   - Go to [Google Cloud Console](https://console.cloud.google.com/)
   - Create a new project or select an existing one
   - Enable "Maps SDK for Android"
   - Create an API key
   - Add the API key to `res/values/google_maps_api.xml` (create if doesn't exist)

3. **Open in Android Studio**

   - Open Android Studio
   - Select "Open an existing project"
   - Navigate to the project directory

4. **Build and Run**
   - Sync Gradle files
   - Connect an Android device or start an emulator
   - Click "Run" or press `Shift + F10`

## Usage

1. **Sign Up**: Create a new account with username, password, email, and university ID
2. **Login**: Sign in with your credentials
3. **Report Crime**:
   - Fill in crime details
   - Select offense type and severity
   - Allow location permissions for GPS tracking
   - Submit the report
4. **View Reports**: See all reported crimes in a list
5. **Delete Reports**: Remove reports by clicking the delete button

## Permissions

The app requires the following permissions:

- `ACCESS_FINE_LOCATION`: For GPS location tracking

## Security Notes

⚠️ **Important**: This is a development project. For production use:

- Implement password hashing (bcrypt, Argon2)
- Use secure authentication tokens
- Encrypt sensitive data
- Implement proper API key management
- Add input validation and sanitization

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available for educational purposes.

## Author

Developed as part of a Mobile Application Development (MAD) project.

---

**Note**: Make sure to add your Google Maps API key before running the app. The app will not function properly without it.
