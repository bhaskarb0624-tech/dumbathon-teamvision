# MADLOG - Sound Effects Documentation

## 🔊 Audio System Overview

The MADLOG horror journal features an extensive audio system with **LOUD** and **WEIRD** sounds that intensify based on the madness stage. All sounds are generated using the Web Audio API for maximum impact.

## 📚 Sound Libraries

### 1. **audio.ts** - Core Sounds
Basic horror atmosphere sounds used throughout the experience.

#### `playStaticNoise(duration, volume)`
- **Type**: Radio static / white noise
- **Default Volume**: 0.5 (LOUD)
- **Duration**: 1.5 seconds
- **Effect**: Stereo chaos with aggressive static
- **Usage**: Popup spawns, general chaos

#### `playDistortedBeep(freq, duration)`
- **Type**: Distorted electronic beep
- **Default Volume**: 0.4 (LOUD)
- **Frequency**: Variable (300-800 Hz)
- **Effect**: Heavy distortion with frequency drop
- **Usage**: Popup closes, confirmations

#### `playWhisper()`
- **Type**: Creepy whisper effect
- **Volume**: 0.3 (MODERATE)
- **Duration**: 0.8 seconds
- **Effect**: Stereo whisper with high-pass filter
- **Usage**: Keyword detection

#### `playScreech()`
- **Type**: High-pitched screech
- **Volume**: 0.6 (VERY LOUD)
- **Frequency**: 2000-8000 Hz sweep
- **Effect**: Dual oscillator screech
- **Usage**: Stage 3+ chaos

---

### 2. **audio-horror.ts** - Horror Atmosphere
Specialized horror sounds for building tension and fear.

#### `playMetallicScreech()`
- **Type**: Metal scraping sound
- **Volume**: 0.7 (VERY LOUD)
- **Duration**: 0.5 seconds
- **Effect**: Triple oscillator with bandpass filter
- **Frequency**: 1500-6000 Hz sweep
- **Usage**: Stage 3 popup spawns

#### `playDeepRumble()`
- **Type**: Ominous low rumble
- **Volume**: 0.8 (VERY LOUD)
- **Duration**: 2 seconds
- **Effect**: Sub-bass rumble (20-40 Hz)
- **Usage**: Stage transitions, ambient

#### `playGlitch()`
- **Type**: Digital corruption
- **Volume**: 0.8 (VERY LOUD)
- **Duration**: 0.15 seconds
- **Effect**: Random digital glitches
- **Usage**: Stage 4 popup closes, errors

#### `playSiren()`
- **Type**: Emergency alert siren
- **Volume**: 0.6 (VERY LOUD)
- **Duration**: 3 seconds
- **Effect**: Oscillating 400-800 Hz
- **Usage**: Action-blocking popups (Stage 3)

#### `playHeartbeat()`
- **Type**: Rapid heartbeat
- **Volume**: 0.5 (LOUD)
- **Duration**: 2 seconds (5 beats)
- **Effect**: 60 Hz pulses at 150 BPM
- **Usage**: Stage transitions

---

### 3. **audio-extreme.ts** - EXTREME Horror
The most intense, disturbing, and LOUD sounds for maximum impact.

#### `playAlarm()`
- **Type**: Ear-piercing alarm
- **Volume**: 0.8 (EXTREMELY LOUD)
- **Duration**: 0.6 seconds
- **Effect**: Pulsing 1000-1200 Hz square waves
- **Usage**: Still Alive timeout, critical warnings

#### `playDemonicVoice()`
- **Type**: Demonic voice effect
- **Volume**: 0.7 (VERY LOUD)
- **Duration**: 1.5 seconds
- **Effect**: Triple oscillator with heavy distortion (40-240 Hz)
- **Usage**: Hacker breach, Stage 4 events

#### `playExplosion()`
- **Type**: Explosion sound
- **Volume**: 0.9 (EXTREMELY LOUD)
- **Duration**: 0.8 seconds
- **Effect**: Decaying white noise with lowpass sweep
- **Usage**: Panic button, major events

#### `playScream()`
- **Type**: Distorted scream
- **Volume**: 0.8 (EXTREMELY LOUD)
- **Duration**: 0.7 seconds
- **Effect**: Triple oscillator sweep (1200-4500 Hz) with distortion
- **Usage**: Still Alive timeout (Stage 3+), Stage 4 popups

#### `playChaosNoise()`
- **Type**: Random chaos
- **Volume**: Variable (VERY LOUD)
- **Effect**: Randomly plays one of: Alarm, Scream, Explosion, or Demonic Voice
- **Usage**: Stage 4 action-blocking popups

---

## 🎯 Sound Triggers by Event

### Popup Events
| Event | Stage 1 | Stage 2 | Stage 3 | Stage 4 |
|-------|---------|---------|---------|---------|
| **Popup Spawn** | Silent | Static Noise (0.6) | Metallic Screech / Glitch / Siren / Screech | Scream / Alarm / Explosion / Chaos |
| **Popup Close** | Silent | Distorted Beep | Distorted Beep (louder) | Glitch |
| **Panic Button** | - | Explosion | Explosion | Explosion |

### Still Alive System
| Event | Sound | Volume |
|-------|-------|--------|
| **Button Appears** | Static Noise | 0.3 |
| **Confirmation** | Distorted Beep + Glitch (Stage 3+) | 0.15 |
| **Timeout** | Alarm + Static (0.8) + Scream (Stage 3+) | EXTREMELY LOUD |

