# MMM-RNV

<p style="text-align: center">
    <a href="https://choosealicense.com/licenses/mit"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
</p>

This module is an extention for the [MagicMirror](https://github.com/MichMich/MagicMirror).

The module is based on the work of [yawnsde](https://github.com/yawnsde/MMM-RNV) but uses the new Data Hub API.

The module monitors a given station in the RNV traffic network and shows by default the 10 upcoming departures with its destination, type and delay. It also shows additional information like the platform.
Either a valid API key or credentials are required, which can be requested here for free: https://opendata.rnv-online.de/datahub-api

## Installation

Open a terminal session, navigate to your MagicMirror's `modules` folder and execute `git clone https://github.com/jupadin/MMM-RNV.git`, such that a new folder called MMM-RNV will be created.

Navigate inside the folder and execute `npm install` to install all dependencies.

Activate the module by adding it to the `config.js` file of the MagicMirror as shown below.

The ID of your specific station can be found here: https://rnvopendataportalpublic.blob.core.windows.net/public/openDataPortal/liniengruppen_mit_haltestellenreferenz.json


The table below lists all possible configuration options.

## Using the module
````javascript
    modules: [
        {
            module: 'MMM-RNV',
            header: 'RNV Abfahrstmonitor',
            position: 'top_right',
            config: {
                apiKey: 'Enter your apiKey here',
                // or
                clientID: 'Enter your @clientID here',
                tenantID: 'Enter your @tenantID here',
                clientSecret: 'Enter your @clientSecret here',
                resourceID: 'Enter your @resource here',
            }
        }
    ]
````

## Configuration options

The following configuration options can be set and/or changed:

### Authentication

| Option | Type | Default | Description | Given names from RNV |
| ---- | ---- | ---- | ---- | ---- |
| `apiKey` | `string` | `""` | Your personal API Key | - |
| or |
| `clientID`| `string` | `""` | Your client ID | @clientID |
| `tenantID` | `string` | `""`| Your tenant ID | @tenantID |
| `clientSecret` | `string` | `""` | Your client secret | @clientSecret |
| `resourceID`| `string` | `""` | Your resourceID | @resource |

The remaining data and credentials, provided by the RNV, is not needed.

### Module

| Option | Type | Default | Description |
| ---- | ---- | ---- | ---- |
| `header` | `string` | `"RNV Abfahrtsmonitor"` | Header which will be displayed |
| `stationID` | `string` | `"2417"` | ID for Mannheim HBF |
| `numJourneys` | `string` | `"10"` | Number of shown departures. |
| `updateInterval` | `string` | `"60000"` | How often the table shall be updated [milliseconds] (1 minute) |
| `animationSpeed` | `string` | `"2000"`| Animation speed to fade in the module on startup [milliseconds] (2 seconds) |
| `coloredLines` | `boolean` | `true` | Display colored line numbers |
| `showLineIcons` | `boolean` | `true` | Show icons next to line numbers |
| `useColorForRealTimeInfo` | `boolean` | `true` | Display colored real time information |
| `showTableHeader` | `boolean` | `true` | Show table header |
| `showTableHeaderAsSymbols` | `boolean` | `false` | Show icons instead of header titles |
| `focus_on` | `array` | `[]` | Array of integers, to highlight specific line numbers |