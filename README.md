# Saviyt

<p align="center">
  <strong>A self-hosted, privacy-focused YouTube frontend.</strong>
</p>

<p align="center">
  Browse and watch YouTube through your own local server, with configurable playback, interface and network settings.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python" alt="Python">
  <img src="https://img.shields.io/badge/License-AGPL--3.0-green" alt="AGPL-3.0">
  <img src="https://img.shields.io/badge/Platform-Linux%20%7C%20Windows-lightgrey" alt="Platforms">
</p>

---

## Overview

**Saviyt** is a self-hosted YouTube frontend built around a Python-based server architecture. It allows users to access YouTube through a locally hosted interface rather than relying directly on the standard YouTube website.

The project provides configurable playback preferences, interface customization, request routing and optional Tor integration.

The objective is to provide a more customizable and locally controlled YouTube browsing experience.

## Features

- **Self-hosted:** Run your own local YouTube frontend.
- **Video Playback:** Configurable video resolution and codec preferences.
- **Subtitles:** Configure subtitle availability and preferred language.
- **Interface Customization:** Choose between light, gray and dark themes.
- **Theater Mode:** Enable a theater-style viewing experience.
- **Comments:** Configure comment visibility and sorting.
- **Related Videos:** Control how related videos are displayed.
- **SponsorBlock Support:** Optional SponsorBlock integration.
- **Tor Integration:** Optionally route supported requests through Tor.
- **Subscription Management:** Local subscription functionality.
- **Configurable Network:** Customize the server port and network access settings.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core application |
| Flask | Web application framework |
| Gevent | Concurrent networking and WSGI server |
| urllib3 | HTTP requests |
| PySocks | SOCKS proxy support |
| Stem | Tor integration |
| Brotli | Compression support |
| SQLite | Local subscription storage |

## Project Structure

```text
Saviyt/
│
├── youtube/
│   ├── watch.py
│   ├── search.py
│   ├── channel.py
│   ├── playlist.py
│   ├── comments.py
│   ├── subscriptions.py
│   └── ...
│
├── tests/
│
├── server.py
├── settings.py
├── requirements.txt
├── requirements-dev.txt
├── start_server.sh
├── run.bat
├── generate_release.py
├── pytest.ini
├── HACKING.md
└── README.md
```

## Installation

### Prerequisites

- Python 3
- Git
- pip
- A terminal or command prompt

### 1. Clone the repository

```bash
git clone https://github.com/5aranx/Saviyt.git
```

```bash
cd Saviyt
```

### 2. Create a virtual environment

**Linux / macOS:**

```bash
python3 -m venv env
source env/bin/activate
```

**Windows:**

```powershell
python -m venv env
.\env\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Start the server

```bash
python server.py
```

The server uses port `8080` by default.

### 5. Open Saviyt

Visit:

```text
http://127.0.0.1:8080
```

You can now access the locally hosted interface.

## Linux Quick Start

Alternatively, after installing dependencies, you can use the included startup script:

```bash
chmod +x start_server.sh
./start_server.sh
```

The script launches the server in the background and writes output to `server.log`.

To inspect logs:

```bash
tail -f server.log
```

## Configuration

Saviyt generates a `settings.txt` configuration file automatically.

The configuration allows you to customize different aspects of the application.

### Network Settings

| Setting | Default | Description |
|---|---|---|
| `port_number` | `8080` | Server listening port |
| `route_tor` | `0` | Tor routing mode |
| `tor_port` | `9150` | Tor SOCKS port |
| `proxy_images` | `True` | Route images through the server |

### Playback Settings

| Setting | Default | Description |
|---|---|---|
| `default_resolution` | `720` | Preferred video resolution |
| `subtitles_mode` | `0` | Default subtitle mode |
| `subtitles_language` | `en` | Preferred subtitle language |
| `autoplay_videos` | `False` | Automatic video playback |
| `use_sponsorblock_js` | `False` | Enable SponsorBlock |

### Interface Settings

| Setting | Default | Description |
|---|---|---|
| `theme` | `0` | Light, gray or dark theme |
| `theater_mode` | `True` | Theater mode |
| `comments_mode` | `1` | Comment visibility |
| `related_videos_mode` | `1` | Related video visibility |
| `video_player` | `1` | Video player selection |

**Note:** The application creates default settings automatically. Refer to `settings.py` for the complete list of supported configuration options.

## Development

To install development dependencies:

```bash
pip install -r requirements-dev.txt
```

Run the test suite:

```bash
python -m pytest
```

For contribution guidelines and architecture details, see [HACKING.md](HACKING.md).

## Security Considerations

- By default, the server listens only on `127.0.0.1`.
- Exposing the server to external networks requires additional security considerations.
- Avoid enabling foreign network access unless you understand the implications.
- Do not expose an unsecured instance directly to the public internet.
- Keep dependencies updated.

## License

Saviyt is distributed under the **GNU Affero General Public License v3.0 (AGPL-3.0)**.

See [LICENSE](LICENSE) for the complete license text.

## Repository

**GitHub:** https://github.com/5aranx/Saviyt

---

<p align="center">
  Built with Python.
</p>
