# LANSploit

A lightweight macOS utility that spoofs a local Minecraft Bedrock LAN world and reroutes all console traffic (Xbox, PlayStation, Nintendo Switch) to any external custom Bedrock server IP.

## Overview

Consoles natively restrict Minecraft Bedrock Edition from adding custom external server IPs directly. **LANSploit** solves this by acting as a local UDP Reverse Proxy on your Mac. It broadcasts a fake LAN game on your local Wi-Fi network and seamlessly forwards the connection to your chosen remote server—no DNS changes or router modifications required.

## Features

* **Native macOS App:** Wrapped in an Automator `.app` with native dialog boxes.
* **Zero External Dependencies:** Powered entirely by built-in macOS AppleScript and Python 3 standard libraries (`socket`, `select`, `sys`).
* **Clean Session Management:** Starts the proxy in the background and cleanly kills the process and temporary files when you click **Stop Proxy**.
* **Cross-Console Support:** Works with PlayStation 4/5, Xbox One/Series X|S, and Nintendo Switch.

## Requirements

* **macOS** (Monterey or newer recommended)
* **Python 3** (Pre-installed on modern macOS or available via Xcode Command Line Tools)
* Your Mac and gaming console must be connected to the **exact same local Wi-Fi/LAN network**.

## Installation & Setup

1. Open **Automator** on your Mac (`Cmd + Space` -> type `Automator`).
2. Click **New Document**, select **Application**, and click **Choose**.
3. In the left sidebar, search for **Run AppleScript** and drag it into the workflow area.
4. Paste the [**LANSploit** AppleScript](https://github.com/aidenonlinux/lansploit/blob/main/code.txt) code into the editor.
5. Press `Cmd + S`, name the app **`LANSploit`**, set the File Format to **Application**, and save it to your **Applications** folder.

## Usage

1. Double-click **LANSploit.app**.
2. Enter the **Server IP or Domain** of the custom Bedrock server you want to join and click **Next**.
3. Enter the **Server Port** (default is `19132`) and click **Start Proxy**.
4. If prompted by macOS Firewall, click **Allow** to permit incoming network connections.
5. Launch **Minecraft** on your console, navigate to the **Friends** tab, and join the **LAN Game** listed at the bottom.
6. When finished playing, click **Stop Proxy** on your Mac to shut down the relay.

## Troubleshooting

* **LAN World not appearing:** Make sure your Mac's firewall isn't blocking incoming UDP traffic on port `19132`, and verify both devices are on the same subnet (not a Guest Wi-Fi network).
* **Port already in use:** Ensure Minecraft Bedrock or any other local server software isn't already running on your Mac and occupying port `19132`.
* **Developer cannot be verified:** If sharing the `.app` with others, right-click `LANSploit.app` and select **Open** to bypass macOS Gatekeeper on first launch.

## License

MIT License — feel free to modify and distribute.
