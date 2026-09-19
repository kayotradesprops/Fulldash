# Trading Workspace — Combined Vercel App

Single Vercel project containing the Home dashboard, Analysis Journal, Trade Tracker, Statistics, customization, Supabase auth/storage, and a free FinanceCalendar.com-powered U.S. economic calendar.

## Deploy
Upload this folder/ZIP to one Vercel project. No build command is required. The economic calendar needs **no API key or paid subscription**.

## Free economic calendar
The serverless endpoint at `/api/economic-calendar.js` requests the FinanceCalendar.com calendar feed and caches it through Vercel. FinanceCalendar.com documents the feed as free for commercial use with attribution, no API key, open CORS, and consensus/actual/prior fields. A visible FinanceCalendar.com attribution link is included under the calendar as required by the provider.

The dashboard displays USD-focused releases with Actual / Consensus / Previous and converts event times to the selected U.S. timezone. Consensus is normally populated close to the release when the source has it; events without consensus remain blank/neutral rather than inventing a forecast.

The Bullish / Bearish / Neutral column is our rule-based **USD surprise heuristic**, not a field supplied by FinanceCalendar.com and not a trading signal. It compares Actual vs Consensus and applies indicator-specific direction rules. Ambiguous/context-dependent events remain Neutral.

## Supabase
The existing Supabase project URL and publishable browser key remain configured in the HTML files. Run `OPTIONAL-PREFERENCES.sql` once if you want appearance preferences synced across devices.

## Daily calendar behavior
The Home calendar now requests only the current date in the user's selected U.S. timezone and displays that date above the table. It no longer mixes future events into today's view. If the selected day has no U.S. releases (or none match the enabled impact filters), the calendar displays: **“No news day, goodluck trader”**.


## v3 appearance + calendar fixes
- Calendar shows the current date in the selected U.S. timezone and requests only that date.
- True empty calendar days show: `No news day, goodluck trader`.
- Impact filters no longer mislabel a filtered list as a no-news day.
- Sidebar, economic calendar, and calendar adjustment controls blend into the page background while retaining neutral grey/black borders.
- Interface Box Color now controls the grey input/control surfaces throughout the workspace and journal frames.
- Typography preferences are scoped to user-authored journal text rather than navigation/menu text, and sync into both journal frames.


## V4 appearance note
The Analysis Journal and Trade Tracker keep their original dark journal backgrounds for visual distinction. Workspace background customization still applies to the main shell/sidebar/calendar, while interface-control colors and user-authored journal typography continue to sync into the journals.
