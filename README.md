# Double Vision Surf Log

A mobile-first personal surf journal with marine forecast snapshots, manual Surfline entry, surf spot management, session history, a year summary, and a conditions analysis view.

## Publish on Netlify

1. Sign in at https://app.netlify.com/
2. Choose **Add new project → Import an existing project**.
3. Connect GitHub and choose **kristofschlagintweit/double-vision-surf-log**.
4. Set **Production branch** to `main`, **Build command** to blank, and **Publish directory** to `.` (repository root).
5. Deploy. Netlify supplies a public URL and will automatically republish when `main` changes.

The site is a standalone `index.html` file with no build tooling.

## Data collection

- **Open-Meteo** marine and weather models: automatic primary and secondary swell, wind, wave height, modeled sea level and ocean current fields when available. Forecasts are requested for the date/time selected.
- **Surfline:** manual entry for two swell components and tide. Surfline API integration is not present.
- **NOAA NDBC 46087:** not yet automated.
- **Juan de Fuca currents from MarineWeather.net:** not yet automated; Open-Meteo model current is shown separately and is not assumed equivalent to the specific tidal station prediction.
- **Local tide station:** not yet integrated. Open-Meteo sea level is relative to mean sea level and is **not** a chart-datum tide height.

The forecast fetch requires internet access, can fail due to source coverage or date ranges, and should be checked against the original source.

## Data safety and limitations

This is a **prototype**. Logs and spot settings are stored in the current browser's localStorage. They do not sync between phones and computers. Use **Export JSON** in Session History to back up data. Clearing browser storage loses unexported sessions. No authentication, server database, or private account exists yet.

The home page currently uses a text wordmark rather than the user's original uploaded logo. Do not treat surf spot coordinates as surveyed values: the starter spots are approximate.

## Future work

Add the original artwork, cloud data storage, account login, editing existing logs, NOAA 46087 historical readings, verified local tides and current predictions, and Surfline screenshot-assisted entry. Validate regional API availability and attribution/licensing before production use.
