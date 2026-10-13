# IntroDB

A Stremio Enhanced plugin that finds intro, recap, and end-credit timestamps from [introdb.app](https://introdb.app). It marks available ranges on the seek bar and shows a button to skip the active segment.

## Requirements

- Stremio Enhanced with its JavaScript plugin support enabled.
- Playback metadata with an IMDb ID. Titles identified only by another ID are not supported by the IntroDB API.
- A network connection to `api.introdb.app`.

No API key is needed.

## Install

1. Open the JavaScript plugin manager in Stremio Enhanced.
2. Add or import [`introdb.plugin.js`](introdb.plugin.js) as a plugin and enable it.
3. Start a movie or TV episode. When matching segment data exists, its ranges appear on the seek bar and the relevant skip button appears during playback.

## Settings

Open the plugin settings in Stremio Enhanced to configure:

| Setting | Description |
| --- | --- |
| Button Theme | Choose the default or glass skip-button style. |
| Show Intro Button | Show or hide the intro skip button. |
| Show Recap Button | Show or hide the recap skip button. |
| Show Credits Button | Show or hide the end-credit skip button. |
| Anonymous usage reporting | Enable or disable anonymous feature usage events. Enabled by default. |

The plugin maps IntroDB's `outro` range to the **Skip Credits** button. Post-credit scenes are not skipped.

## Data and privacy

For supported playback, the plugin requests segment data from `https://api.introdb.app/segments`, using the IMDb ID and, for TV, the season and episode. Playback titles and IDs are not included in analytics events. If anonymous usage reporting is enabled, the plugin sends events such as plugin start, segment availability, and skip-button display or use to the configured analytics service. Disable **Anonymous usage reporting** in plugin settings to opt out.

Segment availability depends on community data. If IntroDB has no matching entry, no skip button is shown.

## Metadata

- Name: IntroDB
- Author: akar1881
- Version: 1.0.0
