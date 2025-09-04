# Sweap - Music Discovery App 🎵

A React Native mobile application that helps users discover new music through an intuitive swipe-based interface, similar to Tinder but for songs. Users can swipe right to like songs and left to pass, with the app eventually generating personalized Spotify playlists based on their preferences.

## Screenshots

### Onboarding Flow
![Image](https://github.com/user-attachments/assets/b8a7fdbb-476c-4cb8-86c8-bce3a7cadb40)
![Image](https://github.com/user-attachments/assets/588bc4cb-d29b-48c8-bb8b-e4c312a925b5)

*The app introduces users to the swiping concept with animated examples*

### Genre & Decade Selection

![Image](https://github.com/user-attachments/assets/4f6bbec3-b522-47cb-b0f9-60c7a32b815a)

*Users select their preferred music genres and decades for personalized recommendations*

### Music Discovery Interface  

![Image](https://github.com/user-attachments/assets/4f6bbec3-b522-47cb-b0f9-60c7a32b815a)

*The main interface displays album artwork with song and artist information*

## Features

- **Intuitive Swipe Interface**: Tinder-style card swiping for music discovery
- **Spotify Integration**: Seamless authentication and API integration with Spotify
- **Personalized Recommendations**: Genre and decade-based music suggestions
- **Animated Onboarding**: Interactive tutorial showing users how to swipe
- **Preference Selection**: Multiple genre and decade options for customized discovery
- **Playlist Generation**: Automatic Spotify playlist creation based on user preferences
- **Offline Fallback**: Sample data when Spotify API is unavailable

## Technologies Used

### Core Framework
- **React Native**: Cross-platform mobile app development
- **Expo**: Development platform and toolchain
- **TypeScript**: Type-safe JavaScript development

### Navigation & UI
- **React Navigation**: Stack navigation between screens
- **React Native Gesture Handler**: Smooth gesture recognition for swiping
- **Expo Linear Gradient**: Visual gradient effects
- **Expo Vector Icons (Ionicons)**: Icon library

### External APIs & Services
- **Spotify Web API**: Music data and playlist management
- **Expo AuthSession**: OAuth authentication flow
- **AsyncStorage**: Local data persistence

### Animation & Visual Effects
- **React Native Animated API**: Smooth card animations and transitions
- **ImageBackground**: Album artwork display
- **Gesture-based interactions**: Pan gesture handling for card swiping

## App Architecture

### Screen Flow
1. **StartupPage**: Animated onboarding with swipe tutorials
2. **LoginPage**: Spotify OAuth authentication
3. **PreferencePage**: Genre and decade selection
4. **MainPage**: Core music discovery interface

### Key Components
- **Navigation Stack**: Native stack navigator managing screen transitions
- **Gesture Handler**: PanGestureHandler for swipe detection and animations
- **Spotify Service**: Centralized API communication and token management
- **Preference System**: Multi-select genre and decade filtering

## Installation & Setup

### Prerequisites
- Node.js (v14 or higher)
- Expo CLI
- Spotify Developer Account
- iOS Simulator or Android Emulator

### Getting Started

1. **Clone the repository**
   ```bash
   git clone [your-repo-url]
   cd sweap-music-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Configure Spotify API**
   - Create a Spotify app at [Spotify Developer Dashboard](https://developer.spotify.com/dashboard)
   - Update `SpotifyService.js` with your client ID
   - Configure redirect URIs in your Spotify app settings

4. **Start the development server**
   ```bash
   expo start
   ```

5. **Run on device/simulator**
   - Press `i` for iOS simulator
   - Press `a` for Android emulator
   - Scan QR code with Expo Go app for physical device testing

## Configuration

### Spotify Integration
Update the `spotifyAuthConfig` in `SpotifyService.js`:

```javascript
const spotifyAuthConfig = {
  clientId: 'your-spotify-client-id',
  scopes: [
    'user-read-private', 
    'user-read-email',
    'user-top-read',
    'user-read-recently-played'
  ],
  // ... other config
};
```

### Genre Mapping
The app includes a genre mapping system to translate UI selections to Spotify's genre seeds:

```javascript
const genreMapping = {
  'POP': 'pop',
  'Rock': 'rock',
  'Hip Hop': 'hip-hop',
  // ... additional mappings
};
```

## Core Functionality

### Music Discovery Algorithm
- Filters songs by selected genres and decades
- Uses Spotify's recommendation engine
- Provides fallback sample data when API is unavailable
- Supports year range filtering for decade-based discovery

### Swipe Mechanics
- **Right Swipe**: Add to liked songs
- **Left Swipe**: Pass on the song
- **Threshold Detection**: Configurable swipe distance for action triggering
- **Visual Feedback**: Card rotation and opacity changes during swipe gestures

### Data Persistence
- Spotify access tokens stored securely
- User preferences maintained across sessions
- Liked/passed song tracking for playlist generation

## Development Notes

### Debug Features
- Development-only debug information display
- Console logging for API interactions and authentication flow
- Redirect URI logging for Spotify app configuration

### Error Handling
- Graceful fallbacks when Spotify API is unavailable
- User-friendly error messages for authentication failures
- Network connectivity detection and handling

## Future Enhancements

- [ ] Playlist creation and management
- [ ] Social sharing features
- [ ] Music preview playback
- [ ] Advanced filtering options
- [ ] User listening history analytics
- [ ] Cross-platform playlist syncing

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Spotify Web API for music data
- React Native community for excellent documentation
- Expo team for streamlined development experience
