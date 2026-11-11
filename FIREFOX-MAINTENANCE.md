# Firefox maintenance

Based on DredsGG/plateia v0.9.4, MIT licensed. This fork has a new add-on ID and does not inherit another add-on's stored settings.

## Current state

Firefox uses the retained v0.9.4 background scripts, browser API and page-context fetch compatibility. Firefox update checks and update application are disabled: upstream v0.9.5 dropped Firefox support. Do not treat upstream installation or auto-update instructions as applying to this fork. The user reports the signed build is installed and working in Firefox; individual Twitch and Kick features have not been independently verified.

## Temporary installation

Open `about:debugging#/runtime/this-firefox`, choose **Load Temporary Add-on**, then select `extension/manifest.json`. This is removed when Firefox exits. Review the extension's requested access before use. Automatic redemption can spend points; leave it disabled until verified.

## Before distribution

- Review upstream-specific support links and documentation before distribution. Bug reports point to this fork.
- Publish the Mozilla-signed v0.9.4 XPI with its SHA-256; keep the add-on ID stable in future versions.
- Implement and test a fork-owned update mechanism; do not restore upstream URLs or the old workflow's direct commits to `main`.
- Update the install guide, versioning, release notes, privacy declarations and data handling disclosures to match actual behavior.
- Test real Firefox in an isolated profile: site permissions, network authentication, Twitch and Kick UI, chat, points, restart and update. Test redemption only with informed consent.
- Merge or cherry-pick upstream changes on a feature branch and rerun Firefox checks for each release.

The original MIT copyright and third-party license files remain in the repository.
