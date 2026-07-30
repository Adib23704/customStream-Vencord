# СustomStream-Vencord

Discord plugin that replaces default stream preview with custom images. Features profiles system and automatic slideshow rotation.

## Features
- **Profiles System**: Create up to 5 profiles with 50 images each
- **Automatic Slideshow**: Images rotate every ~5 minutes (Discord controlled)  
- **Sequential/Random**: Random uses a shuffle — no repeats until all images are shown
- **Ctrl+V**: Paste images from clipboard
- **Multi-select**: Ctrl/Shift+Click images to delete several at once
- **Local Storage**: Images stored in IndexedDB, no external servers
- **Panel Button**: Quick access button next to microphone controls (can be hidden in plugin settings)
- **Hotkey**: `Alt+1` opens and closes the gallery — rebindable in the plugin settings

## Installation

Requires a [Vencord dev install](https://docs.vencord.dev/installing/) — the git checkout you build
yourself, not the installer build.

The plugin lives in `src/userplugins/` inside that checkout, e.g.
`C:\Vencord\src\userplugins\customStream`. Create the `userplugins` folder if it is not there yet;
its subfolder can be named anything.

From the root of the checkout:

```bash
git clone https://github.com/MrTopQ/customStream-Vencord src/userplugins/customStream
```

No git? Download the repository as a ZIP and put this folder in `src/userplugins/` by hand — the
result is the same. Then, from the root of the checkout:

```bash
pnpm build && pnpm inject
```

`pnpm inject` is only needed the first time, when this Vencord is not patched into Discord yet.
Restart Discord afterwards, then enable **CustomStreamTopQ** in Vencord settings → Plugins.

## Notes
- **Your own preview may show your real screen for the first minutes** — that's a local snapshot, it never leaves your PC and disappears after a while. Discord has already accepted your custom image: the plugin replaces the thumbnail uploaded to Discord's servers, so viewers only ever see it.
- **Panel button disappeared after a Discord update?** The patch broke — a fix will be released here, update the plugin.

### Panel Button
Quick access button in the account panel showing current status:

![Panel Button](screenshots/panel-button.png)
![Panel Button1](screenshots/panel-button1.png)

### Gallery Modal
Manage your stream preview images with an intuitive interface:

![Gallery Modal](screenshots/gallery-modal.png)
