# ZMK Configuration for Horizon Keyboard

This repository provides ZMK shield and default keymap for the [Horizon](https://github.com/skarrmann/horizon) keyboard.

The keyboard definition supports [ZMK Studio](https://zmk.studio/). Refer to the keymap to locate the `&studio_unlock` key.

## Debug Logging

This configuration has USB debug logging enabled for troubleshooting. Debug output includes both USB and Bluetooth connection information.

### Viewing Debug Output

**On Linux/macOS:**
```bash
# Find the device (usually /dev/ttyACM0 or similar)
ls /dev/tty*

# Read the debug output
cat /dev/ttyACM0
# or use screen
screen /dev/ttyACM0 115200
```

**On Windows:**
- Use [PuTTY](https://www.putty.org/) or another serial terminal
- Connect to the COM port assigned to your keyboard (check Device Manager)
- Set baud rate to 115200

**Using Python (cross-platform):**
```bash
# Install pyserial
pip install pyserial

# Read output
python -m serial.tools.miniterm /dev/ttyACM0 115200
# On Windows, use COM port like COM3 instead of /dev/ttyACM0
```

### What You'll See

The debug output shows:
- USB connection events
- Bluetooth pairing and connection status
- Key press/release events
- Power management state changes
- ZMK Studio communication (when enabled)

Debug logging is most useful when troubleshooting connectivity issues or verifying firmware behavior.
