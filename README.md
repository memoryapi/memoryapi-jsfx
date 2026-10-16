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

![SpectralCarver](screenshots/spectralcarver.webp)

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

![Opto2A](screenshots/opto2a.webp)

* **Key Features**:
  * **T4 Optical Attenuator Modeling**: Smooth, program-dependent compression curve with characteristic two-stage multi-exponential release memory.
  * **Compress / Limit Modes**: Switchable knee characteristics from gentle musical leveling to peak limiting.
  * **HF Emphasis (R37)**: Dedicated sidechain high-pass emphasis control for frequency-conscious vocal leveling and de-essing.
  * **Classic vs. Fast Photocell Speed**: Switch between vintage relaxed optical response and modern fast response.
  * **Dual Display Metering**: Illuminated vintage VU meter with real-time scrolling Gain Reduction trace graph.
  * **HiDPI Text Scaling**: Quick toggle for 100%, 120%, and 140% UI text zoom.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

### 3. Dynamics / OverTop
**Path**: `Dynamics/OverTop.jsfx`  
**Description**: 3-Band Upward/Downward Multiband Compressor (OTT Style)

![OverTop](screenshots/overtop.webp)

* **Key Features**:
  * **3-Band Upward & Downward Dynamics**: Multiband processing with independent upward compression (lifting quiet details) and downward compression (controlling aggressive peaks).
  * **Interactive Threshold Bars**: Drag horizontally on any band's level bar to offset thresholds with instantaneous visual feedback.
  * **Per-Band Gain & Bypass**: Dedicated bypass toggle and +/-24 dB output gain control for Low (<88 Hz), Mid, and High (>2.5 kHz) bands.
  * **Global Controls**: Depth percentage (dry/wet scaling), Time scaling (1% to 1000%), and Master Input/Output gain trims.
  * **Dedicated Upward % & Downward %**: Balance upward vs downward compression intensity from 0% to 200%.
  * **Modern Vector UI**: Real-time level meters, gain reduction indicators, and scalable HiDPI text zoom (100% - 140%).

### 4. Dynamics / PulseDuck
**Path**: `Dynamics/PulseDuck.jsfx`  
**Description**: Multiband Sidechain & Envelope Shaper

![PulseDuck](screenshots/pulseduck.webp)

* **Key Features**:
  * **16 Instant Curve Presets**: Classic, tight, offbeat, tremolo, and trance gate ducking shapes, plus custom breakpoint node editing with tension curves.
  * **4 Trigger Modes**: Tempo Sync (Repeat), MIDI Note, External Sidechain (Ch 3/4), and Audio Input.
  * **Multiband Crossover**: Full-band, 2-band (Lo/Hi), and 3-band (Lo/Mid/Hi) ducking with 12/24 dB slopes and Band Solo.
  * **Dual Real-Time Scope**: Overlay ducked bass audio (white) directly over incoming sidechain trigger kick (yellow).
  * **One-Click Trace SC**: Automatically detects and fits the ducking curve around your incoming kick transient.
  * **Groove Shaping**: Variable curve slope, timing offset, and phase shift controls (<< < > >>) to lock the pocket.
  * **Scalable UI**: HiDPI text zoom presets (100% - 140%).

### 5. Saturation / OInflator
**Path**: `Saturation/OInflator.jsfx`  
**Description**: Harmonic Waveshaper & Loudness Enhancer

![OInflator](screenshots/oinflator.webp)

* **Key Features**:
  * **Authentic Transfer Curve Waveshaping**: Specialized polynomial waveshaping algorithm that increases perceived loudness, warmth, and density without destroying transient punch.
  * **Real-time Harmonic Transfer Viewport**: Live visual representation of the transfer curve and operating point with instantaneous boost dB readout.
  * **Phase-Compensated Band Split**: Switchable 3-band split mode with 240 Hz and 2.4 kHz crossovers for independent multiband harmonic excitement.
  * **Clip 0dB Protection**: Prevents signals from exceeding 0 dBFS ceiling when active.
  * **Calibrated Studio Metering**: High-resolution input/output peak and RMS bar meters with hold decay and clip latches.
  * **HiDPI Text Scaling**: Quick toggle for 100%, 120%, and 140% UI text zoom.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

