# NEPTUNE Radar V3

NEPTUNE Radar V3 is a local web radar for Neptune.  
This build uses a single launcher, optional password protection, and optional multi-instance startup from one config file.

## Quick Start

1. Extract the radar folder.
2. Open the folder.
3. Run `Start-Radar.exe`.
4. In Neptune, connect to:
   - IP: `127.0.0.1`
   - Port: `7823`
5. Open the radar in your browser:
   - `http://127.0.0.1:7823`
   
Use the radar in a desktop or mobile browser.
- Desktop browsers open the normal desktop layout automatically.
- Mobile phones open the mobile layout automatically.
- If needed, you can force a view manually:
  - Desktop: http://127.0.0.1:7823/?view=desktop
  - Mobile: http://127.0.0.1:7823/?view=mobile
- The default radar address stays: http://127.0.0.1:7823/

## Updating

To update Radar V3, run:
- `Update-Radar-v2.exe`

This updater checks:
- `https://github.com/pubgdma/NEPTUNE-RADAR-WINDOWS-V3.git`


## Password Protection

To protect the web page with a password, edit:
- `config/password.toml`

Disabled:
```toml
password = ""
```

Enabled:
```toml
password = "MySecret123"
```

How it works:
- empty password = no login required
- non-empty password = browser login required before the radar opens

## Multiple Instances

To run more than one radar at the same time, edit:
- `config/config.toml`

Example:
```toml
[server]
ip = "0.0.0.0"

[[instances]]
id = "7823"
port = 7823
enabled = true

[[instances]]
id = "7824"
port = 7824
enabled = true

[[instances]]
id = "7825"
port = 7825
enabled = false
```

Rules:
- each instance must use a unique port
- set `enabled = true` for every instance you want to start
- `Start-Radar.exe` launches all enabled instances automatically

Examples:
- one enabled instance = one radar
- three enabled instances = three radars

Browser examples:
- `http://127.0.0.1:7823`
- `http://127.0.0.1:7824`

If you want LAN or VPN access:
- keep `ip = "0.0.0.0"`
