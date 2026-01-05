
Tags: [[Ports]], [[Firewall]], [[Wireless-Security]], [[WEP]], [[WPA]], [[WPA2]], [[WPA3]], [[Kali]]

**Aircrack-ng** is an advanced suite of software tools designed for auditing and testing the security of wireless networks. This open-source framework is primarily used for network security diagnostics and is particularly effective in executing attacks like packet sniffing, deauthentication, and the cracking of WEP and WPA/WPA2-PSK keys.

## Key Features

- **Versatility:** Supports a wide range of wireless network adapters.
- **Comprehensive Tools:** Includes utilities for network monitoring, packet capturing, and password cracking.
- **Cross-Platform:** Available for Linux, Windows, and OS X platforms.
- **Active Development:** Regularly updated to address new vulnerabilities and improve functionality.
- **Community Support:** Benefits from a large, active community of users and developers.

Here's a table comparing the different tools within the Aircrack-ng suite, each designed for specific tasks related to network security testing, particularly focusing on WiFi networks.

| **Tool**           | **Purpose**                                                                               | **Usage Example**                                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| **airmon-ng**      | Manages monitor mode on wireless network cards.                                           | `airmon-ng start wlan0`                                                                                              |
| **airodump-ng**    | Captures raw 802.11 frames for inspection and network traffic monitoring.                 | `airodump-ng wlan0mon`                                                                                               |
| **aireplay-ng**    | Injects frames to generate traffic and manipulate WiFi associations and authentication.   | `aireplay-ng --deauth 100 -a [BSSID] wlan0mon`                                                                       |
| **aircrack-ng**    | Cracks WEP and WPA/WPA2-PSK keys using captured packets.                                  | `aircrack-ng -w wordlist.txt -b [BSSID] [capfile.cap]`                                                               |
| **airbase-ng**     | Creates a fake AP and allows complex attack scenarios.                                    | `airbase-ng -e "Fake AP" -c 6 wlan0mon`                                                                              |
| **airodump-ng**    | Captures packets from a specific network to aid in analysis and cracking.                 | `airodump-ng --bssid [Target BSSID] -c [Channel] wlan0mon`                                                           |
| **airserv-ng**     | Turns a wireless card into an access point server for other Aircrack-ng tools to connect. | `airserv-ng -d wlan0mon -p 6666`                                                                                     |
| **airtun-ng**      | Creates a virtual tunnel interface for decrypting WEP traffic.                            | `airtun-ng -a [BSSID] wlan0mon`                                                                                      |
| **packetforge-ng** | Forges arbitrary packets to be used in injection attacks.                                 | `packetforge-ng -0 -a [BSSID] -h [Source MAC] -k 255.255.255.255 -l 255.255.255.255 -y [PRGA file] -w [output file]` |
| **airdecap-ng**    | Decrypts WEP/WPA/WPA2 capture files to plaintext.                                         | `airdecap-ng -e "AP Name" -p [password] [capfile.cap]`                                                               |
| **airdecloak-ng**  | Removes WEP cloaking from a packet capture to reveal hidden data.                         | `airdecloak-ng -0 [inputfile.cap]`                                                                                   |
| **besside-ng**     | Automated tool for capturing WPA handshakes, WEP keys, and providing WPA cracking.        | `besside-ng wlan0mon`                                                                                                |