# Trip app (generic, no trip data inside)

Files in this folder go to the web host. Your plan stays OUT of it.

- `index.html` - the whole app
- `sw.js` - offline cache
- `plan.example.csv` - sample file showing the columns

## Your plan (private)
Keep your plan CSV (e.g. `japan-2026.csv`) in a separate private place (private GitHub repo, iCloud, email to yourself). Never put it in this folder.

## Load the plan on the iPhone
1. Send `japan-2026.csv` to the phone (AirDrop, iCloud Drive, or email to yourself and save to Files).
2. Open the app icon -> "Загрузить план" -> choose the file (or paste its text).
3. The plan is stored on the phone only. It works offline afterwards.
4. Change the plan: edit the CSV on a computer, send it again, then "Заменить файл" at the bottom of the calendar.

## CSV format (UTF-8, one row per day)
Required: `day` (YYYY-MM-DD), `city`, `title`. Optional: `hotel`, `hotel_map`, `food`,
`m_/d_/e_` + `text`, `from`, `to`, `mode` (morning / day / evening; mode = transit|walking|driving),
`ticket`, `price`, `buy`, `note`. Locations are built automatically from consecutive days with the same city + hotel.

## Update the app code
Re-upload this folder to Netlify (Deploys -> drag folder). Change `trip-v1` to `trip-v2` in `sw.js` so phones refresh.

3. Add it to the home screen:
   - **iPhone (Safari):** Share → Add to Home Screen.
   - **Android (Chrome):** ⋮ → Add to Home screen / Install app.
4. Test offline: switch on airplane mode and open the icon. Google Maps buttons still need internet or downloaded offline maps.

Without hosting you can also just open `index.html` from the Files app. It works, but there is no offline cache or home-screen icon.
