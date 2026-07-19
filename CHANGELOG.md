# 𝐕𝐈𝐍𝐂𝟑 - 𝐂𝐡𝐚𝐧𝐠𝐞𝐥𝐨𝐠

## 𝟐.𝟎.𝟎 (𝟐𝟏.𝟎𝟖.𝟐𝟎𝟐𝟔)

### 𝐍𝐞𝐰 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬

- **New Modules**: Added 7 new modules including Mid/Side FFT, Dynamic Range Meter, Loudness History, Compare Spectrogram, Stereo Correlation, THD Analyzer and Transient Meter.

- **Visual Themes**: Added 4 new aesthetic themes: Blueprint, Oscilloscope, VHS and Thermal.

- **3D Spectrogram**: Added 5 new visualization modes: Polygon, Smoke, Matter, Reaction and Neural Mesh.

### 𝐌𝐞𝐭𝐞𝐫𝐢𝐧𝐠 & 𝐀𝐜𝐜𝐮𝐫𝐚𝐜𝐲

- Fixed the Pitch & Stats panel showing a completely wrong peak level reading. The meter was converting the level value twice by mistake, producing numbers that bore no relation to the actual signal. For example, a signal at -20 dB would appear as roughly +26 dB. Readings are now accurate.

- Fixed Integrated LUFS reading lower than the true value of the signal. The measurement is designed to ignore silence and very quiet passages so they do not drag the average down, but the threshold for what counts as "too quiet to include" was set far too low. Quiet passages that should have been excluded were being factored in. The threshold now matches the broadcast loudness standard exactly (ITU-R BS.1770-4).

- Fixed LUFS values drifting away from their true readings after several hours of continuous use. Computers accumulate tiny rounding errors when doing repeated arithmetic and the LUFS running average was never corrected for this. Over a long session the drift became noticeable. The accumulator now resets its total periodically to keep readings accurate regardless of session length.

### 𝐑𝐞𝐥𝐢𝐚𝐛𝐢𝐥𝐢𝐭𝐲

- Fixed the Neural Mesh visualization showing a flat black background in the oscilloscope theme instead of the dark-green CRT backdrop used everywhere else in that theme. Its canvas was fully opaque and always painted solid black, which blocked the theme's background from showing through - Crystal, Matter, and Smoke all render onto a transparent canvas with a translucent background fill for this exact reason, so the dark-green backdrop shows through underneath. Neural Mesh now does the same for the oscilloscope theme specifically.

- Fixed System audio mode silencing the Mac's actual audio output for the entire capture session. The main process was requesting `audio: 'loopbackWithMute'` from ScreenCaptureKit, which — despite the name reading like an echo-cancellation setting — mutes the system's real output, not just the captured copy. Switched to `audio: 'loopback'`, which captures the same audio without muting anything.

- Fixed pressing INITIALIZE rapidly or twice in quick succession still being able to start the audio engine twice at once under certain timing (the previous guard checked state that only updates after the microphone/screen permission prompt resolves, leaving a window where a second click could slip through before the first had finished setting up). The guard is now synchronous and closes that window completely; the INITIALIZE button also now disables itself and reads "INITIALIZING…" while a request is in flight.

- Fixed the THD Analyzer's fundamental-frequency estimate permanently locking to "NaN" for the rest of the session after a single flat, silent, or clipped (0 dBFS) input frame. The parabolic peak-interpolation math divided by a value that could legitimately be zero; it's now guarded and falls back to the un-interpolated bin.

- Fixed a legitimate 0 dB reading (signal at full scale) being mis-displayed as near-silence in the THD Analyzer and FFT Sniper's hover readout, caused by treating `0` as a missing value.

- Fixed STOP not releasing the Mid/Side analyser nodes, leaving them dangling on stale references until the next START overwrote them.

- Fixed every "LOAD REF WAV" in Compare Spectrogram opening a new real-time AudioContext that was never closed, leaking one per file loaded in a session.

- Fixed the Crystal, Matter, and Smoke Spectrogram (WebGL) visualizations leaking their shaders, geometry buffers and for Smoke, render-target textures/framebuffers every time the effect re-ran (switching themes, starting/stopping capture, or changing 3D mode). Smoke in particular deleted none of its GPU resources on cleanup. All three now also stop cleanly if the GPU context is lost instead of continuing to render into a dead context.

### 𝐌𝐞𝐭𝐞𝐫𝐢𝐧𝐠 & 𝐀𝐜𝐜𝐮𝐫𝐚𝐜𝐲

- Fixed the Pitch & Stats panel showing a completely wrong peak level reading. The meter was converting the level value twice by mistake, producing numbers that bore no relation to the actual signal. For example, a signal at -20 dB would appear as roughly +26 dB. Readings are now accurate.

- Fixed Integrated LUFS reading lower than the true value of the signal. The measurement is designed to ignore silence and very quiet passages so they do not drag the average down, but the threshold for what counts as "too quiet to include" was set far too low. Quiet passages that should have been excluded were being factored in. The threshold now matches the broadcast loudness standard exactly (ITU-R BS.1770-4).

