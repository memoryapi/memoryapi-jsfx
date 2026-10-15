# MemoryAPI JSFX Repository

A collection of custom audio DSP effects and JSFX plugins for [Cockos REAPER](https://www.reaper.fm/), packaged for seamless installation and automatic updates via [ReaPack](https://reapack.com/).

---

## 📦 How to Install via ReaPack

1. Ensure **ReaPack** is installed in REAPER (included by default in many setups, or downloadable from [reapack.com](https://reapack.com)).
2. In REAPER's top menu, go to:
   **Extensions** > **ReaPack** > **Import repositories...**
3. Paste your repository URL:
   ```text
   https://raw.githubusercontent.com/memoryapi/memoryapi-jsfx/master/index.xml
   ```
4. Click **OK**. ReaPack will fetch the repository index.
5. In REAPER, go to:
   **Extensions** > **ReaPack** > **Browse packages...**
6. Search for `SpectralCarver` (or any plugin from this repo), right-click the package, select **Install**, and click **Apply**.

---

## 🎛 Included Plugins

### 1. Dynamics / SpectralCarver
**Path**: `Dynamics/SpectralCarver.jsfx`  
**Description**: 32-Band Dynamic Spectral Ducker with Cytomic State Variable Filters (SVF)

* **Key Features**:
  * **32-Band SVF Dynamic Carving**: Frequency-dependent ducking that attenuates only the frequencies active in the sidechain, keeping the mix clean and preserving headroom without traditional broadband pumping.
  * **Routing**: Route your kick, vocals, or sidechain trigger audio to **Channels 3/4** of the track.
  * **Interactive Spectrum Display**: Visual real-time sidechain energy and gain reduction meters with draggable Low-Cut and High-Cut filter boundary curtains.
  * **Redesigned Animated UI**: Modern design with hover halos, animated collapsible drawer, and selectable UI Text Zoom (100%/120%/140%) for HiDPI displays.
  * **Stereo & Mid/Side Processing**: Switchable between L/R stereo ducking and M/S ducking (with dedicated M/S width balance).
  * **Freeze & Audition**: Freeze the current sidechain profile into a static carving EQ curve, or audition the filtered sidechain signal.
  * **Safe DSP Ceiling**: Hard NaN/Inf protection and anti-explosion audio ceilings.

### 2. Dynamics / Opto2A
**Path**: `Dynamics/Opto2A.jsfx`  
**Description**: Optical Tube Compressor

* **Key Features**:
  * **T4 Optical Attenuator Modeling**: Smooth, program-dependent compression curve with characteristic two-stage multi-exponential release memory.
  * **Compress / Limit Modes**: Switchable knee characteristics from gentle musical leveling to peak limiting.
  * **HF Emphasis (R37)**: Dedicated sidechain high-pass emphasis control for frequency-conscious vocal leveling and de-essing.
  * **Classic vs. Fast Photocell Speed**: Switch between vintage relaxed optical response and modern fast response.
  * **Dual Display Metering**: Illuminated vintage VU meter with real-time scrolling Gain Reduction trace graph.
  * **HiDPI Text Scaling**: Quick toggle for 100%, 120%, and 140% UI text zoom.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

### 3. Saturation / OInflator
**Path**: `Saturation/OInflator.jsfx`  
**Description**: Harmonic Waveshaper & Loudness Enhancer

* **Key Features**:
  * **Authentic Transfer Curve Waveshaping**: Specialized polynomial waveshaping algorithm that increases perceived loudness, warmth, and density without destroying transient punch.
  * **Real-time Harmonic Transfer Viewport**: Live visual representation of the transfer curve and operating point with instantaneous boost dB readout.
  * **Phase-Compensated Band Split**: Switchable 3-band split mode with 240 Hz and 2.4 kHz crossovers for independent multiband harmonic excitement.
  * **Clip 0dB Protection**: Prevents signals from exceeding 0 dBFS ceiling when active.
  * **Calibrated Studio Metering**: High-resolution input/output peak and RMS bar meters with hold decay and clip latches.
  * **HiDPI Text Scaling**: Quick toggle for 100%, 120%, and 140% UI text zoom.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

### 4. Saturation / Phoenix
**Path**: `Saturation/Phoenix.jsfx`  
**Description**: Analog Tape Saturator

* **Key Features**:
  * **5 Tape Topologies**: Selectable analog saturation types (Luminescent, Iridescent, Radiant, Luster, and Dark Essence).
  * **3 Brightness Curves**: Switchable high-frequency tape flux responses (Opal for neutral, Gold for warm, Sapphire for bright).
  * **Input & Output Trims with Auto-Gain**: Input Trim (-10 to +10 dB), Process amount (0 to 100%), Output Trim (-6 to +6 dB), and optional automatic gain compensation.
  * **Studio Metering & HiDPI Zoom**: Dual input/output peak/RMS meters with OVER clip indicators and selectable UI text scaling.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

---

## 📂 Repository Structure

ReaPack uses directory structure to organize categories in REAPER's package browser:

```text
.
├── .github/
│   └── workflows/
│       ├── deploy.yml          # Automatically regenerates index.xml on push
│       └── check.yml           # Validates package headers on PRs/pushes
├── .reapack-index.conf         # reapack-index options
├── index.xml                   # ReaPack package index file
├── README.md                   # Repository documentation (shown in ReaPack)
├── Dynamics/                   # ReaPack Category: Dynamics
│   ├── Opto2A.jsfx             # JSFX plugin with ReaPack metadata header
│   └── SpectralCarver.jsfx     # JSFX plugin with ReaPack metadata header
└── Saturation/                 # ReaPack Category: Saturation
    ├── OInflator.jsfx          # JSFX plugin with ReaPack metadata header
    └── Phoenix.jsfx            # JSFX plugin with ReaPack metadata header
```

---

## 🛠 Adding New Plugins & Maintaining with `jj` (Jujutsu)

This repository uses **`jj`** (Jujutsu) for source control.

### Adding a New Plugin
1. Place your new `.jsfx` file inside the appropriate category folder (e.g. `Dynamics/`, `EQ/`, `Utility/`, `Synth/`, etc.).
2. Include the standard ReaPack metadata comment header at the top of the file:
   ```jsfx
   desc:MyPlugin (Effect Description)
   // @description MyPlugin (Short description for ReaPack)
   // @author YourName
   // @version 1.0.0
   // @changelog Initial release
   // @about
   //   # MyPlugin
   //   Detailed description formatted in Markdown.
   // @provides
   //   [effect] MyPlugin.jsfx
   ```
3. Commit your changes using `jj`:
   ```bash
   jj describe -m "feat: add MyPlugin"
   jj bookmark set master -r @
   jj git push --bookmark master
   ```
4. The included GitHub Actions workflow will automatically run `reapack-index`, compile `index.xml`, and update the repository on GitHub.
