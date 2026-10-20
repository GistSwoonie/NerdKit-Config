# NerdKit-Config

Remote parameter-driven configuration for the **NerdKit** Android application.

## Overview

This repository hosts the live configuration file (`nerdkit-main-config.toml`) consumed by NerdKit to dynamically manage:
* Active and disabled screens across all categories (Measure, Tools, Navigate, Weather, Maps, Travel, Sky, Sensors, Network, Device).
* App launch welcome dialog copy and action links.
* Pro upgrade / sales promotion cards, discount badges, pricing copy, and feature bullets.
* Emergency maintenance banners.
* Minimum supported app version enforcement.
* Official community and documentation links.

## Mobile Editing (How to change settings while traveling)

1. Open the **GitHub Mobile App** on your phone (or browse to [github.com/GistSwoonie/NerdKit-Config](https://github.com/GistSwoonie/NerdKit-Config)).
2. Tap `nerdkit-main-config.toml`.
3. Tap the **Pencil icon (Edit)**.
4. Make your desired adjustments:
   * To disable a screen: set it to `false` (e.g. `quantum_compass = false`).
   * To enable a screen: set it to `true`.
   * To edit promotion text: modify the string inside quotes `"..."`.
5. Tap **Commit changes...** (add a brief message like "Disabled satellite tracker" or "Weekend Pro sale").
6. The updated configuration will be fetched by NerdKit clients automatically.

## Syntax Guidelines

* Format is standard **TOML**.
* Indentation and extra whitespace do not matter.
* Boolean values must be lowercase (`true` or `false`).
* Strings must be surrounded by double quotes (`"text"`).
