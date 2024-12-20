

# Eat_Easy_Task

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
- [Architecture](#architecture)
- [State Management](#state-management)
- [Dependencies](#dependencies)
- [Networking](#networking)
- [Error Handling](#error-handling)
- [Caching](#caching)

## Overview

`Eat_Easy_Task` is a cross-platform mobile application built with Flutter, designed to provide users with an intuitive and engaging experience for exploring movies. It uses the TMDb API to fetch movie data and employs robust networking, caching, and state management strategies for optimal performance and user experience. The project supports Android, iOS, Linux, Web, macOS, and Windows.

## Features

- Browse a vast catalog of movies from TMDb.
- View detailed information about each movie, including synopsis, cast, ratings, and posters.
- Visually appealing UI with animations and smooth transitions using `flutter_staggered_animations`.
- Offline support through caching with `hive`.
- Theming support (light and dark themes).
- Network error handling and retry mechanism.
- Staggered grid layout for movie posters using `ad_gridview`.
- Search functionality to quickly find movies.
- Watchlist support with persistence.
- User-friendly error handling with customizable messages.

## Screenshots


<img src="https://github.com/user-attachments/assets/237455eb-9bdc-4877-8104-0279501f312b" width="300" alt="Screenshot 1">
<img src="https://github.com/user-attachments/assets/46d1ba10-2ede-4498-bfb3-2fd214bcf6e9" width="300" alt="Screenshot 2">
<img src="https://github.com/user-attachments/assets/c0384a51-3607-445b-a71d-0005154424a7" width="300" alt="Screenshot 3">
<img src="https://github.com/user-attachments/assets/f7339040-2987-45a0-a08c-81092ff777b1" width="300" alt="Screenshot 4">
<img src="https://github.com/user-attachments/assets/579ba84c-54e6-489f-8003-bbe6cad07249" width="300" alt="Screenshot 5">

## Getting Started

### Prerequisites

- [Flutter SDK](https://flutter.dev/docs/get-started/install) (version >= 3.0.0)
- [Android Studio](https://developer.android.com/studio) or [Xcode](https://developer.apple.com/xcode/) (for mobile development)

### Installation

1. Clone the repository:

   ```bash
   gh repo clone Fathi123-max/eat_easy_task
   ```

2. Navigate to the project directory:

   ```bash
   cd eat_easy_task
   ```

3. Install dependencies:

   ```bash
   flutter pub get
   ```

4. Run the app:

   ```bash
   flutter run
   ```

## Architecture

The app follows a layered architecture:

- **Presentation Layer:** Contains UI widgets, pages, and BLoCs.
- **Domain Layer:** Defines use cases and business logic.
- **Data Layer:** Handles data fetching from remote APIs and local storage.


```
lib
├── main.dart
├── core
│   ├── di
│   │   ├── modules
│   │   │   ├── network_module.dart
│   │   │   └── database_module.dart
│   │   └── injection_container.dart
│   ├── error
│   │   └── failures.dart
│   ├── constants
│   │   └── api_constants.dart
│   ├── routes
│   │   └── app_router.dart
│   └── theme
│       └── app_theme.dart
└── features
    └── movies
        ├── domain
        │   └── repositories
        │       └── movie_repository.dart
        ├── data
        │   ├── repositories
        │   │   └── movie_repository_impl.dart
        │   ├── models
        │   │   ├── movie_model.dart
        │   │   ├── movie_model.g.dart
        │   │   ├── person_model.dart
        │   │   └── person_model.g.dart
        │   └── datasources
        │       ├── movie_local_data_source.dart
        │       └── movie_remote_data_source.dart
        └── presentation
            ├── bloc
            │   ├── movie_list_bloc.dart
            │   ├── movie_list_event.dart
            │   └── movie_list_state.dart
            ├── widgets
            │   ├── animated_watchlist_button.dart
            │   ├── animated_movie_card.dart
            │   ├── animated_favorite_button.dart
            │   ├── staggered_movie_grid.dart
            │   ├── horizontal_movie_list.dart
            │   ├── move_cridits.dart
            │   ├── shimmer_placeholder.dart
            │   └── shimmer_placeholder.dart
            └── pages
                ├── movie_list_page.dart
                └── movie_details_page.dart
```

## State Management

The app uses the [BLoC pattern](https://pub.dev/packages/bloc) for state management, providing a clear separation of concerns and enhancing testability and maintainability.

## Dependencies

- `flutter_bloc`: For state management.
- `dio`: For making HTTP requests.
- `hive`: For local data storage and caching.
- `cached_network_image`: For efficient image loading and caching.
- `shimmer`: For loading placeholders.
- `equatable`: For value equality in Dart.
- `get_it` and `injectable`: For dependency injection.
- `logger`: For logging.
- `dartz`: For functional programming utilities.
- `flutter_staggered_animations`: For UI animations.
- `font_awesome_flutter`: For icons.
- `ad_gridview`: For staggered grid layouts.
- `connectivity_plus`: Check for network connectivity.
- `retry`: Retry HTTP requests.

## Networking

The app uses `dio` for networking, with the following features:

- Base URL and API key are defined in `api_constants.dart`.
- Includes interceptors for caching (`dio_cache_interceptor`), retrying failed requests (`dio_retry_plus`), error handling, and logging.

## Error Handling

The app implements centralized error handling using a custom error interceptor in `dio`. It handles various HTTP error codes (e.g., 401, 404, 422, 429, 500) and network connectivity issues, providing user-friendly error messages.

## Caching

The app uses `hive` and `dio_cache_interceptor_hive_store` for caching API responses, enabling offline access to recently viewed data and improving performance.


# Thanks For Time 
