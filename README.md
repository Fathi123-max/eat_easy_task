Okay, let's craft a more informed README.md based on the combined knowledge from the file structure, code snippets (especially `main.dart` and `network_module.dart`), and the Xcode project details.

# movie_app

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/YOUR_USERNAME/YOUR_REPO/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Flutter Version](https://img.shields.io/badge/Flutter-%3E=3.0.0-blue)](https://flutter.dev)

A Flutter application for browsing and discovering movies, leveraging the TMDb API.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Architecture](#architecture)
- [State Management](#state-management)
- [Dependencies](#dependencies)
- [Networking](#networking)
- [Error Handling](#error-handling)
- [Caching](#caching)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview

`movie_app` is a cross-platform mobile application built with Flutter, designed to provide users with an intuitive and engaging experience for exploring movies. It uses the TMDb API to fetch movie data and employs robust networking, caching, and state management strategies for optimal performance and user experience. The project supports Android, iOS, Linux, Web, macOS, and Windows.

## Features

- Browse a vast catalog of movies from TMDb.
- View detailed information about each movie, including synopsis, cast, ratings, and posters.
- Search for movies by title.
- Visually appealing UI with animations and smooth transitions using `flutter_staggered_animations`.
- Offline support through caching with `hive`.
- Theming support (light and dark themes).
- Network error handling and retry mechanism.
- Staggered grid layout for movie posters using `ad_gridview`.

## Screenshots

*(Include screenshots or GIFs of your app here. Use descriptive captions)*

<img src="screenshots/screenshot1.png" width="300" alt="Movie List Screen">
<img src="screenshots/screenshot2.png" width="300" alt="Movie Details Screen">

## Getting Started

### Prerequisites

- [Flutter SDK](https://flutter.dev/docs/get-started/install) (version >= 3.0.0)
- [Android Studio](https://developer.android.com/studio) or [Xcode](https://developer.apple.com/xcode/) (for mobile development)
- [CMake](https://cmake.org/download/) and GTK development libraries (for Linux development)

### Installation

1. Clone the repository:

   ```bash
   git clone [invalid URL removed]
   ```

2. Navigate to the project directory:

   ```bash
   cd movie_app
   ```

3. Install dependencies:

   ```bash
   flutter pub get
   ```

## Usage

*For Android/iOS:*

```bash
flutter run
```

*For Linux:*

```bash
cd linux
cmake -S . -B build
cmake --build build
./build/mahr
```

## Architecture

The app follows a layered architecture:

-   **Presentation Layer:** Contains UI widgets, pages, and BLoCs.
-   **Domain Layer:** Defines use cases and business logic.
-   **Data Layer:** Handles data fetching from remote APIs and local storage.

## State Management

The app uses the [BLoC pattern](https://pub.dev/packages/bloc) for state management, providing a clear separation of concerns and enhancing testability and maintainability.

## Dependencies

-   `flutter_bloc`: For state management.
-   `dio`: For making HTTP requests.
-   `hive`: For local data storage and caching.
-   `cached_network_image`: For efficient image loading and caching.
-   `shimmer`: For loading placeholders.
-   `equatable`: For value equality in Dart.
-   `get_it` and `injectable`: For dependency injection.
-   `logger`: For logging.
-   `dartz`: For functional programming utilities.
-   `flutter_staggered_animations`: For UI animations.
-   `font_awesome_flutter`: For icons.
-   `ad_gridview`: For staggered grid layouts.
-   `connectivity_plus`: Check for network connectivity.
-   `retry`: Retry http request.

## Networking

The app uses `dio` for networking, with the following features:

-   Base URL and API key are defined in `api_constants.dart`.
-   Includes interceptors for caching (`dio_cache_interceptor`), retrying failed requests (`dio_retry_plus`), error handling, and logging.

## Error Handling

The app implements centralized error handling using a custom error interceptor in `dio`. It handles various HTTP error codes (e.g., 401, 404, 422, 429, 500) and network connectivity issues, providing user-friendly error messages.

## Caching

The app uses `hive` and `dio_cache_interceptor_hive_store` for caching API responses, enabling offline access to recently viewed data and improving performance.

## License

[MIT](LICENSE)

## Contact

[Fathi Wehba](fathiwehba5@example.com)
