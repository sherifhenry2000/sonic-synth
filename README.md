# Sonic Synth - Group Music Tech

Sonic Synth is an interactive synthesizer which senses objects in front of a moving sonar device, translating physical spatial data into an evolving, unique generative soundscape. By providing a seamless journey from hardware telemetry to dynamic audio generation, the system acts as an end-to-end pipeline mapping spatial coordinates directly to complex acoustic parameters.

---

## 🏗 System Architecture

The project relies on four interconnected layers to process spatial telemetry into high-fidelity audio:

| Component | Role & Function |
| :--- | :--- |
| **Sonar & Arduino** | An ultrasonic sensor scans the environment to detect object distance and width with high precision, streaming raw serial data to the software stack. |
| **Processing GUI** | A dynamic visual "radar" display that maps distance and angle data instantly, converting raw serial input and parameter data into structured OSC messages. |
| **JUCE Engine** | The central brain of the application that manages state, analyzes incoming telemetry, and models physical entities by assigning properties like size, angle, and distance. |
| **SuperCollider** | Dynamically generates audio based on spatial telemetry from the OSC messages. |

---

## 🚀 Installation & Setup

### Prerequisites

* [Arduino IDE](https://www.arduino.cc/en/software)
* [Processing](https://processing.org/download)
* [JUCE Framework](https://juce.com/)
* [SuperCollider](https://supercollider.github.io/) (with [sc3-plugins v3.13.0](https://github.com/supercollider/sc3-plugins/releases/tag/Version-3.13.0))

---

### 1. Hardware Setup

1. Connect your ultrasonic sensor to the Arduino.
2. Open `Sonicarduino/sonicarduino/sonicarduino.ino` and upload it to the board.
3. Note the serial port being used (e.g., `COM3` on Windows or `/dev/ttyUSB0` on macOS/Linux).

---

### 2. Running the Software Stack (Windows)

1. **Launch SuperCollider:** Open `sonic-synth-scd/sonicDrones.scd` and boot the audio server (`Ctrl + B`).
2. **Start JUCE Engine:** Build and run the JUCE application via your preferred IDE or run the executable directly at:
   ```text
   sonic-synth-juce-gui/sonic-synth-juce-gui.exe
