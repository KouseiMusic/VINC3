<p align="center"><img width="190" height="193" alt="vinc3banner" src="https://github.com/user-attachments/assets/ba115c1a-ce26-4999-8672-56a88455eabb" /></p>

_<p align="center">Audio Analysis & DSP Metering. Frequency Visualization & Audio Monitoring._</p>

---

![Version](https://img.shields.io/badge/Version-1.1.0-brightgreen?style=flat-square)
![macOS Support](https://img.shields.io/badge/macOS-Sonoma%20%7C%20Sequoia%20%7C%20Tahoe-000000?style=flat-square&logo=apple&logoColor=white)
![Architecture](https://img.shields.io/badge/Architecture-Intel%20%7C%20Arm64%20%7C%20Universal-black?labelColor=606060&style=flat-square&logo=apple&logoColor=white)
![Format](https://img.shields.io/badge/Format-Standalone-00CED1?style=flat-square)</p>

---

<img width="1439" height="868" alt="vinc3preview" src="https://github.com/user-attachments/assets/8f94e5c6-8586-49af-a916-3a74b9249dbc" />

---

## 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **3D Engine**: Three-dimensional audio spectrogram engine.
- **Metering Modules**: High Precision monitoring suite.
- **Standalone**: Runs as a native application on macOS (Sonoma, Sequoia, Tahoe) without a browser.
- **Zero Dependencies**: Fully offline capable. No internet connection required.
- **Minimalist UI**: Dark-themed, high-contrast interface optimized for low-light studio environments. 5 themes available.

---

## 𝐒𝐲𝐬𝐭𝐞𝐦 𝐑𝐞𝐪𝐮𝐢𝐫𝐞𝐦𝐞𝐧𝐭𝐬

- **macOS**: 14.0 (Sonoma), 15.0 (Sequoia), or 16.0 (Tahoe).
- **Architecture**: Intel, Arm64 (Silicon) & U2B (Universal).
- **DAWs**: Ableton 11+, Ableton 12+, Logic Pro & Reason with [BlackHole](https://github.com/ExistentialAudio/BlackHole) driver.
- **Permissions**: Requires Microphone (for hardware input) and Screen Recording (for system audio loopback).

---

## 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧

1. Download the latest [`VINC3`](https://github.com/KouseiMusic/VINC3/releases/download/VINC3_1.1.0/VINC3.app.macOS.U2B.zip)
2. Extract & Drag `VINC3` to your `Applications` folder.
- _Note : Follow the macOS Permissions tutorial below for first-time setup, before use and before applying step 3._
3. Launch `VINC3` and `Allow` Microphone capture once the tab appears.
4. Select your audio source `MIC` or `SYSTEM`
5. Click on `INITIALIZE`. It will start the engine.

---

## 𝐦𝐚𝐜𝐎𝐒 𝐏𝐞𝐫𝐦𝐢𝐬𝐬𝐢𝐨𝐧𝐬

To function as a standalone analyzer. `VINC3` requires specific system access. Make sure to fill all these requirements before starting using :

### 𝟏. 𝐌𝐢𝐜𝐫𝐨𝐩𝐡𝐨𝐧𝐞 𝐀𝐜𝐜𝐞𝐬𝐬
Required to analyze audio from your interface or built-in mic.
- `System Settings` > `Privacy & Security` > `Microphone` > Add `VINC3`.

### 𝟐. 𝐒𝐜𝐫𝐞𝐞𝐧 𝐑𝐞𝐜𝐨𝐫𝐝𝐢𝐧𝐠
Required for **System Audio Loopback** (capturing audio from other softwares).
- `System Settings` > `Privacy & Security` > `Screen Recording` > Add `VINC3`.

- _Reminder: `VINC3` does not record a single pixel. It doesn't record audio. It doesn't record video. It doesn't require Internet. These permissions are macOS requirements for internal audio routing._

---

## 𝐌𝐨𝐝𝐮𝐥𝐞𝐬
| Module | Description | Features |
| :--- | :--- | :--- |
| **Spectrogram** | 3D spectral energy visualization. | **Sphere**, **Wave**, **Cube** & **Terminal** modes. |
| **FFT Meter** | Surgical frequency monitoring via HD FFT. | Peak tracking, auto-labeling & Logarithmic scaling (20Hz-20kHz). |
| **Level Meters** | Industry-standard loudness compliance. | Real-time M/S/I LUFS, dBFS tracking & Crest Factor alerts. |
| **Analog VU** | Classic hardware-inspired ballistics. | 300ms integration time & Hot Zone saturation indicators. |
| **Oscilloscope** | Real-time linear waveform visualization. | Dual-channel (L/R) stereo image monitoring. |
| **Stereo Monitor** | Phase and width analysis. | Vector scope and real-time panning display. |
| **Pitch & Stats** | Real-time audio statistics. | Pitch detection, Chroma wheel display & bit-depth estimation. |
| **Linear Spec** | Scrolling frequency energy history. | Logarithmic timeline for detecting long-term resonances. |
| **Phase Correlation**| Phase alignment analysis. | Real-time correlation tracking (+1 to -1) & mono compatibility check. |

---

## 𝐂𝐨𝐧𝐭𝐫𝐨𝐥𝐬

| Control | Description |
| :--- | :--- |
| **MIC** | Set audio source to your Microphone. |
| **SYSTEM** | Set audio source to your System audio. |
| **INITIALIZE** | Boot the engine using the selected audio source. |
| **STOP** | Terminate the engine and all active processing. |
| **SAVE** | Save current active modules, their sizes and positions as default layout. |
| **LOAD** | Load previously saved template layout. |
| **RESET** | Revert all modules to their default factory positions. |
| **Software Scaling** | Select the window borders to resize or move the `VINC3` window. |
| **Module Scaling** | Drag the bottom-right corner to resize; hold `Left Click` to move. |

---

## 𝐂𝐫𝐞𝐝𝐢𝐭𝐬

- **Sponsor / Benefactor**: Vincent P.

---

_This software is free. Don't forget to give it a ⭐ on Github if you liked the project._

---

<p align="center"><code>𝒦𝑜𝓊𝓈𝑒𝒾</code></p>
<p align="center">2026</code></p>
