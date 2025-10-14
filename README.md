# jellyfin-plugin-moviecontentfilter

GitHub mirror for the Jellyfin plugin for Movie Content Filter, to allow users to skip objectionable content in videos, based on their preferences.

[Project Source Code](https://codeberg.org/jacobwillden/jellyfin-plugin-moviecontentfilter)

[Movie Content Filter Website](https://www.moviecontentfilter.com/)

## General Information

This project is in very early development right now, and there are many features to add (and some bugs to fix). It is built on the source code from the open-source VideoSkip browser extension and the open-source Intro Skipper plugin for Jellyfin (linked below). The source code is freely available to copy and build on, released under the GNU General Public License (GNU GPL), version 3. (I'm currently figuring out if I can distribute the plugin under version 3 or later.)

`SPDX-License-Identifier: GPL-3.0-only`

[VideoSkip Source Code Link](https://github.com/fruiz500/VideoSkip-extension/)

[Intro Skipper Source Code Link](https://github.com/ConfusedPolarBear/intro-skipper)

## Building from Source

### Prerequisites

- [.NET 6.0 SDK](https://dotnet.microsoft.com/download/dotnet/6.0) or later

### Build Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/NiceneNerd/jellyfin-plugin-moviecontentfilter.git
   cd jellyfin-plugin-moviecontentfilter
   ```

2. Build the plugin:
   ```bash
   cd Jellyfin.Plugin.MovieContentFilter
   dotnet build -c Release
   ```

   Or, to create a publish package with all dependencies:
   ```bash
   dotnet publish -c Release
   ```

   **Note**: If you encounter a build error about package vulnerabilities (NU1903), you can bypass the warnings-as-errors check using:
   ```bash
   dotnet build -c Release -p:TreatWarningsAsErrors=false
   ```
   or
   ```bash
   dotnet publish -c Release -p:TreatWarningsAsErrors=false
   ```

3. The build output will be located in:
   - Build: `Jellyfin.Plugin.MovieContentFilter/bin/Release/net6.0/`
   - Publish: `Jellyfin.Plugin.MovieContentFilter/bin/Release/net6.0/publish/`

### Installing the Built Plugin

After building, copy the plugin DLL and its dependencies to your Jellyfin plugins directory:

- **Linux**: `/var/lib/jellyfin/plugins/MovieContentFilter/`
- **Windows**: `%AppData%\Jellyfin\Server\plugins\MovieContentFilter\`
- **macOS**: `~/.local/share/jellyfin/plugins/MovieContentFilter/`

If using the publish output, copy all files from the `publish/` directory. If using the build output, you'll need to ensure all required dependencies are present.

After copying the files, restart your Jellyfin server for the plugin to load.

## Installation Instructions

(Work in Progress)

## How to Use

(Work in Progress)

## Legal

The plugin does not alter video files at all, but instead lets "users choose to see or not to see parts of the content, and the [plugin] remembers their choice" (quoted from the [Read Me file for the VideoSkip extension](https://github.com/fruiz500/VideoSkip-extension/blob/master/README.md), which extension's code this plugin is built on). It also does not enable unauthorized access to video files.

The video content that our plugin can filter belongs to its respective copyright holders. We claim no affliation or endorsement from any of these copyright holders.

Notice to All Users: When watching a motion picture (referring to a movie, television show, etc) using this plugin, the performance of the motion picture is altered from the performance intended by the director or copyright holder of the motion picture.
