---
id: macos-hide-dock
aliases: []
tags: []
---

# MacOS Hide Dock

We can hack around the macos default dock behavior by using the following command in the terminal:

```bash
defaults write com.apple.dock autohide-delay -float 15; killall Dock
```

This command will set the dock to autohide after 15 seconds. You can adjust the value to your liking, or increase it to something like 1000 to effectively disable the Dock.

To revert to the default behavior, use the following command:

```bash
defaults delete com.apple.dock autohide-delay; killall Dock
```

Source: [Stack Exchange](https://apple.stackexchange.com/a/82084)