### 6. Saturation / Phoenix
**Path**: `Saturation/Phoenix.jsfx`  
**Description**: Analog Tape Saturator

![Phoenix](screenshots/phoenix.webp)

* **Key Features**:
  * **5 Tape Topologies**: Selectable analog saturation types (Luminescent, Iridescent, Radiant, Luster, and Dark Essence).
  * **3 Brightness Curves**: Switchable high-frequency tape flux responses (Opal for neutral, Gold for warm, Sapphire for bright).
  * **Input & Output Trims with Auto-Gain**: Input Trim (-10 to +10 dB), Process amount (0 to 100%), Output Trim (-6 to +6 dB), and optional automatic gain compensation.
  * **Studio Metering & HiDPI Zoom**: Dual input/output peak/RMS meters with OVER clip indicators and selectable UI text scaling.
  * **Credits**: DSP algorithms by [JClones](https://github.com/JClones/JSFXClones), licensed under MIT.

### 7. Creative / ChronoWarp
**Path**: `Creative/ChronoWarp.jsfx`  
**Description**: Creative Half-Time & Varispeed Engine

![ChronoWarp](screenshots/chronowarp.webp)

* **Key Features**:
  * **3 Speed Modes**: 1.5x (-5 semitones triplet), 2x Half-Time (-1 octave half-speed), and 4x Quarter-Time (-2 octaves quad-slow).
  * **Continuous Ring-Buffer DSP**: 4-point Hermite cubic interpolation over an ~87-second continuous ring buffer for artifact-free, clickless time transformation.
  * **Synchronized Loop Lengths**: Quantized to project tempo from 1/16 beat up to 8 full bars.
  * **Bipolar Smooth Windowing**: Smooth contour shape transitions between transient-preserving percussion/FX mode and seamless sustain/swell mode.
  * **Dual Bandpass Crossover**: Draggable low-cut and high-cut frequency filters with dedicated Band Solo auditioning.
  * **Upper-Octave Shimmer & Reverse**: Layer an octave-up granular sheen or flip slice playback direction.
  * **Tempo-Synced Fade In/Out**: Cleanly eliminates edge transients or creates musical fade swells.
  * **Interactive Modern UI**: Live waveform visualizer with position playhead indicator and scalable HiDPI text zoom (100% - 140%).

### 8. Creative / VintageFlux
**Path**: `Creative/VintageFlux.jsfx`  
**Description**: 6-Module Vintage Multi-FX & Lo-Fi Color Workstation

![VintageFlux](screenshots/vintageflux.webp)

* **Key Features**:
  * **6 Dedicated Vintage FX Modules**:
    * **Noise**: Vinyl, Cassette, VHS, and White noise with envelope following and ducking.
    * **Wobble**: Pitch wow & flutter with rate and stereo drift.
    * **Distort**: Tube, Tape, Crunch, and Wavefold saturation with focused frequency crossover.
    * **Digital**: Sample rate downsampling and bitcrushing with smoothing and pass/cut modes.
    * **Space**: Ambient algorithmic reverb with pre-delay, decay, and damping controls.
    * **Magnetic**: Vintage tape wear, dropouts, and flutter imperfections.
  * **Global Magnitude Slider**: Scales all module intensities and master character simultaneously.
  * **Dedicated Flux Controls**: Organic, non-repeating random analog drift on every module.
  * **Master Tone & Filters**: 12/24 dB Low/High cuts, Tilt/Smile tone EQ, M/S width, and output trim.
  * **Scalable UI**: HiDPI text zoom presets (100% - 140%).

### 9. Delay / EchoForge
**Path**: `Delay/EchoForge.jsfx`  
**Description**: Analog Tape, Lo-Fi & Diffused Delay Workstation

![EchoForge](screenshots/echoforge.webp)

* **Key Features**:
  * **4 Delay Models**: Mono, Stereo, Ping-Pong, and Off (standalone Lo-Fi / Modulation / Reverb FX processor).
  * **Tempo Sync & Free Milliseconds**: Tempo-quantized 16th steps (1 to 16) or free-running delay times from 1 ms to 1000 ms.
  * **Tape Pitch Glide vs Keep Pitch**: Switch between classic tape-style Doppler pitch slewing or clickless crossfaded time changes.
  * **Self-Oscillation & Analog Distortion**: Feedback up to 150% with tape-modeled saturation and soft limiter protection.
  * **Resonant Multi-Mode Filter**: Low-Pass, High-Pass, and Band-Pass filter in the feedback path with adjustable resonance.
  * **4-Stage Stereo All-Pass Diffuser**: Smears delay repeats into expansive, lush ambient reverb washes.
  * **Lo-Fi Degradation Engine**: Continuous sample rate downsampling (down to 1 kHz) and bitcrushing (down to 2 bits).
  * **Multi-Destination Modulation**: Dedicated LFO modulating delay time and filter cutoff for tape wow & flutter or sweeping filter dub effects.
  * **Tone Tilt, Spread & Mix**: Output tone shaping, stereo width spread, and independent dry/wet controls.
  * **Interactive UI**: Live animated waveform and echo tap visualizer with scalable HiDPI text zoom (100% - 140%).

### 10. EQ / ConsoleQ
**Path**: `EQ/ConsoleQ.jsfx`  
**Description**: Hybrid Console EQ, Air Strip & FFT Spectrum Analyzer

![ConsoleQ](screenshots/consoleq.webp)

* **Key Features**:
  * **4-Band Console EQ**: Low, Low-Mid, High-Mid, and High frequency bands with switchable Bell and Shelf curves for LF/HF.
  * **Console Cut Filters**: 18 dB/oct resonant High-Pass (20 - 500 Hz) and 12 dB/oct Low-Pass (3k - 22 kHz) filters.
  * **High-Headroom Air Band & Sub Weight**: Dedicated Air Band shelf with selectable frequencies (2.5k, 5k, 10k, 20k, 40 kHz) up to +20 dB boost, plus a Sub 10Hz resonance weight bell.
  * **Dual Console Topologies**: Switchable E-Series (Constant Q) and G-Series (Proportional Q) response curves.
  * **Analog Character Coloring**: Clean, Subtle, and Warm analog harmonic drive modes.
  * **Interactive Graph Nodes**: Drag band frequency and gain handles directly on the live EQ response curve.
  * **Real-time 2048-Point FFT Analyzer**: High-resolution spectrum visualizer switchable between Post-EQ, Pre-EQ, and Off.
  * **Momentary Band Solo**: Hold the [S] audition button on any frequency band column to isolate its processing range.
  * **Output Section**: Mid/Side stereo width (0% - 200%), panning, auto-gain compensation, and latched peak LED.
  * **Scalable UI**: HiDPI text zoom presets (100% - 140%).

### 11. EQ / PocketQ
**Path**: `EQ/PocketQ.jsfx`  
**Description**: Compact Console & Air Channel Strip EQ

![PocketQ](screenshots/pocketq.webp)

* **Key Features**:
  * **Fixed Musical Frequency Bands**: Tuned classic frequencies: Sub (10 Hz), 40 Hz, 160 Hz, 650 Hz, and 2.5 kHz (switchable Shelf/Bell).
  * **Air Band**: Selectable ultra-high frequencies (2.5k, 5k, 10k, 20k, 40 kHz) with up to +20 dB boost.
  * **Console Cut Filters**: 18 dB/oct HPF (20 - 500 Hz) and 12 dB/oct LPF (3k - 22 kHz).
  * **E-Series & G-Series Modes**: Switch between tight constant Q and smooth proportional Q response.
  * **Console Drive**: Clean vs. Warm analog harmonic drive.
  * **Auto Gain & Phase Invert**: Output level compensation and quick polarity toggle.
  * **Ultra-Lightweight CPU Footprint**: Zero FFT overhead, designed for tracking and heavy multi-track mixing sessions.
  * **Scalable UI**: HiDPI text zoom presets (100% - 140%).

### 12. EQ / ReEQ Studio
**Path**: `EQ/ReEQ_Studio.jsfx`  
**Description**: Polished 16-Band Parametric Equalizer

![ReEQ Studio](screenshots/reeq_studio.webp)

* **Key Features**:
  * **16 Fully Parametric Bands**: Individual solo, gain, Q, frequency, and slope controls across all 16 bands.
  * **Extended Filter Topologies**: Peak, Low/High Cut (including Butterworth and Analog models), Low/High Shelf, Notch, Band Pass, Tilt Shelf, Pultec Low Shelf, and All Pass.
  * **Stereo, Mid/Side & Left/Right**: Independent processing modes per band.
  * **Real-Time FFT Analyzer**: High-resolution spectrum visualizer with Pre-EQ, Post-EQ, Mid/Side, and L/R visualization.
  * **HQ Oversampling**: High-Quality mode with linear-phase FIR half-band filtering.
  * **Interactive GUI**: Marquee multi-node selection, piano roll scale display, and smart context-aware band creation.
  * **Credits**: Original DSP & core architecture by [Justin Johnson (ReJJ)](https://github.com/Justin-Johnson/ReEQ).

### 13. Reverb / AetherVerb
**Path**: `Reverb/AetherVerb.jsfx`  
**Description**: 8-Mode Algorithmic, Shimmer & FDN Reverb

![AetherVerb](screenshots/aetherverb.webp)

* **Key Features**:
  * **8 Reverb Topologies**: Plate 140, Concert Hall, Cloud, Shimmer, Bloom, Chorale, Non-Linear, and SuperFDN (8-delay Feedback Delay Network).
  * **Multi-Voice Pitch Shimmer**: Two independent shimmer voices with octave and musical interval transpositions (-1 Oct, -5th, Detune, +5th, +1 Oct, +2 Oct).
  * **Formant Chorale Resonators**: Morphing vowel filtering (AH, OH, OO) for vocal resonances and synthetic choir pads.
  * **Dynamic Auto-Decay**: Built-in envelope follower ducks the reverb tail during active performance to preserve clarity and prevent muddy buildups.
  * **Analog Preamp & Converter Modeling**: Clean, Tube V54, and Solid State 162 preamps paired with Modern HiFi, 70s 12-Bit, and 80s Dark digital converter flavors.
  * **Infinite & Freeze**: Instant hold modes for endless ambient sustain drones and atmospheric backdrops.
  * **Integrated Tone & Post-EQ**: Pre Low/High Cut filters plus an interactive 2-band parametric post-EQ with draggable node handles.
  * **Modern Vector Interface**: HiDPI UI text zoom presets (100% - 150%) and collapsible tweak drawer.

### 14. Dynamics / VelvetClip
**Path**: `Dynamics/VelvetClip.jsfx`  
**Description**: Transparent Threshold-Linear Soft Clipper

![VelvetClip](screenshots/velvetclip.webp)

* **Key Features**:
  * **100% Bit-Identical Pass-Through**: Absolutely linear (y = x) below threshold with 0% harmonic distortion until peaks cross into the clipping region.
  * **Interactive Transfer Graph**: Drag vertically directly on the response curve to offset clipping threshold with live numerical feedback.
  * **3 Clipper Topologies**:
    * **Fruity Soft**: Asymptotic rational curve that smoothly limits transients without folding or harsh odd-harmonic distortion.
    * **Cubic Knee**: Punchy polynomial knee that transitions smoothly into a rigid 0 dBFS brickwall ceiling.
    * **Bass Shaper**: Logarithmic knee curve specifically tuned to saturate high peaks while preserving low-end definition.
  * **808 Sub Safe**: Internal crossover filter that isolates low frequencies (<95 Hz) around the clipper so sub bass notes never buzz or lose energy.
  * **HQ 2x Oversampling**: Zero-latency linear phase half-band filtering to suppress digital aliasing on aggressive transients.
  * **Dual History Scope**: Real-time scrolling visualizer displaying output waveform alongside shaved peak reductions.
  * **Precision Metering**: Calibrated stereo output level bar and shaved dB clip amount indicator.
  * **Scalable UI**: HiDPI text zoom presets (100% - 150%).

### 15. Synth / AetherSynth
**Path**: `Synth/AetherSynth.jsfx`  
**Description**: 8-Voice Polyphonic Unison & ZDF Analog Synthesizer

![AetherSynth](screenshots/aethersynth.webp)

* **Key Features**:
  * **8-Voice Polyphony & Modes**: Polyphonic (8-voice), Mono, and Legato voice allocation with portamento glide and organic analog slop/drift.
  * **Dual Multi-Wave Oscillators**:
    * **Oscillator 1 (Unison Stack)**: Saw, Pulse, Triangle, Sine, and TriWrap waveforms with stepped octave selector (-2 to +2), 1 to 7 unison voices, detune, and stereo spread.
    * **Oscillator 2 & Sub/Noise**: Hard sync, linear FM, ring modulation, pulse width modulation, dedicated sub-oscillator (-1 / -2 octaves), and analog white noise generator.
  * **3 Zero-Delay Feedback (ZDF) Filter Topologies**:
    * **Ladder 24dB**: Rich Moog-style transistor ladder with non-linear saturation drive.
    * **Bite Screamer**: Aggressive MS-20 style resonant filter with screaming feedback.
    * **Uhbie Morph**: Continuous 12dB multi-mode filter smoothly morphing between Low-Pass, Band-Pass, and High-Pass.
  * **Interactive Filter Display**: Real-time frequency response visualization with live cutoff and resonance plotting.
  * **Dual Modulation Envelopes**: Amp ADSR and Mod ADSR with live animated envelope traces.
  * **Dual LFOs**: Sine, Triangle, Saw, Square, and Random S&H targeting pitch vibrato, PWM, and filter cutoff.
  * **Master FX Section**: Built-in analog distortion, stereo chorus, tempo/free ping-pong delay, and algorithmic hall reverb.
  * **Built-In Factory Soundbank**: 8 production-ready presets (Anthem Supersaw, Diva Ladder Bass, Acid 303, Jupiter Pad, Pluck Poly Arp, Neuro Sub Reese, Vintage Keys).
  * **Playable Virtual Keyboard**: Interactive 4-octave piano roll keyboard with active voice visualization.
  * **Scalable UI**: HiDPI UI zoom presets (100% - 150%).

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
├── screenshots/                # Plugin screenshot previews (WebP)
├── Creative/                   # ReaPack Category: Creative
│   ├── ChronoWarp.jsfx         # JSFX plugin with ReaPack metadata header
│   └── VintageFlux.jsfx        # JSFX plugin with ReaPack metadata header
├── Delay/                      # ReaPack Category: Delay
│   └── EchoForge.jsfx          # JSFX plugin with ReaPack metadata header
├── Dynamics/                   # ReaPack Category: Dynamics
│   ├── Opto2A.jsfx             # JSFX plugin with ReaPack metadata header
│   ├── OverTop.jsfx            # JSFX plugin with ReaPack metadata header
│   ├── PulseDuck.jsfx          # JSFX plugin with ReaPack metadata header
│   ├── SpectralCarver.jsfx     # JSFX plugin with ReaPack metadata header
│   └── VelvetClip.jsfx         # JSFX plugin with ReaPack metadata header
├── EQ/                         # ReaPack Category: EQ
│   ├── Dependencies/           # ReEQ include files
│   │   ├── firhalfband.jsfx-inc
│   │   ├── spectrum.jsfx-inc
│   │   └── svf_filter.jsfx-inc
│   ├── ConsoleQ.jsfx           # JSFX plugin with ReaPack metadata header
│   ├── PocketQ.jsfx            # JSFX plugin with ReaPack metadata header
│   └── ReEQ_Studio.jsfx        # JSFX plugin with ReaPack metadata header
├── Reverb/                     # ReaPack Category: Reverb
│   └── AetherVerb.jsfx         # JSFX plugin with ReaPack metadata header
├── Saturation/                 # ReaPack Category: Saturation
│   ├── OInflator.jsfx          # JSFX plugin with ReaPack metadata header
│   └── Phoenix.jsfx            # JSFX plugin with ReaPack metadata header
└── Synth/                      # ReaPack Category: Synth
    └── AetherSynth.jsfx        # JSFX plugin with ReaPack metadata header
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
