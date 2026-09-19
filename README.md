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