- Fixed LUFS values drifting away from their true readings after several hours of continuous use. Computers accumulate tiny rounding errors when doing repeated arithmetic and the LUFS running average was never corrected for this. Over a long session the drift became noticeable. The accumulator now resets its total periodically to keep readings accurate regardless of session length.

### 𝐒𝐲𝐬𝐭𝐞𝐦 𝐀𝐮𝐝𝐢𝐨

- Fixed SYSTEM mode silently producing no signal on macOS even after Screen Recording permission had been granted. An internal setting that only applies on Windows was mistakenly being applied on macOS as well. macOS does not recognise it and when it encountered it; discarded the audio track without any error message. Removing it restores reliable system audio capture on all supported macOS versions.

### 𝐈𝐧𝐭𝐞𝐫𝐟𝐚𝐜𝐞

- Fixed Level Meters stuttering and animating unevenly. The peak-hold indicator was causing the display to restart its update loop dozens of times per second every time a new peak was detected. Each restart introduced a brief gap visible as a stutter. The update loop now runs continuously without interruption.

- Fixed the Linear Spectrogram bleeding the previous theme's colours through the display for up to seventeen seconds after switching themes. The scrolling history image was never cleared when a theme change was applied, so the old colours remained visible underneath the new ones until the history scrolled past. The history is now wiped immediately on theme change.

- Fixed the green fullscreen button in the title bar being broken or permanently greyed out on macOS Sequoia and Tahoe. Two internal window settings were contradicting each other, which caused macOS to disable the button. The settings are now consistent and the button works as expected.

### 𝐒𝐞𝐭𝐭𝐢𝐧𝐠𝐬

- Fixed theme selection and audio source not being remembered after closing and reopening the application. Two separate parts of the application were using different internal names when saving and reading these preferences, so they never matched on the next launch. Every session started on the default teal theme and System source regardless of what had been set. The names are now unified, and preferences are saved the moment they are changed rather than only when Save Layout is clicked.

### 𝐑𝐞𝐥𝐢𝐚𝐛𝐢𝐥𝐢𝐭𝐲

- Fixed pressing INITIALIZE rapidly or twice in quick succession causing the audio engine to start twice at the same time, consuming extra resources and potentially causing conflicts. The engine now ignores any start request while it is already running.

- Fixed the audio engine maintaining an unnecessary connection to the system audio output while processing. It produced no sound, but the connection could cause unexpected behaviour on certain audio interfaces or virtual audio drivers. It has been replaced with a fully silenced internal path.

- Fixed module windows saving the wrong size when a layout was saved immediately after resizing. The layout system was recording the size one step behind what was actually displayed on screen. Saved sizes now match what is visible in real time.

### 𝐒𝐞𝐜𝐮𝐫𝐢𝐭𝐲

- Added `NSAudioCaptureUsageDescription` to Info.plist. Recent Chromium versions silently return a dead, trackless audio stream from system-audio capture on macOS Sonoma+ if this key is absent no error is raised, so this could present as "system audio just doesn't work" with no clue why.

- Denied window.open()/new-window and cross-origin navigation attempts from the main window (defense in depth; nothing currently triggers this, but a compromised renderer could otherwise pivot into loading remote content).

- Added a Content-Security-Policy to the packaged app (production builds only, so it can't interfere with the dev server's HMR websocket).

- Removed an unused IPC handler that returned thumbnail screenshots and titles of every open window on the system to the renderer; nothing in the app called it.

- `sandbox: true` is now set explicitly on the renderer rather than relying on Electron's default.

### 𝐔𝐈 & 𝐕𝐢𝐬𝐮𝐚𝐥 𝐅𝐢𝐱𝐞𝐬

- Singularity: Reversed the rotation direction of the dust particle animation.

- Pitch & Stats: Reduced the font size of text values and legends by 20% to improve visual hierarchy.

- FFT Hover Details: Fixed an issue where the frequency/dB hover indicator would get cropped at the top and right edges of the FFT module window.

- Pitch & Stats: Repositioned Bit Depth tracking display to avoid layout collision and improve the visual hierarchy.

### 𝐏𝐞𝐫𝐟𝐨𝐫𝐦𝐚𝐧𝐜𝐞 & 𝐑𝐞𝐧𝐝𝐞𝐫𝐢𝐧𝐠 𝐎𝐩𝐭𝐢𝐦𝐢𝐳𝐚𝐭𝐢𝐨𝐧𝐬

- Engine Acceleration: Added GPU acceleration flags (zero-copy, hardware rasterization) to the Electron main process for smoother UI rendering.

- High-DPI Display Fixes: Capped the maximum physical device pixel ratio scaling inside Canvas modules to 2.0x to eliminate performance stuttering on 4K+ displays (Retina/ProDisplay XDR).

- FFT Rendering: Replaced expensive shadowBlur API calls with optimized multi-stroke compositing, significantly reducing CPU/GPU overhead.

