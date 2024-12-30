## Outline for Implementing a Speech-to-Text App on Linux Using DeepGram API

### **1. Project Overview**
- **Purpose**: Develop a GUI-based Linux application for real-time speech-to-text transcription using the DeepGram API.
- **Target System**: OpenSUSE Tumbleweed with KDE Plasma.
- **Key Features**:
  - Store and manage DeepGram API key persistently.
  - Real-time transcription with start/stop buttons and customizable shortcut keys.
  - Simulated keystroke output for transcription.
  - Microphone selection (USB prioritized, Bluetooth optional).
  - Dockable GUI with system tray integration.

---

### **2. Core Functionalities**

#### **2.1 Persistent Storage**
- Store the DeepGram API key securely (e.g., using encrypted storage or configuration files in the user's home directory).
- Store user preferences such as:
  - Microphone selection.
  - Shortcut keys for starting/stopping transcription.

#### **2.2 Real-Time Transcription**
- Capture audio input from the selected microphone.
- Send audio data to the DeepGram API for processing in real time.
- Simulate keystrokes to insert transcribed text into active applications.

#### **2.3 GUI Features**
- Attractive and functional GUI with the following components:
  - Input field for entering and saving DeepGram API key.
  - Dropdown menu for microphone selection (USB prioritized, Bluetooth optional).
  - Buttons for starting/stopping transcription with status display (e.g., "Capturing in Progress").
  - Settings panel to configure shortcut keys for start/stop functionality.
  - Minimize to system tray functionality.

#### **2.4 System Tray Integration**
- Dock application to the system tray when minimized or exited.
- Tray icon context menu with options:
  - Show: Restore the GUI.
  - Hide: Minimize to tray.
  - Quit: Exit the application.

---

### **3. Implementation Details**

#### **3.1 Technology Stack**
- Programming Language: Python (for cross-platform support and ease of development).
- GUI Framework: PyQt5 or PyQt6 (for KDE Plasma compatibility and attractive UI design).
- Audio Handling: PyAudio or sounddevice library for capturing audio input.
- API Integration: `requests` or `httpx` library for interacting with the DeepGram API.

#### **3.2 Persistent Storage**
- Use `configparser` or `json` module to store user settings in a configuration file (`~/.speech_to_text_app/config`).
- For sensitive data like the API key, consider encrypting it using libraries like `cryptography`.

#### **3.3 Audio Input Management**
- List available microphones using PyAudio or sounddevice.
- Allow users to select their preferred microphone from a dropdown menu in the GUI.
- Save microphone selection persistently between sessions.

#### **3.4 Real-Time Transcription Workflow**
1. Start capturing audio from the selected microphone when transcription begins.
2. Stream audio chunks to the DeepGram API endpoint using WebSocket or HTTP streaming.
3. Receive transcribed text from the API and simulate keystrokes using a library like `pynput`.

#### **3.5 Shortcut Key Configuration**
- Allow users to set global shortcuts for starting and stopping transcription via a settings panel in the GUI.
- Use libraries like `keyboard` or `pynput` to register and listen for global hotkeys.

#### **3.6 System Tray Integration**
- Use PyQt's system tray functionality to implement minimize-to-tray behavior.
- Provide context menu options (Show, Hide, Quit) for managing the application from the tray icon.

---

### **4. User Interface Design**

#### **4.1 Main Window**
- Sections:
  - API Key Management:
    - Input field with save button for storing the DeepGram API key.
  - Microphone Selection:
    - Dropdown menu listing available microphones.
    - Refresh button to detect new devices.
  - Transcription Controls:
    - Start/Stop buttons with real-time status display (e.g., "Capturing in Progress").
    - Shortcut key configuration panel.

#### **4.2 Settings Panel**
- Options:
  - Configure shortcut keys for starting/stopping transcription.
  - Toggle between real-time and batch processing modes (future feature).

#### **4.3 System Tray Icon**
- Context Menu:
  - Show: Restore main window from tray.
  - Hide: Minimize main window to tray.
  - Quit: Exit application.

---

### **5. Future Enhancements**
- Add batch processing mode with a separate UI workflow for uploading pre-recorded audio files and retrieving transcriptions.
- Support additional operating systems (e.g., Windows, macOS) by abstracting platform-specific features like tray integration and shortcut handling.
- Add support for Bluetooth microphones if feasible.

---

### **6. Testing Plan**
1. Test on OpenSUSE Tumbleweed with KDE Plasma environment:
   - Verify microphone detection (USB prioritized).
   - Confirm real-time transcription accuracy via DeepGram API integration.
   - Validate shortcut key functionality and persistence of user settings across sessions.
2. Conduct usability testing to ensure an intuitive user experience.

 