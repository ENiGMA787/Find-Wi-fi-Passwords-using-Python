# WiFi Password Retrieval Script

## Introduction
This Python script retrieves WiFi passwords for networks previously connected to your Windows system. It helps recover forgotten WiFi passwords by executing Windows `netsh wlan` commands using Python.

**Note**: This script only retrieves passwords for WiFi networks previously connected to your system. It cannot find passwords for unknown or nearby WiFi networks.

## Prerequisites
- **Operating System**: Windows
- **Python**: Version 3.x
- **Module**: `subprocess` (included in Python's standard library)

## How It Works
The script uses the `subprocess` module to execute the following Windows `netsh wlan` commands:
- `netsh wlan show profiles`: Lists all saved WiFi network profiles.
- `netsh wlan show profile PROFILE-NAME key=clear`: Displays the password (Key Content) for a specific WiFi profile.

### Steps
1. Import the `subprocess` module to run terminal commands.
2. Execute `netsh wlan show profiles` to retrieve all saved WiFi profiles.
3. Parse the output to extract profile names.
4. For each profile, run `netsh wlan show profile PROFILE-NAME key=clear` to get the password.
5. Display the WiFi network names and their passwords in a formatted table.
6. Pause the script with an `input()` prompt to allow the user to view the output.

## Installation
1. Ensure Python 3.x is installed on your Windows system.
2. Clone or download this repository:
   ```bash
   git clone https://github.com/ENiGMA787/wifi-password-retrieval.git
