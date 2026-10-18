# EVEN Assistant — Master Blueprint & Dual-Device Guide

Target Device: POCO M4 Pro 4G (MediaTek Helio G96, MIUI 13/14)
Reference Blueprint: Realme 6 (MediaTek Helio G90T, realme UI 2.0)
Package Name: com.even.assistant

### Phase 1: Smart Wake-Word System
- Wake-word phrases: "Hey Even" / "Even, sun." -> Immediate reply: "Haan Boss, bolo."
- Continuous speech loop with silence error backoff & rearm.
- Offline wake-word detection status: MARKED AS FUTURE UPGRADE (requires vendor DSP / Porcupine license). Native loop provides active foreground hotword detection.

### Phase 3: Phone Actions
- Calling: "Maa ko call lagao" -> Custom confirmation dialog before ACTION_CALL.
- App Launches: YouTube, WhatsApp, Instagram, Telegram, Facebook, Chrome, Camera, Maps.
- Safe Messaging: SMS text preview + Boss confirm before sending.
- Alarms & Timers: "10 minute ka timer", "Subah 7 baje ka alarm" via AlarmClock API.
- Audio Controls: Media Play/Pause, Next, Volume adjustments.

### Phase 4: Advanced Intelligence
- AI Conversation: Online Gemini streaming in Hindi/Hinglish Boss persona.
- Consent-based Memory: "Yaad rakhna..." -> Prompts Boss before local storage in SharedPreferences.MODE_PRIVATE.
- Multi-step Commands: "YouTube kholo aur volume badhao" chained via MultiStepCommandParser.
- Offline Fallback: Local intent engine executes device actions without internet.

### Phase 5: Background & Testing
- Lockscreen wake via setShowWhenLocked(true) & setTurnScreenOn(true).
- Bluetooth headset media key hook via BluetoothMediaReceiver.
- MIUI Battery saver: Set to "No restrictions".
- MIUI Autostart: Allow EVEN in background.
