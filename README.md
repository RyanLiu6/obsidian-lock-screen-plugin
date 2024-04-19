# Obsidian Lock Screen Plugin

Adds lock screen functionality to Obsidian. _This is a UI-only feature; no actual filesystem encryption is taking place._

## Fork Details

Credits to [Eric Biewener](https://github.com/ericbiewener), who developed the [original plugin](https://github.com/ericbiewener/obsidian-lock-screen-plugin).

I started using Obsidian recently and was looking for a plugin like this to give my Vault some privacy. As the original is no longer under active development, this fork was created to fit my own preferences.

## Features

-   Lock screen is shown when Vault is initially opened or whenever you are not active on your Vault

    -   This can be triggered instantly with a keyboard shortcut (configurable within Settings -> Hotkeys) or command palette
    -   On Desktop, this happens when the window loses focus (with configurable delay)
    -   On Mobile, this happens when interaction stops (with configurable delay), per Eric:
        > "This is a workaround for sensing when the app has been backgrounded until Obsidian's API can notify plugins about app backgrounding."

-   Lock screen is now an image instead of a blank page with password input

    -   Images are updated daily, using [this](https://github.com/TimothyYe/bing-wallpaper) API endpoint.
    -   Default resolution and region is 1920x1080 and en-US, but can be configured in Plugin Settings.
    -   For Mobile, this image is cropped to be 9:16 aspect ratio to better fit the device.
        -   If you have an unusual device, aspect ratio can be configured in Plugin Settings.

-   Authentication management has been updated:
    -   While this Plugin is an UI-only feature and does not encrypt any files, a strong password is still suggested. Hence, a note is included to encourage the usage of a Password Manager like [Bitwarden](https://bitwarden.com/) or [1Password](https://1password.com/) to generate and store their passwords.
    -   Once the password field is set, it cannot be "unset" or left blank. If left blank, it'll default back to the previously set password.
    -   A Passcode option is added so users who do not wish to use passwords can use a passcode. This will be a 6 digit passcode.

### Using Biometric Unlock (FaceID, Face-Unlock, etc)

Unfortunately, due to how plugins are implemented for Obsidian, I am not able to access system-built features for iOS or Android to use existing Biometric unlock to set up lock screen via this plugin. This would be a core plugin that Obsidian has to build for their individual apps, and is not something I can control. Sorry!
