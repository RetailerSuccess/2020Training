# Store Training Tracker

A one-page web app for filtering the **Advocate Report Export** by store address.
Load the daily `.xlsx` (or a `.csv`) and see, store by store, which advocates have
finished which trainings.

**Your data never leaves your browser.** The file is read on your computer and is
not uploaded anywhere or stored in this repository, so the repo can be public.

## Features
- Store list with address search, completion % and incomplete counts
- Sort by address, most incomplete, lowest completion or most advocates
- Filter by training, advocate name/email, and status (has incomplete / fully complete)
- Per-store grid: every advocate x every training (✓ complete, ✗ incomplete)
- "Incomplete by training" summary across all stores shown
- Export the filtered rows to CSV (e.g. only incomplete trainings for one store)
- Copy the emails of advocates at a store who still have trainings to finish
- Optional "Remember on this device" so the last file reloads automatically (saved in that browser only)

## Required columns
`Door Name`, `Advocate Name`, `Training`, `Status`. Optional: `SFID`, `Dealer Name`, `Email Address`.
The store address is taken from `Door Name` (e.g. `20/20 Mobile Inc 1002 E Amarillo` becomes `1002 E Amarillo`).
A status starting with "Complete" counts as complete; anything else counts as incomplete.

## Publish on GitHub Pages
1. Create a new repository on GitHub (e.g. `store-training-tracker`).
2. Upload `index.html`, `README.md`, `.gitignore` and `sample-data.csv` (**Add file → Upload files**), then commit.
3. Go to **Settings → Pages**. Under *Build and deployment*, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
4. After a minute the site is live at `https://<your-username>.github.io/store-training-tracker/`.

To try it out, load `sample-data.csv` (fictional data).

## Use it locally
Double-click `index.html` to open it in a browser. You need an internet connection the first
time, because the spreadsheet reader (SheetJS) loads from its CDN.

## Privacy
- Don't commit the real export to the repo. `.gitignore` blocks `.xlsx` files to help prevent it.
- GitHub Pages sites are public, but the site holds no data. Each person loads their own file.
