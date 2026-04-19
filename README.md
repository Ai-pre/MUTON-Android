# MUTON-Android

MUTON-Android is the Android client for MUTON, a real-time multimodal dialogue assistance system for hearing-impaired users. The app streams camera frames and audio chunks to the backend, receives subtitles and multimodal summaries, and displays the results in a mobile UI.

This repository was split out from the Android app branch of the main MUTON project so that the mobile client can be documented, versioned, and shared independently from the backend and model training code.

## Main Responsibilities

- capture camera frames for visual input
- capture microphone audio for streaming STT
- send requests to the MUTON backend
- show visual emotion, subtitle text, and multimodal summary output
- load the active backend address from `backend_url.json`

## Project Structure

```text
MUTON-Android/
  app/
    src/main/java/com/example/myapplication/
    src/main/res/
  gradle/
  build.gradle.kts
  settings.gradle.kts
```

## Backend Connection

The Android app is designed to work with the backend repository:

- backend repo: [Ai-pre/MUTON](https://github.com/Ai-pre/MUTON)

The app reads the current backend address from:

```text
https://raw.githubusercontent.com/Ai-pre/MUTON/server_main/backend_url.json
```

## Run

Open the project in Android Studio and run the `app` module on a device or emulator with camera and microphone access.

## Notes

- This repository contains only the Android client.
- Backend runtime, API details, and model training live in the main MUTON repository.
