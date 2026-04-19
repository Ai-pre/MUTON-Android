# MUTON-Android

MUTON-Android is the Android client for MUTON, a real-time multimodal dialogue assistance system for hearing-impaired users, especially users who rely on oral communication rather than sign language. The app streams camera frames and audio chunks to the backend, receives subtitles and multimodal summaries, and displays the result in a mobile interface designed for practical conversation support.

## Why This App Exists

Many captioning tools can convert speech into text, but they still struggle to deliver the emotional and contextual cues that matter in real conversation. The Android client exists to make the MUTON backend usable in a real mobile setting by capturing live face and voice input, synchronizing the user interaction flow, and presenting subtitle, visual emotion, and summary output in one place.

In P-project, the main goal was to prove that an Android app could be connected to a full multimodal pipeline. In Graduation Project 2, the frontend role became more important: the app had to support a more stable live demo, dynamic backend address updates, and clearer UI feedback while the backend model path evolved from a custom fusion structure to a Qwen2.5-Omni based summary pipeline.

![MUTON Android main screen](https://github.com/user-attachments/assets/67b02611-b136-4166-8215-c3986d915b1e)

![MUTON Android live screen](https://github.com/user-attachments/assets/ec7bd87a-aca3-4b09-bdc4-7fe2890d4703)

## What The Android App Does

- captures camera frames for visual input
- captures microphone audio for streaming STT
- sends multimodal requests to the MUTON backend
- displays visual emotion, subtitle text, and multimodal summary output
- loads the active backend address dynamically from `backend_url.json`
- supports the wider mobile flow around the demo, including home, login, settings, and record-related screens

## Role In Graduation Project 2

The Android app is not just a thin transport layer. In Graduation Project 2, it became part of the system-level improvement process:

- the backend URL flow was stabilized through remote configuration
- the live UI was refined so that subtitle, emotion, and summary could be shown together
- the app remained compatible while the backend summary architecture changed
- the overall mobile experience was shaped for demonstration and real-time usability rather than model experimentation alone

## Backend Relationship

This repository contains only the Android client. Backend runtime, API details, and model training live in the main repository:

- backend repo: [Ai-pre/MUTON](https://github.com/Ai-pre/MUTON)

The app reads the current backend address from:

```text
https://raw.githubusercontent.com/Ai-pre/MUTON/server_main/backend_url.json
```

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

## Run

Open the project in Android Studio and run the `app` module on a device or emulator with camera and microphone access.

For the best demo behavior, make sure:

- the backend server is already running
- the current Cloudflare tunnel URL has been published to `backend_url.json`
- the device has camera, microphone, and network access

## Notes

- This repository is focused on the Android client experience.
- The recommended current backend path is `whisper-1` for STT and `Qwen2.5-Omni + ko_stage LoRA` for multimodal summary generation.
- Detailed API and architecture documentation remain in the main MUTON repository.
