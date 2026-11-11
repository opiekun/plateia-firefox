<div align="center">

<img src="extension/icons/128.png" width="96" alt="Plateia Community icon">

# Plateia Community

A Firefox extension for Twitch and Kick. Community-maintained fork of [Plateia](https://github.com/DredsGG/plateia) by [Dreds](https://github.com/DredsGG).

![Firefox](https://img.shields.io/badge/Firefox-140%2B-FF7139?logo=firefoxbrowser&logoColor=white)
![Manifest V3](https://img.shields.io/badge/Manifest-V3-4285F4)
![License](https://img.shields.io/badge/license-MIT-green)

**Languages:** Português · English · Español

<img src="docs/plateia-twitch-room.png" width="900" alt="Plateia Twitch room with channels and streams">

<sub>Upstream screenshot with simulated channels and data.</sub>

</div>

## Features

Plateia adds a room to Twitch and Kick for managing channels and watching streams. Each site has its own room, channel list, settings, and PokeIdle panel.

### Twitch

- Claims available channel-points chests and completed Drops.
- Opens streams in a room, rotates active slots, and maintains chat presence for channels on the list.
- Adds channels by name, link, followed channels, or PokeIdle's channel list.
- Shows points, chest activity, Drops, and PokeIdle bonus status.
- Can redeem PokeIdle rewards with channel points when the configured conditions are met.

### Kick

- Opens and rotates streams in a room with a channel queue.
- Shows channel-point balances and PokeIdle bundle progress.
- Can redeem PokeIdle reward bundles, claim the daily reward, and claim completed Drops.

<img src="docs/plateia-kick-room.png" width="900" alt="Plateia Kick room showing channels and streams">

<sub>Upstream screenshot with simulated channels and data.</sub>

### PokeIdle

Open [PokeIdle](https://pokeidle.io) in a separate tab to let Plateia read the game's channel and bonus status. The PokeIdle tab shows active bonuses, upcoming redemptions, and recent activity. Twitch and Kick integrations depend on the relevant game and streaming accounts being linked.

<img src="docs/plateia-twitch-redeem.png" width="320" alt="PokeIdle panel showing bonuses and redemption status">

**Automatic redemption is enabled by default** and can spend channel points. Turn it off in Settings if you do not want Plateia to redeem rewards.

## Install

Firefox desktop 140 or newer is required.

1. Download [Plateia Community v0.9.4](https://github.com/opiekun/plateia-firefox/releases/download/community-v0.9.4/plateia-community-0.9.4.xpi).
2. Open the downloaded `.xpi` in Firefox and confirm the installation and requested permissions. The add-on is signed by Mozilla and stays installed after Firefox closes.
3. Open or reload Twitch or Kick and use the Plateia button on the page.

If the button does not appear, check that Plateia Community has permission to access the relevant site in `about:addons`. The fork uses its own add-on ID, so settings from a different Plateia installation do not transfer automatically.

For development, open `about:debugging#/runtime/this-firefox`, choose **Load Temporary Add-on**, and select `extension/manifest.json`. Temporary add-ons are removed when Firefox closes.

## Updates

Automatic updates are not configured for this fork. Download and install future signed releases manually. The inherited update controls in the extension do not check for Firefox releases.

## Privacy and permissions

Plateia stores its settings in browser local storage. To provide its features, it reads session information from Twitch and Kick and sends authenticated requests to those services. PokeIdle integration reads game status from its site. Bug reports open a GitHub issue draft; review the text before submitting it.

Firefox displays the requested permissions and data categories during installation. Do not include account credentials or session tokens in bug reports.

## Report a bug

Open an [issue](https://github.com/opiekun/plateia-firefox/issues) with your Firefox version, Plateia version, site, steps to reproduce, and the result you expected. The **Report bug** button in either room can prepare a diagnostic for you to review.

## Development

The extension is in `extension/`. Its background script is `extension/src/fundo.js`, shared code is in `extension/src/comum.js`, and the Twitch and Kick room code is in `extension/src/sala.js` and `extension/src/kick/`.

Run Mozilla's validator from the repository root:

```sh
npx web-ext lint --source-dir extension --self-hosted
```

The Node test suite requires `jsdom`:

```sh
node tests/rodar-todos.cjs extension
```

This fork maintains Firefox support based on upstream v0.9.4. Changes from upstream need review and Firefox testing before inclusion. Firefox for Android is not tested.

## License and credits

[MIT](LICENSE). Plateia was created by [André Miller Fleck (Dreds)](https://github.com/DredsGG). This fork is independently maintained by [Opiekun](https://github.com/opiekun). Third-party license notices are included alongside bundled code.
