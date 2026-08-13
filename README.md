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

./images/add-source.jpg

![alt text]((https://raw.githubusercontent.com/MrArgparse/stashOpenMediaPlayerRemote/refs/heads/main/images/add-source.jpg) "Logo Title Text 1")
---

# Install the plugin

Install **Stash Open Media Player Remote** from the package source.

./images/install-plugin.jpg

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

./images/run-script.jpg

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
//tai.chi/stash

Increment Play Count:
Enabled
```

![Example config](./images/example- How it works

## Local Mode

Stash launches the media player directly.

Recommended only when Stash and the media player are running on the same machine.

## Remote Mode

The browser launches:

```text
stashopenmediaplayerremote://
```

which starts the configured media player on your local computer.

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
//tai.chi/stash
```

## Button does not appear

Refresh Stash after installing or updating the plugin.

If the issue persists, reload plugins from Settings → Plugins.
