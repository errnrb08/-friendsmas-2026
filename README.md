# Friendsmas 2026 website starter

## Event settings included
- Friday, December 18, 2026 at 7:00 PM
- Mi Casa
- RSVP deadline: December 12, 2026
- Funny Christmas chaos visual theme
- 16 two-player beer pong teams maximum
- Double-elimination bracket, randomized after registration closes

## Important
`index.html` is the designed website, but it is **not live yet**. Do not share it as a registration link until you host it and connect the registration backend. The QR code must be made from the final public website URL.

## Free setup path
1. Create a blank Google Sheet named `Friendsmas 2026 RSVPs`.
2. In that Sheet, open Extensions → Apps Script.
3. Replace the starter code with the contents of `Code.gs`.
4. In Apps Script, open Project Settings → Script Properties and add:
   - Property: `ADMIN_KEY`
   - Value: a long private organizer password. Do not share it with guests.
5. Deploy → New deployment → Web app:
   - Execute as: Me
   - Who has access: Anyone
   - Deploy and copy the Web app URL.
6. In `index.html`, replace `PASTE_YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE` with that URL.
7. Publish `index.html` using GitHub Pages (free static hosting) or another static host.
8. In Apps Script, run `onOpen` once and authorize it. Reload the Google Sheet. Use Friendsmas → Generate random bracket after registration closes. The `Bracket` tab stores the draw.
9. Create a QR code from the final public website URL and share the QR image and clickable URL with guests.

## Sheets created automatically
- `RSVPs`: all yes/no responses
- `Teams`: tournament entries (maximum 16)
- `Bracket`: randomized double-elimination bracket draw and later-round placeholders

## Current implementation notes
- The Apps Script endpoint enforces the 16-team cap while submissions are processed under a lock.
- The organizer generates the randomized bracket manually after the December 12 deadline. The public bracket layout still needs a proper winners/losers bracket engine before live results can be tracked.
- The site currently uses a submission confirmation message. For a production launch, test the Apps Script deployment with a few test RSVPs and confirm the sheet rows arrive before distributing the link.
- The bracket is stored in the spreadsheet. The public bracket display endpoint can be expanded in a later pass to publish the completed bracket and match results on the website.
