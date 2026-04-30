# Lexmark / Xerox · Y Soft — Value Alignment Meeting

Web version of the Value Alignment Meeting deck for Lexmark / Xerox and Y Soft (5/6/26).

## View it

Live site: (not yet published)

## Run locally

```sh
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Layout

- `index.html` — the deck (19 slides; 1920×1080 canvas auto-scales to viewport)
- `styles.css` — shared styles
- `deck-stage.js` — `<deck-stage>` web component
- `assets/team/` — headshots and brand logos
- `assets/` — additional imagery
- `fonts/` — YSoft typeface

## Deck structure

**Main flow:**
1. Title — Value Alignment Meeting · SAFEQ Cloud
2. In the room — meeting team
3. Today's Agenda

**Reference / backup material:**
4. Backup divider
5. Who is Y Soft
6. Hardware and software company
7. Why cloud
8. Market data shifting to the cloud
9. The year of cloud print
10. Three pillars of SAFEQ Cloud
11. Infrastructure savings
12. Five-year print server cost analysis
13. Cloud print at scale
14. Regional data centers
15. Security pillar
16. Why security matters now
17. Defense in depth
18. Security risks in legacy print

**Close:**
19. Thank you

## Controls

- `←` / `→` — previous / next slide
- `Home` / `End` — jump to first / last
- Number keys `1`–`9` — jump to slide
- `F` — toggle fullscreen
- `R` — reset to first slide
