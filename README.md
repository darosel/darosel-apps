# darosel-apps

Shared app list for the "More apps from Darosel.Apps" page in every Darosel.Apps app.

Served by GitHub Pages at **https://darosel.github.io/darosel-apps/apps.json**.

## Format

```json
{
  "schema": 1,
  "apps": [
    {
      "id": "weekspark",                     // stable id; an app never lists its own id
      "name": "WeekSpark",                   // fallback title
      "appStoreName": "WeekSpark: Weekly Planner",
      "title":    { "en": "...", "sv": "..." },   // per-language card title, falls back to "en", then "name"
      "subtitle": { "en": "...", "sv": "..." },   // one short line, same fallback
      "icon": "icons/weekspark.png",         // path relative to apps.json (512x512 PNG)
      "appStoreId": "6809785269",
      "url": "https://apps.apple.com/app/id6809785269",
      "live": true                           // only live apps are shown
    }
  ]
}
```

Language codes: en, sv, fi, nb, da, de, fr, es, pt, id, zh, ja, ko, hi, ar.

## Publishing a new app

1. Add a 512x512 PNG to `icons/`.
2. Add an entry to `apps.json` with `"live": false`, commit and push.
3. When the app is approved in the App Store: set `"live": true`, fill in `appStoreId` and `url`, push.
   Every app picks up the change the next time the More apps page is opened (each app also ships a
   built-in copy of the list for when there is no network).

Keep `schema` at 1 unless the format changes in a way older apps can't read; apps ignore unknown fields.
