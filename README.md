# GitNotify

A macOS menu-bar app that shows the GitHub pull requests waiting on your review, and your own open PRs, each with its CI, mergeability and reviewer status. It notifies you when something needs you.

This repository only hosts releases; the source is private.

Requires macOS 14 or later and the [GitHub CLI](https://cli.github.com), logged in with `gh auth login`.

## Install

Homebrew:

```sh
brew install --cask mihailupoiu/tap/git-notify
```

Or the install script, which also updates an existing copy:

```sh
curl -fsSL https://github.com/MihaiLupoiu/git-notify-releases/releases/latest/download/install.sh | bash
```

Or by hand: download `GitNotify.zip` from the [latest release](https://github.com/MihaiLupoiu/git-notify-releases/releases/latest), unzip it, move `GitNotify.app` to `/Applications`, then run:

```sh
xattr -dr com.apple.quarantine /Applications/GitNotify.app
```

The app isn't signed with an Apple Developer ID, so macOS refuses to open a downloaded copy until that quarantine flag is removed. Homebrew and the install script do this for you.

If you installed by hand or with the script and want to switch to Homebrew, add `--force`, because Homebrew won't replace an app it didn't install:

```sh
brew install --cask --force mihailupoiu/tap/git-notify
```

## Update

- Homebrew: `brew upgrade --cask git-notify`
- Script: run the install command again.
- By hand: quit GitNotify, then repeat the manual steps with the new zip.

Your settings are kept.

## Uninstall

- Homebrew: `brew uninstall --cask git-notify`, or `brew uninstall --zap --cask git-notify` to also delete your settings.
- Otherwise: quit GitNotify from its menu, then `rm -rf /Applications/GitNotify.app`. To also delete your settings: `rm -rf ~/.config/git-notify ~/Library/Application\ Support/git-notify`.

## Configure

Settings are in the app (menu-bar icon › Settings…) and in `~/.config/git-notify/config.json`, which you can edit by hand. Set your GitHub organizations under **Watched Orgs**.
