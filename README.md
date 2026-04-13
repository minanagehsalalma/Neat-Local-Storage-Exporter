# Neat LocalStorage Exporter

Browser-side helper for exporting and re-importing `localStorage` data during debugging, QA, migration, and repro workflows.

![image](https://github.com/user-attachments/assets/b9c4f384-60d9-43b0-b874-4b27a7d04355)

## Why this exists

When you need to reproduce a bug, move browser state between environments, or inspect app storage without copying keys one by one, this script gives you a quick in-page utility.

It runs directly in the browser console and opens a small overlay that can:

- export every `localStorage` key from the current page origin as JSON
- copy the exported JSON to your clipboard
- import a previously exported JSON payload into the current page origin
- clear `localStorage` with an explicit confirmation step

## Good fit

- QA and bug reproduction
- moving non-sensitive test state between local, staging, and preview environments
- validating how a frontend behaves with a known `localStorage` payload
- inspecting browser-side state during development

## How it works

The script only works in the page context where you run it. If you want to move state between two apps or environments, run it once on the source page to export the JSON, then run it again on the destination page to import the JSON there.

![image](https://github.com/user-attachments/assets/0b7618e9-b0b1-4356-89fd-977ae4357e3d)

## Usage

1. Open the target page in your browser.
2. Open DevTools.
3. Paste the contents of `copy_localstorage.js` into the console.
4. Use the overlay to export or import data.

## Notes

- This is designed for development and troubleshooting workflows.
- Only use it on apps and environments you own or are authorized to test.
- The exported payload is plain JSON, so treat it carefully if it contains sensitive application state.
