# Hospital Marketing Compass

A marketing analytics app for private hospitals. It reads monthly summary numbers and shows:

- **Overview**: visits, new patients, revenue, capacity used, no-show rate, inquiry conversion, campaign return, compared with the previous period.
- **Problems**: automatic flags for idle capacity, falling demand, high no-shows, weak inquiry conversion, payer or source concentration, and losing campaigns, each with an estimated monthly impact and suggested marketing actions.
- **Target audience**: segments (department × age group × area) ranked by value per patient, growth and free capacity.
- **Campaigns**: return per riyal and cost per booking by channel and by campaign.
- **Action plan**: a simple to-do list with owner, due date and status.
- **Data & settings**: Excel template download, Excel/CSV upload, adjustable thresholds.

It installs as an app (PWA) on phones and computers and works offline after the first visit.

## Privacy

- All data stays **in the browser on the device** where it was uploaded (localStorage). Nothing is sent to any server.
- Upload **grouped numbers only**. Never put patient names, file numbers, national IDs or phone numbers in the Excel file.
- `.gitignore` blocks `.xlsx`, `.xls` and `.csv` files so hospital data is not committed to the repository by mistake.

## Publish on GitHub Pages

1. Create a new repository on GitHub, e.g. `hospital-marketing-compass`. Use **Private** if you do not want the code public (GitHub Pages on private repos needs a paid plan; otherwise use Public. The data is never in the repo either way).
2. Upload every file and folder in this directory to the repository root (`index.html` must be at the root). On github.com: **Add file → Upload files**, drag the contents in, then **Commit changes**.
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to *Deploy from a branch*, branch `main`, folder `/ (root)`, then **Save**.
4. After 1–2 minutes the app is live at `https://<your-username>.github.io/hospital-marketing-compass/`.

## Install as an app

- **iPhone / iPad (Safari)**: open the link → Share button → **Add to Home Screen**.
- **Android (Chrome)**: open the link → menu ⋮ → **Install app** (or *Add to Home screen*).
- **Windows / Mac (Chrome or Edge)**: open the link → install icon in the address bar.

## Load the hospital's data

1. Open **Data & settings** → **Download Excel template**.
2. Fill the four sheets (`Departments_Monthly`, `Sources_Monthly`, `Segments`, `Campaigns`). Keep the column names. Months as `YYYY-MM`.
3. Upload the file with **Import into: Auto**. The header badge changes from *Demo data* to *Your data*.
4. Adjust thresholds under **Settings and thresholds** to match the hospital's targets.

Data is per device and per browser. To use it on another device, upload the same file there.

## Updating the app

After changing any file, open `sw.js` and bump `VERSION` (e.g. `hmc-v1.0.1`), then commit. Installed copies pick up the new version on the next launch.

## Notes

- The **AI advisor** tab works only when the app is opened inside Claude. On GitHub Pages it shows a notice; every other feature works.
- Impact figures are estimates for ranking problems, not forecasts.

## Third-party libraries

Bundled in `vendor/` so the app works offline:

- [Chart.js](https://www.chartjs.org/) 4.4.1, MIT License (`vendor/LICENSE-chartjs.md`)
- [SheetJS Community Edition](https://sheetjs.com/) 0.18.5, Apache License 2.0 (`vendor/LICENSE-sheetjs.txt`)
