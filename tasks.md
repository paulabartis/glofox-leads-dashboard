# Lead Quality Dashboard — Tasks

## Status: In Progress

---

## ✅ Done
- Sync script (`scripts/sync_sf_leads_to_sheet.py`) — pulls 8 SF monthly reports → Google Sheet
- Dashboard HTML (`leads-dashboard/index.html`) — reads Sheet live, all filters in browser
- Sections: KPI strip, trend chart, channel/region breakdown, NW reasons, rep scorecard, workable pool attributes
- Filter bar: Monthly/Weekly toggle, period buttons (YTD/Jan/Feb/Mar/Apr), Channel/Region/Rep dropdowns
- Refresh button

---

## 🔲 Setup (user action required)
- [ ] Share sheet with `glofox-mcp@glofoxmcp.iam.gserviceaccount.com` (Editor)
- [ ] Set sheet to "Anyone with the link can view"
- [ ] Create GitHub repo `paulabartis/glofox-leads-dashboard`
- [ ] Enable GitHub Pages (Settings → Pages → Deploy from main branch)
- [ ] Run `python3 scripts/sync_sf_leads_to_sheet.py` for first data load
- [ ] Push to GitHub Pages

---

## 🔲 Next / Backlog
- [ ] WoW / MoM / QoQ delta badges on KPI cards (vs prior period)
- [ ] Channel drill-down within NW reasons (filter NW table by channel)
- [ ] Rep drill-through: click rep row → filter all sections to that rep
- [ ] "Workable but not sales-ready" cohort tag once Lead Status values are confirmed
- [ ] Add May 2026 reports when month closes
- [ ] Mobile layout polish
