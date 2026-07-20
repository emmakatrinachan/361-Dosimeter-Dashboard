# Dosimeter Tracking Dashboard

Custom public dashboard for ESP32 + AHT20 route exposure tracking.

## Files

- `index.html` - public route exposure dashboard.
- `location.html` - phone GPS uploader page.

## ThingSpeak Channel Fields

Set up the ThingSpeak channel with:

- `field1` - Temperature C
- `field2` - Humidity %
- `field3` - Phone GPS Accuracy m
- `field4` - Device Status, optional

ThingSpeak latitude and longitude are sent separately as `lat` and `long`.

## How To Use

1. Upload this repo to GitHub.
2. Enable GitHub Pages.
3. Open the dashboard:

```text
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

4. Paste your ThingSpeak Channel ID.
5. If the ThingSpeak channel is private, paste your Read API Key.

## Phone Location Upload

Open:

```text
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/location.html
```

Paste the ThingSpeak Write API Key and tap `Start 10 Minute Tracking`.

Do not hardcode the Write API Key into this repo. The write key allows data uploads to your ThingSpeak channel.

## ESP32 Upload

The ESP32 firmware should upload:

- `field1` - temperature in Celsius
- `field2` - relative humidity percent
- `status` - device label

The phone uploader separately uploads:

- `field3` - GPS accuracy in meters
- `lat` - phone latitude
- `long` - phone longitude
- `status` - phone location label

The dashboard matches phone GPS rows with nearby ESP32 sensor rows by timestamp.
