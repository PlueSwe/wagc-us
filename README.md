# WAGC.us redesign

Source snapshot of the redesigned World Amateur Golfers Championship site, built on WordPress + Divi5.
Each page is implemented as a single self-contained `divi/code` module (inline `<style>`, HTML, and `<script>`), which is why every file here is a standalone HTML fragment rather than templated partials.

Live staging site: https://wagc.techcareer.se/

## Structure

- `pages/home.html` — homepage (hero slideshow, news ticker, stats, upcoming tournaments teaser)
- `pages/tournaments.html` — full tournament schedule with live registration status pulled from GolfGenius
- `pages/about-wagc.html` — About WAGC page (history, format, notable supporters, Team USA)
- `pages/tournaments/*.html` — one detail page per upcoming tournament, each with registration status, entry fees, and a direct GolfGenius register link

## Notes

- The shared header (topbar, main nav, news ticker) and footer CTA are duplicated across every page file, matching how the live Divi code modules are actually stored (no shared template layer in the CMS).
- The news ticker aggregates live RSS feeds from USGA, GOLF.com, PGA Tour, LPGA, Golf Channel, Golf Digest, Golfweek, DP World Tour, and The R&A via a client-side CORS proxy.
- Tournament registration status/close-times and entry fees are sourced from GolfGenius's internal API and are a point-in-time snapshot, not live-synced.
