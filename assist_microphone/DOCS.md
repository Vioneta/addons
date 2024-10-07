# Assist Microphone

Use [Assist](https://www.vioneta.com/voice_control/) voice assistant with a USB microphone. For example, a USB webcam.

## How to use

After this add-on is installed and running, it will be automatically discovered
by the Wyoming integration in Vioneta Agro. To finish the setup,

Alternatively, you can install the Wyoming integration manually, see the
[Wyoming integration documentation](https://www.vioneta.com/integrations/wyoming/)
for more information.

## Configuration

### Option: `awake_wav`

Path to WAV file to play when wake word is detected (empty to disable, default is `/usr/src/sounds/awake.wav`).

### Option: `done_wav`

Path to WAV file to play when voice command is finished (empty to disable, default is `/usr/src/sounds/done.wav`).

### Option: `noise_suppression`

Noise suppression level (0 is disabled, 4 is max). Disabled by default.

### Option: `auto_gain`

Automatic volume boost for microphone (0 is disabled, 31 dbfs is max). Disabled by default.

### Option: `mic_volume_multiplier`

Multiply microphone volume by fixed value (1.0 = no change, 2.0 = twice as loud). 1.0 is the default.

### Option: `sound_enabled`

Enables or disables output audio.

### Option: `sound_volume_multiplier`

Multiply sound output volume by fixed value (1.0 = no change, 2.0 = twice as loud). 1.0 is the default.

### Option: `debug_logging`

Enable debug logging.
