# BatMan-OS-Simulator




```
batman_os/
├── main.py                    # Entry point - Flask server
├── requirements.txt
├── config.py                  # Global config
│
├── core/
│   ├── __init__.py
│   ├── auth.py                # Login, register, session management
│   ├── crypto.py              # Argon2id + AES-256-GCM + MasterKey
│   ├── vault.py               # Encrypted vault per user
│   ├── machine_secret.py      # Machine fingerprint
│   └── user_manager.py        # User CRUD
│
├── api/
│   ├── __init__.py
│   ├── auth_routes.py         # /api/auth/*
│   ├── fs_routes.py           # /api/fs/* (filesystem)
│   ├── app_routes.py          # /api/apps/*
│   ├── system_routes.py       # /api/system/* (cpu/ram/shutdown)
│   ├── terminal_routes.py     # /api/terminal/* (websocket)
│   └── settings_routes.py     # /api/settings/*
│
├── users/                     # Per-user data (created at runtime)
│   └── {username}/
│       ├── root/
│       │   └── batman.db      # Encrypted SQLite
│       ├── desktop/
│       ├── documents/
│       ├── downloads/
│       ├── apps/
│       └── assets/
│           ├── bg.jpg
│           └── ico.png
│
├── static/
│   ├── css/
│   ├── js/
│   └── assets/
│       ├── default_bg.jpg
│       └── default_ico.png
│
└── templates/
    ├── index.html             # Main shell (login + OS)
    ├── login.html             # Login page
    └── home_template.html     # Default home.html copied per user
```
