[1]: https://github.com/topics/wifi-hacking ""
[2]: https://github.com/wifiphisher/wifiphisher ""
[3]: https://github.com/derv82/wifite2 ""
[4]: https://github.com/wifiphisher/wifiphisher.git ""

# WPA2 Handshake Automation Tool

The **WPA2 Handshake Automation Tool** is a Python3 script designed to simplify the process of setting up and capturing WPA2 handshakes. Whether you're testing your own network security or conducting ethical hacking, this tool streamlines the steps required to capture WPA2 handshakes.

## Features

- Quick setup for making and capturing WPA2 handshakes
- Requires a WIFI card that supports Monitor mode and Packet injection
- Works on Linux distributions
- Utilizes the Aircrack-ng suite of tools

## Prerequisites

Before using this tool, ensure you have the following:

1. **WIFI Card with Monitor Mode and Packet Injection Support**:
   - Your WIFI card must support monitor mode and packet injection. This allows the card to capture wireless traffic effectively.

2. **Linux Distribution**:
   - This tool is designed for Linux environments. Make sure you're running a Linux distribution.

3. **Aircrack-ng Suite**:
   - Install the Aircrack-ng suite on your system. It includes essential tools for wireless network auditing, including packet capture, WEP/WPA/WPA2 cracking, and more.

## Usage

1. **Clone the Repository**:
   ```
   git clone https://github.com/yteicos-ItNa07/wifi_breaker.git
   cd wifi_breaker
   ```

2. **Configure Your WIFI Card**:
   - Set your WIFI card to monitor mode using `airmon-ng`:
     ```
     sudo airmon-ng start wlan0
     ```

3. **Run the Automation Tool**:
   - Execute the Python script:
     ```
     python3 wpa2_handshake_automation.py
     ```

4. **Follow the Prompts**:
   - The tool will guide you through the process:
     - Scanning for available networks
     - Selecting the target network
     - Capturing the WPA2 handshake
     - Saving the handshake file

## Disclaimer

- Use this tool responsibly and legally. Ensure you have proper authorization before testing any network.
- Respect privacy and adhere to ethical guidelines when capturing handshakes.

## Contributions

Contributions and improvements are welcome! Feel free to fork this repository and submit pull requests.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

Source: Conversation with Bing, 4/27/2024
(1) wifi-hacking · GitHub Topics · GitHub. https://github.com/topics/wifi-hacking.
(2) GitHub - wifiphisher/wifiphisher: The Rogue Access Point Framework. https://github.com/wifiphisher/wifiphisher.
(3) GitHub - derv82/wifite2: Rewrite of the popular wireless network .... https://github.com/derv82/wifite2.
(4) undefined. https://github.com/wifiphisher/wifiphisher.git.
