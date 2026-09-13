# Whipet AI

![Whip divider](assets/divider.png)

Sometimes your coding agent is going too slow, and you must whip it into shape..

Or pat it on the shoulder. Your call.

Works with Claude Code, Codex, and any coding agent - it just sends Ctrl-C and types.

![Whipet AI demo: on Claude Code and Codex - the whip cracks, FASTER gets typed, then a hand pats and types kind words](assets/demo.gif)

## Install + run

This fork is not on npm yet. Install straight from GitHub (Node 18 to 24; Node 26 breaks electron's installer):

```bash
npm install -g github:shmulc8/Whipet
whipet
```

windows and mac supported out of the box, but Linux is a special snowflake so you need to install `xdotool` for keyboard automation

```bash
sudo apt install xdotool
```

## Controls

- Click the Dock or tray icon, or press `Option+Shift+W` (`Alt+Shift+W`): spawn whip.
- Right-click tray icon: quit.
- Flick, then click while the whip is snapping: that is a strike. It sends an interrupt (Ctrl-C) and one of the encouraging messages!
- A click with a still whip does nothing. Fast flicks alone crack with sound and sparks but never type.
- Right click: drop whip.
- Scroll wheel or middle click: switch between whip and pat without leaving the screen.
- Smash the bottles on the shelves for points. Fast hits in a row multiply the score; your best is kept.

## Pat on the shoulder

For the days it deserves it. Press `Option+Shift+P` (`Alt+Shift+P`) or pick it from the tray menu: a hand follows
your mouse. Left click pats it, sends a kind word (no interrupt, just the message and Enter) and floats some hearts.
Right click waves goodbye. Scroll or middle click swaps back to the whip. From a terminal, `whipet pat` summons the
hand and `whipet whip` the whip; plain `whipet`, the Dock icon and the tray icon reopen whichever you used last.
Right click the Dock icon for a Whip / Pat menu.

## macOS setup

On first run `whipet` builds `Whipet AI.app` inside the package (a renamed, re-signed copy of the bundled
Electron with the whip icon) and launches it through `open`, so macOS sees an app called Whipet AI rather
than your terminal. Typing into the focused app needs Accessibility access for it: when macOS prompts,
open System Settings > Privacy & Security > Accessibility and turn on **Whipet AI**. If it is not listed:

```bash
open -R "$(npm root -g)/whipet/Whipet AI.app"
```

Drag it onto the list and turn it on.

If `whipet` prints `Could not load Electron` on Node 26, electron's postinstall failed to unzip its binary.
Reinstall on Node 22 or 24 (`nvm use 24 && npm install -g whipet`).

## Credits

Fork of [GitFrog1111/OpenWhip](https://github.com/GitFrog1111/OpenWhip). The macOS fixes, physics, bottles and pat mode
are proposed upstream in [PR #65](https://github.com/GitFrog1111/OpenWhip/pull/65). MIT licensed.
