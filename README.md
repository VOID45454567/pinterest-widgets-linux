#  Pinterest Widget for Linux

A beautiful desktop widget that brings your Pinterest boards and feed to your Linux desktop, inspired by iOS and macOS widgets.

## Features

-  **Personal Pinterest Integration** - Display your boards and feed
-  **Customizable Layouts** - Choose from 2×2, 3×3, 4×4 grid sizes
-  **Auto-refresh** - Configurable update intervals
-  **Universal Linux Support** - Works on X11 and Wayland
-  **Hyprland Optimized** - Native layer-shell integration
-  **Privacy First** - All data stays on your device
-  **Containerized** - Easy deployment with Docker

## Quick Start

### Prerequisites

- Docker and Docker Compose
- Pinterest account
- Linux desktop environment

### Installation

1. Clone the repository:
```bash
git clone https://github.com/username/pinterest-widget.git
cd pinterest-widget
```

2. Configure Pinterest API:
```bash
cp .env.example .env
# Edit .env with your Pinterest API credentials
```

3. Start the application:
```bash
docker compose up -d
```

4. Open your browser to `http://localhost:8080` and follow the setup wizard

## Configuration

### Pinterest Developer Setup

1. Create a Pinterest Business account (if needed)
2. Go to [Pinterest Developers](https://developers.pinterest.com/apps/)
3. Create a new application
4. Add redirect URI: `http://localhost:8080/callback`
5. Copy Client ID and Secret to `.env`

### Widget Settings

- **Grid Size**: 2×2, 3×3, 4×4, or custom
- **Refresh Interval**: 15 minutes to 24 hours
- **Board Selection**: Choose which boards to display
- **Position**: Corner placement or custom coordinates

## Architecture

```
├── backend/        # FastAPI server (Python)
│   ├── oauth_manager.py
│   ├── pinterest_client.py
│   └── cache_manager.py
├── frontend/       # Web UI (HTML/JS or React)
│   └── ...
└── docker-compose.yml
```

## Development

### Running Locally

```bash
# Backend
cd backend
pip install -r requirements.txt
uvicorn main:app --reload

# Frontend
cd frontend
npm install
npm run dev
```

## Privacy

This application:
-  Only requests read-only access to your Pinterest data
-  Stores all data locally on your device
-  Never shares your information with third parties
-  Does not post or modify content on your behalf

See our [Privacy Policy](https://username.github.io/pinterest-widget/privacy.html) for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - see [LICENSE](LICENSE) file for details

## Support

For issues, questions, or feature requests, please [open an issue](https://github.com/username/pinterest-widget/issues).

## Roadmap

- [ ] MVP with Pinterest OAuth
- [ ] Setup wizard UI
- [ ] Native GTK4 frontend
- [ ] Hyprland layer-shell integration
- [ ] Flatpak packaging
- [ ] AUR package
- [ ] Multiple board support
- [ ] Animation transitions
- [ ] System tray controls

---

Built with ❤️ for the Linux community
