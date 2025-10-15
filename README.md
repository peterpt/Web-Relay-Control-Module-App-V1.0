# Web-Relay-Control-Module-App-V1.0

# Relay Control Panel

A modern, feature-rich Python GUI for discovering, configuring, and controlling network-based relay modules, specifically designed for the **Web Relay Control V1.0** hardware.

![Application Screenshot](https://github.com/peterpt/Web-Relay-Control-Module-App-V1.0/blob/main/app.png)

## Overview

This application provides a robust and user-friendly graphical interface to manage one or more "Web Relay Control V1.0" (GeekTeches NC1601) modules on a network. It was built from the ground up to handle the specific quirks of the hardware and to provide a seamless user experience, from initial discovery to daily operation in a kiosk environment.

The application is written in Python using the Tkinter library for the GUI and is designed to be cross-platform (tested on Linux).

## Key Features

This project is more than just a simple controller. It includes a wide range of advanced features designed for stability, customization, and ease of use.

### UI & Live Control
*   **Live Grid Interface:** A clear, grid-based layout showing all relays for the selected module.
*   **Click-to-Toggle:** Instantly toggle any relay on or off by clicking its zone.
*   **Polished UI:** Features a "pressed" effect on click and a "smart refresh" system that updates icons without any blinking or flickering.
*   **Responsive Layout:** The interface and icons dynamically resize to fit any window size, looking great on both small screens and high-resolution displays.

### Kiosk & Touchscreen Mode
*   **Fullscreen Kiosk Mode:** Launch the app in a borderless, fullscreen mode (`-f` flag), perfect for dedicated touch panels.
*   **Escape Hatch:** Easily exit fullscreen mode by pressing the `ESC` key, which restores the windowed mode and the menu bar.
*   **Multi-Monitor Aware:** Correctly enters fullscreen on the primary monitor without stretching across multiple displays.

### Advanced Icon System
*   **Fully Customizable Icons:** Assign a unique ON and OFF icon to each individual relay.
*   **Visual Icon Picker:** A built-in, user-friendly icon picker displays a visual grid of all available images from the `/icons` folder, allowing for easy selection.
*   **Automatic Icon Sanitizer:** At startup, the app automatically processes all images in the `/icons` folder:
    *   Converts any non-PNG images (like JPGs or GIFs) to the PNG format.
    *   Resizes all source icons to a standard, high-resolution 256x256, ensuring quality.
*   **Robust Fallback System:** If a custom or default icon file is ever missing, the application will **not crash**. It will gracefully fall back to drawing a colored circle (green for ON, red for OFF) as a status indicator.

### Discovery & Configuration
*   **Factory Device Scan:** A dedicated function to scan the `192.168.1.x` network for new, unconfigured modules.
*   **Manual Entry:** Manually add a module by specifying its IP address and Command Path.
*   **Powerful Network Configuration:** Change a module's IP address and Command Path directly from the application's management window.

### Error Handling & Recovery
*   **Online/Offline Detection:** The app intelligently detects if a module is offline and disables its controls, providing clear visual feedback.
*   **"Smart Finder" for Lost Modules:** If a module's IP has changed, the Smart Finder can locate it on the local network using a tiered search algorithm.
*   **Network Reachability Test:** A traceroute-based pre-check prevents you from accidentally moving a module to an IP address that is unreachable from your computer.
*   **Graceful Shutdown:** The application correctly handles `CTRL+C` in the terminal, ensuring a clean exit without leaving graphical artifacts.

### Internationalization
*   **Multi-Language Support:** The UI has been translated into multiple languages. The selected language is saved to the configuration file.
*   **Splash Screen:** Displays a customizable splash screen on startup with an embedded, Base64-encoded image.

## Target Hardware

This application was specifically developed and tested for the **GeekTeches NC1601 / Web Relay Control V1.0** module. While it may work with other similar web-based relays, it is tailored to the specific HTML responses and configuration methods of this board.

## Requirements

*   Python 3.x
*   The external libraries listed in `requirements.txt`.

## Installation

1.  **Clone the repository (or download the files):**
    ```bash
    git clone (https://github.com/peterpt/Web-Relay-Control-Module-App-V1.0)
    cd relay-control
    ```

2.  **Install the required libraries:**
    ```bash
    pip3 install -r requirements.txt
    ```

## Usage

1.  **Run the application:**
    *   **Windowed Mode:**
        ```bash
        python3 wrcm.py
        ```
    *   **Fullscreen Kiosk Mode:**
        ```bash
        python3 wrcm.py -f
        ```
2.  **Configuration:** The `config.ini` file will be created automatically on the first run. Use the "Find Devices" or "Configure" menus to add and set up your relay modules.

## Acknowledgments

This application was developed through a collaborative process with a user providing detailed specifications, testing, and feedback.

**Code assistant:** Google Gemini Pro Model

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
