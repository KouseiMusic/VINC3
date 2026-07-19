<p align="center"><img width="190" height="193" alt="vinc3banner" src="https://github.com/user-attachments/assets/ba115c1a-ce26-4999-8672-56a88455eabb" /></p>

_<p align="center">Audio Analysis & DSP Metering. Frequency Visualization & Audio Monitoring.</p>_

---

![Version](https://img.shields.io/badge/Version-2.0.0-brightgreen?style=flat-square)
![macOS Support](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-000000?style=flat-square&logo=apple&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Universal-black?labelColor=606060&style=flat-square&logo=apple&logoColor=white)
![Format](https://img.shields.io/badge/Format-Standalone-00CED1?style=flat-square)
![DAW](https://img.shields.io/badge/DAW-All-000000?style=flat-square&logo=abletonlive&logoColor=white)


---

<img width="1439" height="868" alt="vinc3preview" src="https://github.com/user-attachments/assets/8f94e5c6-8586-49af-a916-3a74b9249dbc" />

---

## 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **3D Spectrogram Engine**: A three-dimensional view of your audio's frequency content, updated in real time. Visualise how energy is distributed across the spectrum over time, with five distinct animation modes to suit different analytical or aesthetic preferences.
- **Full Metering Suite**: Nine independent monitoring modules covering loudness, dynamics, stereo imaging, waveform, frequency analysis, and pitch; everything needed to make informed mixing and mastering decisions without switching tools.
- **Standalone Application**: Runs as a native macOS application. No browser, no subscription, no account. Open it and it works.
- **Fully Offline**: No internet connection is ever required or used. All processing happens locally on your machine.
- **Floating Module Windows**: Each metering module is an independent window. Drag them anywhere on screen, resize them to any size and save that arrangement as your default layout. Different sessions, different setups.
- **Seven Visual Themes**: Switch between Teal, Pink, Purple, Green, White, Blue and Windows 98 to match your studio environment or personal preference.
- **Minimalist Interface**: Dark-themed and high-contrast, designed to be readable at a glance in low-light studio environments without distracting from the listening experience.

---

## 𝐒𝐲𝐬𝐭𝐞𝐦 𝐑𝐞𝐪𝐮𝐢𝐫𝐞𝐦𝐞𝐧𝐭𝐬

- **macOS**: 14.0 (Sonoma), 15.0 (Sequoia), or 16.0 (Tahoe).
- **Architecture**: Intel (x64), Apple Silicon (arm64) & Universal (U2B).
- **RAM**: 4 GB minimum, 8 GB recommended for extended sessions with multiple modules open.
- **DAW Compatibility**: Works alongside any DAW.
- **Permissions**: Microphone access (for hardware input monitoring) and Screen Recording (for system audio capture). See the Permissions section below.

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧
1. Download the latest [`VINC3`](https://github.com/KouseiMusic/VINC3/releases/download/VINC3_1.2.0/VINC3.app.macOS.U2B.zip) release.
2. Open the downloaded ZIP file and drag `VINC3.app` to your `Applications` folder.
3. Before launching for the first time, grant the required permissions described in the section below. Doing this before the first launch avoids having to restart the application.
4. Launch `VINC3`. If macOS shows a warning that the app is from an unidentified developer, right-click the app icon and select `Open`, then confirm.
5. When prompted, allow Microphone access.
6. Select your audio source. `MIC` for your microphone or audio interface, `SYSTEM` for whatever is playing through your computer.
7. Click `INITIALIZE` to start the engine. All active modules will begin displaying live data.

---

## 𝐦𝐚𝐜𝐎𝐒 𝐏𝐞𝐫𝐦𝐢𝐬𝐬𝐢𝐨𝐧𝐬

VINC3 requires two permissions to function. macOS will ask for these automatically the first time each feature is used, but granting them in advance through System Settings avoids interruptions during a session.

### 1. Microphone Access

Required when using MIC mode to analyse audio from your microphone, audio interface or any hardware input connected to your Mac.

`System Settings` > `Privacy & Security` > `Microphone` > enable `VINC3`.

### 2. Screen Recording

Required when using SYSTEM mode to capture audio playing through your Mac — from a DAW, a streaming service, a video or any other application. VINC3 does not record or store your screen. macOS uses the Screen Recording permission as the gateway to system audio capture, which is a macOS architecture decision unrelated to visual recording.

`System Settings` > `Privacy & Security` > `Screen Recording` > enable `VINC3`.

_VINC3 does not record video, does not record your screen, does not store audio, and does not transmit anything. These permissions are used exclusively for audio signal routing. No data leaves your machine._

---

## 𝐀𝐮𝐝𝐢𝐨 𝐒𝐨𝐮𝐫𝐜𝐞 𝐌𝐨𝐝𝐞𝐬

**SYSTEM - System Audio Loopback**

Captures whatever audio is currently playing through your Mac's audio output, your DAW's master bus, a streaming application, a video or anything else. This is the primary mode for mastering monitoring, reference listening comparisons and broadcast compliance checking.

On macOS Sonoma and later, system audio capture is handled natively by the operating system via ScreenCaptureKit. No third-party virtual audio device is required. If you are on an older macOS version, you will need a virtual audio driver such as [BlackHole](https://github.com/ExistentialAudio/BlackHole) to route audio to VINC3.

**MIC - Microphone / Hardware Input**

Captures audio directly from your microphone or audio interface. Use this mode when you want to analyse a signal coming into your Mac from an external source, an instrument, a vocalist, a hardware synthesiser or any device plugged into your interface. No additional software is needed.

---

## 𝐌𝐨𝐝𝐮𝐥𝐞𝐬

| Module | What it shows | Display options |
| :--- | :--- | :--- |
| **Spectrogram 3D** | A three-dimensional representation of your audio's frequency content over time. Energy is shown across the full spectrum, with depth representing time history. | Sphere, Wave, Cube, Terminal, Singularity |
| **FFT Meter** | A precise frequency spectrum display spanning 20 Hz to 20 kHz on a logarithmic scale, the same scale your ears use. A live readout marks the loudest frequency and its musical note name. Peak-hold lines show recent transient activity. | Line, Bars, Binary |
| **Level Meters** | Industry-standard loudness metering. Shows peak levels for left and right channels in dBFS, plus Momentary, Short-Term, and Integrated LUFS to ITU-R BS.1770-4 spec. Also displays Crest Factor, the gap between peak and average, which indicates dynamic range. | Horizontal, Vertical |
| **Analog VU Meter** | A faithful recreation of the classic hardware VU meter, with a 300 ms ballistic integration time that reflects perceived loudness similarly to how engineers trained on analogue consoles think about level. | Classic needle, Modern LED bar |
| **Oscilloscope** | Displays the raw audio waveform for both left and right channels simultaneously in real time. Useful for checking waveform symmetry, clipping and the relationship between channels. Zero-crossing trigger ensures a stable, readable display. | - |
| **Stereo Monitor** | A vector scope showing the stereo image as a Lissajous figure. A perfectly mono signal appears as a vertical line. A wide stereo signal fills toward the corners. Out-of-phase audio pulls the image horizontal. Phosphor persistence gives a sense of movement history. | - |
| **Pitch & Stats** | A collection of analytical readouts: the dominant musical pitch currently present in the signal, an estimate of the audio's bit depth, DC offset per channel (a sign of hardware or plugin issues) and stereo phase correlation. | - |
| **Linear Spectrogram** | A scrolling waterfall display that shows frequency energy moving left to right over time. Useful for spotting sustained resonances, tonal buildup, or low-frequency energy that is difficult to see in a standard FFT display. | Theme colours, Classic thermal palette |
| **Phase Correlation** | Shows the phase relationship between the left and right channels on a scale from -1 to +1. A reading near +1 means the channels are in phase and will sum correctly to mono. A reading near -1 means the channels are out of phase and will partially or fully cancel in mono. Also displays Mid and Side levels. | - |

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

| Control | What it does |
| :--- | :--- |
| **MIC / SYSTEM** | Selects the audio source before starting. Cannot be changed while the engine is running. |
| **OPTIONS** | Opens the settings panel for theme selection and module visibility. Can be accessed at any time, including while the engine is running. |
| **INITIALIZE** | Starts the audio engine and activates all visible modules. You will be prompted for permissions on the first use. |
| **STOP** | Stops the audio engine and clears all active readings. Settings and layout are preserved. |
| **SAVE** | Saves the current positions, sizes and visibility of all modules, plus the current theme and source selection, as your default layout. |
| **LOAD** | Restores the most recently saved layout. Useful if you have accidentally moved windows or want to return to a known arrangement. |
| **RESET** | Returns all module windows to their factory default positions and sizes. Does not affect theme or source selection. |
| **Module - Move** | Click and hold anywhere on a module window's surface (away from the resize handle) and drag to reposition it anywhere on screen. |
| **Module - Resize** | Drag the small handle in the bottom-right corner of any module window to resize it. |
| **App window - Resize** | Drag the edges or corners of the main VINC3 window to resize the overall application area. |

---

## 𝐂𝐫𝐞𝐝𝐢𝐭𝐬

- **Sponsor / Benefactor**: Vincent P.

---

_This software is free. If you find it useful, a ⭐️ on GitHub helps others discover it._

---

<p align="center"><code>Kousei</code></p>
<p align="center">2026</p>
