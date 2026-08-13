# Stash Open Media Player Remote

Open Stash scenes in an external media player such as SMPlayer, VLC, MPC-HC, MPV, and others.

Supports:

- Local media player launching
- Remote protocol launching (recommended for Docker, Unraid, NAS, and remote Stash installations)
- Path mapping between Stash paths and SMB/network paths
- Optional play count incrementing

---

# Add the source

Add the following package source to Stash:

```text
Name:
stashOpenMediaPlayerRemote

URL:
https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/index.yml
```


![alt text](https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/images/add-source.jpg)

---

# Install the plugin

Install **Stash Open Media Player Remote** from the package source.

![alt text](https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/images/install-plugin.jpg)

---

# Install the protocol handler (Remote Mode)

If Stash is running on:

- Docker
- Unraid
- NAS
- Another machine

then enable **Use Remote Protocol Handler** and install the helper script on the computer where the media player is installed.

Navigate to the plugin folder and run:

```bash
python install-stashOpenMediaPlayerRemote.py
```

![alt text](https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/images/install-protocol.jpg)

---

# Example configuration

## Remote Setup (Recommended)

```text
Media Player Path:
C:\Program Files\SMPlayer\smplayer.exe

Use Remote Protocol Handler:
Enabled

Path Mapping From:
/data

Path Mapping To:
//network_path/stash

Increment Play Count:
Enabled
```

![alt text](https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/images/plugin-config.jpg)

## Local Mode

Stash launches the media player directly.

Recommended only when Stash and the media player are running on the same machine.

## Remote Mode

The browser launches:

```text
stashopenmediaplayerremote://
```

which starts the configured media player on your local computer. 

Make sure to accept the permission prompt in your browser the first time you click the "open with external player" button.

This mode is recommended for:

- Docker
- Unraid
- NAS
- Remote servers

---

# Troubleshooting

## Media file not found

Verify that:

- Path Mapping From matches the Stash file path.
- Path Mapping To points to a valid SMB/network share.
- The media file can be opened manually from Windows Explorer.

Example:

```text
/data
```

→

```text
//network_path/stash
```

## Button does not appear

Refresh Stash after installing or updating the plugin.

If the issue persists, reload plugins from Settings → Plugins.
