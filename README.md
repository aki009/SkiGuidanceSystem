# Ski Guidance System for Blind and Deaf Individuals

## Project Description

This project seeks to develop a ski guidance system that enables blind and deaf individuals to safely ski with the assistance of a guide. The system consists of three main components:

1. **Main Controller**: Operated by the guide, it processes voice commands and wirelessly communicates instructions to the remote units.
2. **Remote Units**: Two wearable devices, one for the left hand/side and one for the right, that provide haptic feedback (vibrations) to guide the skier.
3. **Wireless Communication Link**: Ensures real-time, low-latency communication between the main controller and the remote units, with mechanisms to detect and handle connection faults.

### System Functionality

The guide issues spoken commands through a headset, which are recognized by the main controller using a speech recognition system. These commands are interpreted and sent as instructions to the remote units. The remote units provide haptic feedback by vibrating on either the left or right side (or both), guiding the skier in the following ways:

#### Directional Commands:
- **Command**: `Left`
  - **Response**: The remote unit on the skier's **left side** vibrates briefly.
  - **Purpose**: Indicates that the skier should veer or turn left.
- **Command**: `Right`
  - **Response**: The remote unit on the skier's **right side** vibrates briefly.
  - **Purpose**: Indicates that the skier should veer or turn right.

#### Turning Intensity:
- **Command**: `Turn` (repeated one or more times)
  - **Response**: The remote unit on the indicated side vibrates repeatedly or continuously for the duration of the command.
  - **Purpose**: Indicates the degree of turning. For example:
    - A single `Turn` corresponds to a gentle turn.
    - Repeated `Turn` commands result in prolonged vibrations, guiding the skier to make a sharper or sustained turn.
- **Example**: The guide says `Left, turn, turn` to instruct the skier to make a sharp left turn, with the left remote unit vibrating continuously while the command is active.

#### Stop Command:
- **Command**: `Stop`
  - **Response**: Both remote units vibrate **simultaneously and continuously**.
  - **Purpose**: Alerts the skier to stop immediately for safety.

#### Straight Command:
- **Command**: `Straight` (or silence for a short duration)
  - **Response**: Both remote units **stop vibrating**.
  - **Purpose**: Indicates that the skier should maintain their current trajectory without turning.

### System Safety Features

The system includes built-in fault detection to ensure safety in case of communication issues or hardware failures. If the wireless link between the main controller and one or both remote units is interrupted due to interference or low battery, the following actions occur:
- **Main Controller**: Alerts the guide through an **audio or vibration signal** to indicate a communication fault.
- **Remote Units**: Both units vibrate simultaneously (like the `Stop` command) to signal the skier to stop skiing.

---

## Task Assignments

### 1. Identify System on Chip (SoC) for Main Controller
- **Task Owner**: [Name]
- **Description**: Research and select an SoC for the main controller with the following capabilities:
  - **Fast Speech Recognition**: Capable of recognizing commands with a latency under 0.1 seconds to ensure real-time guidance.
  - **Processing Power**: Handles simultaneous voice recognition, command interpretation, and wireless communication.
  - **Connectivity**: Supports the selected radio link technology for reliable communication with remote units.
- **Deliverables**:
  - A shortlist of candidate SoCs with specifications and latency benchmarks.
  - Recommendation and justification for the chosen SoC.

### 2. Identify Radio Link Technology
- **Task Owner**: [Name]
- **Description**: Evaluate and select a radio link technology to enable robust communication between the main controller and remote units. Key considerations include:
  - **Low Latency**: Transmission delays must remain below 0.1 seconds.
  - **Reliability**: Must operate without significant interference in outdoor environments.
  - **Synchronization**: Mechanisms to ensure the main controller can sync with both remote units.
  - **Fault Detection**: Ability to detect communication failures and trigger appropriate safety responses.
- **Deliverables**:
  - Recommendation of radio link technology with a detailed comparison of options.
  - Protocol for syncing and handling fault conditions.

### 3. Identify System on Chip (SoC) for Remote Units
- **Task Owner**: [Name]
- **Description**: Research and select an SoC for the remote units with the following capabilities:
  - **Wireless Connectivity**: Supports the selected radio link technology.
  - **Low Power Consumption**: Ensures long battery life for extended use.
  - **Real-Time Vibration Feedback**: Processes commands and activates vibrations with a delay under 0.1 seconds.
- **Deliverables**:
  - A shortlist of candidate SoCs with specifications and battery performance.
  - Recommendation and justification for the chosen SoC.

### 4. Develop Software for Main Controller
- **Task Owner**: [Name]
- **Description**: Write and test the software for the main controller to perform the following:
  - **Voice Command Recognition**: Process voice commands with real-time recognition.
  - **Command Mapping**: Interpret commands and map them to specific vibration patterns for the remote units.
  - **Wireless Communication**: Transmit instructions to remote units and monitor communication status.
  - **Fault Handling**: Detect communication issues and alert the guide.
- **Deliverables**:
  - Speech recognition module with testing results.
  - Wireless communication protocol implementation.
  - Fault detection and alert system.
  - Complete documentation.

### 5. Develop Software for Remote Units
- **Task Owner**: [Name]
- **Description**: Write and test software for the remote units to perform the following:
  - **Wireless Syncing**: Sync with the main controller and receive instructions reliably.
  - **Vibration Control**: Translate commands into precise haptic feedback (e.g., single pulse, continuous vibration).
  - **Fault Response**: Activate simultaneous vibrations in case of communication failure.
- **Deliverables**:
  - Wireless communication module with testing results.
  - Vibration control implementation.
  - Fault response mechanism.
  - Complete documentation.

---

## Milestones and Timeline

1. **System on Chip Selection** (Tasks 1 and 3): [Insert Timeline]
2. **Radio Link Technology Selection** (Task 2): [Insert Timeline]
3. **Main Controller Software Development** (Task 4): [Insert Timeline]
4. **Remote Units Software Development** (Task 5): [Insert Timeline]
5. **System Integration and Testing**: [Insert Timeline]
