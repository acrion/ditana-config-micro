This Arch package provides a preconfigured setup of the [micro](https://github.com/zyedidia/micro) text editor for [Ditana GNU/Linux](https://ditana.org), optimizing it for a seamless and efficient terminal-based editing experience.

## Description

The micro editor, mirroring the user interface of GUI editors, supports shortcuts and mouse interactions, offering a familiar editing environment within the terminal. This package installs micro with custom configurations and sets it as the default editor in Ditana GNU/Linux.

## Features

- Preconfigured micro editor optimized for Ditana GNU/Linux
- Set as the default system editor
- Custom desktop entry for proper integration with XFCE
- Enhanced settings for an improved user experience

## Configurations

The micro editor is configured with the following settings:

- Display Git diff indicators next to lines
- Save and restore cursor position when opening files
- Retain undo history even after closing and reopening files
- Use spaces instead of tabs for indentation
- Use a subtle visual indicator for indentations
- Automatically reuse existing superuser privileges when saving, if possible
- Automatically create missing parent directories when saving
- Highlight all instances of searched text after a successful search
- Open multiple files side-by-side in vertical splits
- Wrap long lines at word boundaries (when soft wrap is enabled)
- Display a scroll bar

**Note:** By default, micro does not remove trailing whitespace. If you wish to enable automatic removal of trailing whitespace, you can add `"rmtrailingws": true` to your `~/.config/micro/settings.json` file. Be cautious when enabling this setting, as it may interfere with Markdown syntax where trailing spaces have a distinct meaning.

A special `micro.desktop` file is installed to override the default `micro.desktop`. This is needed to support right-clicking a file under the XFCE desktop environment. It uses `exo-open --launch TerminalEmulator micro %F`.

## Installation

This package is available in the Ditana GNU/Linux Arch repository and is installed by default.

## Usage

After installation, micro will be set as the default editor. You can open files in micro using:

- **Terminal:** `micro filename`
- **File Manager:** Right-click on a file and select "Open with micro"

## Dependencies

- [micro](https://github.com/zyedidia/micro)
- [xclip](https://github.com/astrand/xclip)
- [exo](https://docs.xfce.org/xfce/exo/start)

## Support

For issues, feature requests, or contributions related to the Ditana configuration of micro, please use the GitHub issue tracker or submit a pull request.

---

This Arch package is part of the [Ditana GNU/Linux](https://ditana.org) project, aiming to provide efficient and user-friendly tools for system management and text editing.
