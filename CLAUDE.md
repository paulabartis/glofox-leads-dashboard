# Glofox Lead Quality Dashboard

## What this is
Interactive dashboard showing Glofox SMB MQL volume, workability rates, NW reasons,
rep scorecard, and workable pool attributes. Public GitHub Pages site.

## URLs
- Live: https://paulabartis.github.io/glofox-leads-dashboard/
- Sheet: https://docs.google.com/spreadsheets/d/167c-qQ06tSHDeF2oOQ5ejJYMLPpBE69yVBdwsvzRaaY

## Data flow
1. `python3 scripts/sync_sf_leads_to_sheet.py` → pulls SF reports → writes to Google Sheet
2. `leads-dashboard/index.html` → reads Sheet CSV at runtime → all filtering in browser

## To refresh data
```bash
python3 scripts/sync_sf_leads_to_sheet.py
```
Then click Refresh in the dashboard, or push index.html to GitHub Pages.

## Adding a new month
1. Dupe Lead + Contact SF reports, set date filter to new month
2. Add the 2 new report IDs to `MONTHLY_REPORTS` in `scripts/sync_sf_leads_to_sheet.py`
3. Re-run the sync script

## SF Report IDs (2026)
| Month | Lead Report ID         | Contact Report ID      |
|-------|------------------------|------------------------|
| Jan   | 00OUz00000IGJ4MMAX     | 00OUz00000IGO41MAH     |
| Feb   | 00OUz00000IGNPhMAP     | 00OUz00000IGO8rMAH     |
| Mar   | 00OUz00000IGNfpMAH     | 00OUz00000IGOFJMA5     |
| Apr   | 00OUz00000IGNkfMAH     | 00OUz00000IGPPtMAP     |

## Sheet setup requirements
- Share with `glofox-mcp@glofoxmcp.iam.gserviceaccount.com` (Editor) — for Python writes
- Set to "Anyone with the link can view" — for dashboard browser reads

## GitHub push
```bash
git remote set-url origin "https://paulabartis:$GLOFOX_GITHUB_PAT@github.com/paulabartis/glofox-leads-dashboard.git"
git push origin main
git remote set-url origin "https://github.com/paulabartis/glofox-leads-dashboard.git"
```