### Action-Blocking Popups
| Stage | Sound | Volume |
|-------|-------|--------|
| **Stage 2** | Static Noise | 0.6 |
| **Stage 3** | Siren | 0.6 |
| **Stage 4** | Chaos Noise (random) | 0.7-0.9 |

### Stage Transitions
| Stage | Sound | When |
|-------|-------|------|
| **Stage 2** | Heartbeat | On transition |
| **Stage 3** | Deep Rumble | On transition |
| **Stage 4** | Demonic Voice + Alarm + Scream | Hacker breach |

### Ambient Sounds
Random ambient sounds play every 15-35 seconds based on stage:

| Stage | Sounds | Frequency |
|-------|--------|-----------|
| **Stage 2** | Whisper, Static Noise | 30% chance |
| **Stage 3** | Metallic Screech, Glitch, Deep Rumble, Screech | 30% chance |
| **Stage 4** | Scream, Demonic Voice, Explosion, Alarm | 30% chance |

---

## 🎚️ Volume Levels

### Volume Scale
- **0.1-0.3**: Moderate (whispers, subtle effects)
- **0.4-0.6**: Loud (standard horror sounds)
- **0.7-0.8**: Very Loud (intense moments)
- **0.9+**: Extremely Loud (critical events)

### Loudest Sounds (Top 5)
1. **Explosion** - 0.9 volume
2. **Deep Rumble** - 0.8 volume
3. **Glitch** - 0.8 volume
4. **Scream** - 0.8 volume
5. **Alarm** - 0.8 volume

---

## 🎨 Audio Effects Used

### Distortion
- Wave shaping with custom curves
- Oversample: 4x for quality
- Used in: Beeps, Screams, Demonic Voice

### Filters
- **Bandpass**: Static noise, metallic sounds
- **Highpass**: Whispers (3000 Hz cutoff)
- **Lowpass**: Explosions, rumbles (200 Hz cutoff)

### Stereo Effects
- Independent left/right channels
- Phase modulation for whispers
- Random stereo chaos for static

### Frequency Sweeps
- Linear ramps: Metallic screech
- Exponential ramps: Distorted beeps, screams
- Oscillating: Sirens

---

## 🔧 Technical Details

### Audio Context
- Sample Rate: 44100 Hz (default)
- Channels: Stereo (2)
- Format: Float32Array buffers

### Performance
- All sounds generated in real-time
- No audio files loaded
- Minimal memory footprint
- Instant playback

### Browser Compatibility
- Chrome/Edge: Full support
- Firefox: Full support
- Safari: Full support
- Mobile: Supported (may require user interaction first)

---

## 🎮 Testing Sounds

### Manual Testing
Open browser console and test individual sounds:

```javascript
// Import sounds (if in dev tools)
import { playStaticNoise, playScreech } from './lib/audio';
import { playMetallicScreech, playGlitch } from './lib/audio-horror';
import { playAlarm, playScream } from './lib/audio-extreme';

// Test sounds
playStaticNoise(1, 0.5);
playScreech();
playMetallicScreech();
playGlitch();
playAlarm();
playScream();
```

### In-Game Testing
1. **Stage 1**: No sounds (silent)
2. **Stage 2**: Write 3 entries to trigger
   - Listen for heartbeat on transition
   - Popups spawn with static noise
3. **Stage 3**: Write 5 total entries
   - Deep rumble on transition
   - Metallic screeches and glitches
4. **Stage 4**: Wait 5 minutes
   - Demonic voice + alarm + scream
   - Chaos sounds everywhere

---

## ⚠️ User Experience Notes

### Volume Warnings
- Sounds are intentionally LOUD for horror effect
- Users should adjust system volume accordingly
- Critical events (timeout, breach) are EXTREMELY LOUD
- Ambient sounds provide constant tension

### Accessibility
- No audio required for core functionality
- Visual indicators accompany all audio cues
- Users can mute browser tab if needed
- All important information shown visually

### Performance Impact
- Minimal CPU usage
- No audio file downloads
- Real-time synthesis
- Efficient cleanup

---

## 🎯 Sound Design Philosophy

1. **Escalation**: Sounds get louder and weirder with each stage
2. **Unpredictability**: Random selection keeps users on edge
3. **Layering**: Multiple sounds can play simultaneously
4. **Intensity**: Critical moments use multiple overlapping sounds
5. **Atmosphere**: Ambient sounds maintain constant tension

---

## 📊 Sound Statistics

- **Total Unique Sounds**: 15
- **Volume Range**: 0.15 - 0.9
- **Duration Range**: 0.1 - 3 seconds
- **Frequency Range**: 20 Hz - 8000 Hz
- **Average Loudness**: 0.6 (LOUD)
- **Loudest Sound**: Explosion (0.9)
- **Most Used**: Static Noise
- **Most Disturbing**: Demonic Voice + Scream combo

---

## 🔮 Future Enhancements

Potential additions:
- [ ] Spatial audio (3D positioning)
- [ ] Reverb effects for depth
- [ ] Voice synthesis for text-to-speech
- [ ] Binaural beats for psychological effect
- [ ] Dynamic volume based on user interaction
- [ ] Adaptive audio based on time of day
