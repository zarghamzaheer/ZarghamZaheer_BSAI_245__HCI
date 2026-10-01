# ZarghamZaheer_BSAI_245__HCI
Hci project
# Usability Tracker

A lightweight JavaScript tool that records how visitors interact with a web page, so you can see where they click, where they move the mouse, and how far they scroll. It was built as a student project to learn about web analytics and usability testing.

## Features

- **Click tracking:** saves the position, element type, ID, class and short text of every click
- **Mouse movement tracking:** samples the cursor position every 250 ms to avoid slowing the page
- **Scroll depth tracking:** records the furthest point of the page a visitor reaches, as a percentage
- **Privacy protection:** never records text from input, textarea or select fields
- **Heatmap overlay:** draws red dots for clicks and faint blue dots for mouse movement
- **Data export:** download the session data as a JSON file
- **Session summary:** shows total clicks, mouse moves, scroll depth and session length

## How It Works

The script runs in the visitor's browser and listens for click, mousemove and scroll events. Each event is stored in memory with a session ID, a timestamp and its coordinates. Everything is exposed through a global `UsabilityTracker` object.

## Usage

1. Add the script to your page:
```html
   <script src="tracker.js"></script>
```
2. Open the page, then click, move the mouse and scroll.
3. Open the browser console (F12) and try:
```javascript
   UsabilityTracker.getSummary();     // session statistics
   UsabilityTracker.renderHeatmap();  // show dots on the page
   UsabilityTracker.clearOverlay();   // remove the dots
   UsabilityTracker.downloadJSON();   // save the data as a file
```

## Configuration

Settings are in the `CONFIG` object at the top of the script:

| Setting | Default | Description |
|---|---|---|
| `mouseMoveSampleMs` | 250 | How often the mouse position is saved |
| `maxLogs` | 5000 | Maximum number of events stored |
| `maxTextLength` | 30 | Maximum characters saved from clicked text |
| `logToConsole` | true | Print events in the console |
| `ignoreInputs` | true | Hide text from form fields |

## Limitations

- Data is stored in memory only and is lost when the page is refreshed
- The heatmap shows individual points rather than blended color gradients
- There is no server, so data is not sent anywhere automatically

## Future Improvements

- Send data to a backend or database
- Add a gradient-style heatmap
- Track rage clicks and dead clicks
- Build a dashboard to view results

## Privacy Notice

This tool tracks user behavior. If you use it on a real website, inform your visitors and follow privacy laws such as GDPR.

## License

MIT License. Free to use for learning and projects.
