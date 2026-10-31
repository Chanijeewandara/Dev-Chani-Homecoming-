# Dev & Chani · Homecoming invitation

Folder layout

```
apps-script/rsvp-database.gs   -> Google Sheet + private replies page (paste into Apps Script)
photos/                        -> couple1.jpg, couple2.jpg (see PUT-PHOTOS-HERE.txt)
index.html                     -> the invitation guests open
links.html                     -> YOUR page: makes a personal link + WhatsApp message for each guest
README.md                      -> this file
```

## 1. Photos
Put two photos in `photos/` named exactly `couple1.jpg` and `couple2.jpg` (under ~400 KB each).
If a photo is missing the page shows the "D & C" monogram instead, so nothing breaks.

## 2. RSVP database (5 minutes)
1. Go to sheets.new, create a Google Sheet.
2. Extensions > Apps Script. Delete the sample code, paste all of `apps-script/rsvp-database.gs`.
3. Change `ADMIN_KEY` to your own secret word (optional: set `NOTIFY_EMAIL`).
4. Deploy > New deployment > Web app. Execute as: **Me**. Who has access: **Anyone**. Copy the URL ending in `/exec`.
5. Open `index.html`, find `var RSVP_ENDPOINT = "";` and paste the URL between the quotes.

To view replies: open the Sheet, or `YOUR_WEB_APP_URL?key=YOUR_ADMIN_KEY`.
After changing the script later: Deploy > Manage deployments > Edit > New version.

## 3. Put it online (GitHub Pages)
Upload `index.html`, `links.html` and the `photos` folder to a GitHub repository, then
Settings > Pages > Deploy from branch > main. Your address will look like
`https://your-name.github.io/your-repo/`.
The `apps-script` folder does not need to be uploaded (it lives in Google).

## 4. Personal links for guests
Open `links.html` from your hosted site, type guest names (one per line, optional `, phone`),
press **Make links**. Each guest gets `index.html?to=Name`, so the invitation greets them by name
and their reply is saved with that name. Use the WhatsApp button to send.
Keep the `links.html` address to yourself; it is not linked from the invitation.

## Notes
- The envelope opens by itself after about 4 seconds; guests can also tap the seal.
- If the RSVP address is empty, guests are offered a WhatsApp reply instead, so nothing is lost.
- Fonts load from Google Fonts; with no internet the page falls back to a serif font.
