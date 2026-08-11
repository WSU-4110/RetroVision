# RetroVision

**RetroVision** is a C++ video engine designed to simulate broadcast television channel switching, real-time media decoding, and aspect-correct rendering. Built with SDL3 and FFmpeg, RetroVision synchronizes video playback with continuous broadcast schedules and streams raw media frames through a hardware-accelerated rendering pipeline.

---

## Features

- **Live Channel Tuning & Switching:** Seamlessly switch between configured television channels using numpad or arrow controls with context-aware broadcast synchronization.
- **FFmpeg Integration:** Native video stream demuxing and decoding using `libavcodec`, `libavformat`, and `libswscale`.
- **YUV-to-RGBA Conversion:** Real-time color space conversion and frame buffer preparation via `libswscale`.
- **Aspect-Correct Viewport Rendering:** Dynamic scaling with automatic letterboxing and pillarboxing to preserve original video aspect ratios regardless of window resizing.
- **Configurable Channel Lineups:** Simple JSON-driven channel configuration system (`channels.json`) with support for channel metadata, media files, and fallback states.
- **Frame Pacing & Synchronization:** Low-latency frame fetching loop with frame-rate regulation to ensure smooth, natural video playback.

---

## Tech Stack

- **Language:** C++20
- **Multimedia & Windowing:** SDL3
- **Graphics API:** OpenGL 3.3 Core Profile
- **Media Decoding Pipeline:** FFmpeg (`libavcodec`, `libavformat`, `libswscale`, `libavutil`)
- **Configuration Parsing:** `nlohmann/json`
- **Build System & Package Management:** CMake, Ninja, `vcpkg`, MSYS2 (UCRT64) / MinGW-w64

---

## Prerequisites

Before building RetroVision, ensure your development environment is set up with the following tooling and libraries:

### 1. Environment & Toolchain
- **MSYS2 (UCRT64 Environment)** on Windows (or standard Linux/macOS terminal environment)
- **C++ Compiler:** GCC, Clang, or MSVC with C++20 support

### 2. Build Systems
- **CMake** (version 3.20 or higher)
- **Ninja** build tool

### 3. External Dependencies
Installed via `vcpkg` or your platform package manager:
- **SDL3** (`sdl3`)
- **FFmpeg** (`ffmpeg` providing `libavcodec`, `libavformat`, `libswscale`, `libavutil`)
- **nlohmann-json** (`nlohmann-json`)

---

## Building the Application

### Option A: Using Built-in Build Scripts (Recommended)

#### **On MSYS2 / Bash (UCRT64):**
Execute the shell build script from the project root directory:
```bash
./build.sh