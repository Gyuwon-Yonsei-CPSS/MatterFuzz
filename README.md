# 🔥 MatterFuzz

Welcome to **MatterFuzz**, a Python-based fuzzing tool designed to test IoT devices using the Matter protocol for potential Denial of Service (DoS) or crashes. This tool generates and mutates valid Matter protocol messages, sends them to IoT devices, and detects any abnormal behavior.

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/Python-3.x-blue.svg" alt="Python">
</p>

---

## 🎯 Features

- **🔧 Mutation-based fuzzing** of Matter protocol messages
- **📡 Device interaction** with IoT devices (e.g., Tapo Plug, Matter Hub)
- **💣 DoS and Crash detection** with automated logging
- **📊 Detailed logging** of responses and crashes

---

## 📋 Table of Contents

1. [Installation](#-installation)
2. [Usage](#-usage)
3. [Directory Structure](#-directory-structure)
4. [Fuzzing Trigger](#-fuzzing-trigger)
5. [How It Works](#-how-it-works)
6. [Contributing](#-contributing)
7. [License](#-license)

---

## 🚀 Installation
To get started with **MatterFuzz**, follow these steps

1. Clone this repository
```
   git clone https://github.com/Gyuwon-Yonsei-CPSS/MatterFuzz.git
   cd MatterFuzz
```

   
Install the required dependencies
```
pip install -r requirements.txt
```


💻 Usage
Here's how you can start fuzzing your IoT devices using MatterFuzz

Configure Target IP: Set the IP address of your target IoT device (e.g., Tapo Plug) in the fuzz.py file
```
target_device_ip = "192.168.1.100"  # Replace with your device's IP
```

Run the Fuzzer
```
python fuzz.py
```

View Results
Logs will be stored in the results/logs/ directory.
Any crashes or abnormal behavior will be saved in results/crashes/.


📂 Directory Structure
The MatterFuzz project is organized as follows
```
matter_blackbox_fuzzer/
│
├── fuzz.py                 # Main fuzzing script
├── matter_protocol.py       # Matter protocol message generation and mutation
├── device_interaction.py    # Communication with IoT device
├── logger.py                # Logs results and crashes
├── tests/                   # Unit tests for each module
│   ├── test_matter_protocol.py
│   └── test_device_interaction.py
├── results/                 # Results and logs
│   ├── logs/
│   └── crashes/
├── README.md                # Project description
└── requirements.txt         # Dependencies
```

🚦 Fuzzing Trigger
MatterFuzz uses mutation-based fuzzing to alter valid Matter protocol messages and test device responses.

Mutation-based fuzzing: Generates valid messages and randomly mutates them to simulate unexpected input.
Crash Detection: If a device fails to respond or behaves abnormally (DoS or crash), the fuzzer logs the faulty message in the crashes/ folder.


Triggers for DoS or crashes may include
Unresponsive Device: No response from the IoT device.
Unexpected Behavior: Device reboots, becomes slow, or stops functioning normally.


🛠️ How It Works
MatterFuzz follows these core steps

Message Generation
The fuzzer generates valid Matter protocol messages using the format defined in matter_protocol.py.

Message Mutation
Each generated message is slightly altered using random mutation techniques to create unpredictable input for the device.

Device Interaction
The mutated message is sent to the target device (e.g., Tapo Plug), and the response is recorded.

Response Analysis
If the device crashes or becomes unresponsive, the message is saved in the crashes/ folder for further analysis.


🧩 Contributing
Contributions are welcome! Here's how you can get involved


Fork the repository
Create your feature branch: git checkout -b feature/YourFeature
Commit your changes: git commit -m 'Add YourFeature'
Push to the branch: git push origin feature/YourFeature
Open a pull request


📜 License
This project is licensed under the MIT License. See the LICENSE file for more information.


Happy fuzzing! 😎