- Spectrogram Engine: Migrated to hardware-accelerated canvas drawImage operation instead of CPU-bound getImageData for shifting the display buffers.

### 𝐒𝐞𝐭𝐭𝐢𝐧𝐠𝐬

- Fixed theme selection and audio source not being remembered after closing and reopening the application. Two separate parts of the application were using different internal names when saving and reading these preferences, so they never matched on the next launch. Every session started on the default teal theme and System source regardless of what had been set. The names are now unified and preferences are saved the moment they are changed rather than only when Save Layout is clicked.

---

## 𝟏.𝟏.𝟎 (𝟎𝟓-𝟎𝟔-𝟐𝟎𝟐𝟔)

### 𝐈𝐧𝐭𝐞𝐫𝐟𝐚𝐜𝐞

- 3 New visual themes: White, Blue & Windows 98.

- Two New 3D Spectrograms: Terminal & Binary.

- 2 New Modules:
  - Phase Correlation meter with Mid and Side level readout.
  - Pitch & Stats panel showing the dominant musical note, an estimate of the audio bit depth, DC offset per channel and stereo phase correlation.

### 𝐋𝐚𝐲𝐨𝐮𝐭 & 𝐖𝐨𝐫𝐤𝐬𝐩𝐚𝐜𝐞

- Updated the default factory layout. The out-of-the-box positions and sizes of all module windows have been revised to make better use of the screen from the first launch, without needing to rearrange anything manually.

### 𝐏𝐞𝐫𝐟𝐨𝐫𝐦𝐚𝐧𝐜𝐞 & 𝐃𝐢𝐬𝐩𝐥𝐚𝐲

- Fixed stuttering on Retina and Pro Display XDR screens. On 4K and higher-resolution displays, canvas modules were rendering at the full physical pixel density of the screen, which could cause choppy animation on high-refresh-rate monitors. Rendering is now capped at 2x scaling, which looks identical at normal viewing distances but is significantly lighter on the GPU.

---

## 𝟏.𝟎.𝟎 (𝟐𝟐-𝟎𝟓-𝟐𝟎𝟐𝟔)

### 𝐋𝐚𝐲𝐨𝐮𝐭 & 𝐖𝐨𝐫𝐤𝐬𝐩𝐚𝐜𝐞

- Added layout saving and loading. You can now save which modules are open, where they are positioned, and how large they are, directly from the toolbar using the Save button. Load restores exactly what was saved. Reset returns everything to the factory arrangement.

### 𝐈𝐧𝐭𝐞𝐫𝐟𝐚𝐜𝐞

- Fixed the FFT Meter tooltip; the small overlay showing frequency and level when hovering over the display, getting cut off at the top and right edges of the module window. It now shifts its position to stay fully visible wherever the cursor is.

- Fixed the Bit Depth readout in the Pitch & Stats panel overlapping with other information. It has been moved to its own clearly separated position in the layout.

### 𝐏𝐞𝐫𝐟𝐨𝐫𝐦𝐚𝐧𝐜𝐞 & 𝐃𝐢𝐬𝐩𝐥𝐚𝐲

- Enabled GPU acceleration at application startup, allowing the graphics hardware to take on more of the rendering work and keep the interface responsive during sessions with multiple modules open.

- Reduced CPU and GPU load on the FFT Meter. The glow effect on the spectrum line was previously produced by a blur operation that is costly when applied to a large path redrawn sixty times per second. It has been replaced with a layered drawing approach that produces the same visual result at a fraction of the processing cost.

- Switched the Linear Spectrogram to hardware-accelerated scrolling. Shifting the history image one step on every frame was previously done by reading and rewriting pixel data in software. It now uses a GPU-accelerated image copy operation, moving that work off the CPU entirely.

---

## 𝟎.𝟗.𝟗 (𝟐𝟏-𝟎𝟑-𝟐𝟎𝟐𝟔)

- 3D Spectrogram with 3 visualisation modes: Sphere, Wave & Cube.

- FFT Meter covering the full audible range (20 Hz to 20 kHz) on a logarithmic scale with peak hold lines and a live readout of the loudest frequency and its musical note name.

- Level Meters showing peak levels for left and right channels, Momentary, Short-Term, and Integrated LUFS to broadcast standard and Crest Factor. Available in horizontal and vertical layouts.

- Analog VU Meter with a Classic needle mode and a Modern LED bar mode, with a 300 ms ballistic integration time.

- Oscilloscope showing the live waveform for both left and right channels with a zero-crossing trigger for a stable, readable display.

- Stereo Monitor vector scope for visualising stereo width and left/right balance as a Lissajous figure with phosphor persistence.

- Linear Spectrogram scrolling waterfall for tracking frequency energy over time, useful for spotting sustained resonances and tonal buildup.

- 4 visual themes: Teal, Pink, Purple & Green.

- Microphone and system audio input modes with automatic fallback if the primary capture method is unavailable.

- Available as a native macOS application for Intel (x64), Apple Silicon (arm64) and Universal Binary. Supports macOS Sonoma, Sequoia and Tahoe.
