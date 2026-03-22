# Werner Website Design Handoff — 2026-03-22

## Where Things Stand

The website redesign lives in `/Users/heathochroch/werner-website/` (separate repo from Werner-Backbone). The homepage is `demo-ultimate.html` and all subpages have been restyled to match.

### Files Updated (all have new design system applied)
- `demo-ultimate.html` — **homepage** (the main deliverable)
- `about.html`, `fleet.html`, `testimonials.html`, `faq.html`, `contact.html`
- `services/index.html`, `services/wedding.html`, `services/school.html`, `services/corporate.html`
- `quote-widget.html` — standalone quote form (pre-existing, not restyled yet)

### Design System
- **Fonts**: Playfair Display (headings) + Source Sans 3 (body) via Google Fonts
- **Colors**: `--navy: #0B1D3A`, `--gold: #B8965A`, `--cream: #F8F4EE`, `--char: #1C1C1C`
- **Nav**: Navy bar, logo in white pill container, gold "Get a Free Quote" button, demoted "Pay Online"
- **All pages**: Self-contained inline `<style>` (no shared CSS file, no build system)
- **All links**: Home → `/demo-ultimate.html`, Quotes → `/quote-widget.html`
- **When going live**: Rename `demo-ultimate.html` to `index.html`, change all `/demo-ultimate.html` refs to `/`

### Local Dev
```bash
cd /Users/heathochroch/werner-website && python3 -m http.server 8765
# Open http://localhost:8765/demo-ultimate.html
# Use private/incognito tab — browser aggressively caches old versions
```

### Images Added This Session
All in `/Users/heathochroch/werner-website/images/`:
- `hero-valleyforge.webp` — hero background (bus at Valley Forge with arch)
- `bus-franklin-institute.webp` — bus at Franklin Institute (school/education)
- `bus-baseball-stadium.webp` — bus at baseball stadium (athletics)
- `bus-front-quarter.webp` — front quarter detail view
- `bus-medium-angle.webp` — medium angle (fleet preview)
- `bus-side-full.webp` — full side view at Valley Forge
- `bus-snow-hd.webp` — HD snow scene
- `philly-skyline.webp` — aerial Philly skyline (corporate)
- `philly-skyline-bright.webp` — bright Philly skyline (contact page header)
- `philly-bridge-sunset.webp` — Ben Franklin Bridge sunset (tours, final CTA)
- `nyc-skyline.webp` — NYC skyline (special events)
- Source photos came from `/Users/heathochroch/Desktop/Branding/Upscaled photos/` and `/Users/heathochroch/Desktop/Branding/Website Photo Research/`

## OPEN TASKS — What Needs To Be Done Next

### 1. Fix Nav Alignment & Button Styling (PRIORITY)
The nav bar on `demo-ultimate.html` has spacing/alignment issues:
- Phone number `(800) 532-9800` feels asymmetrically placed
- "Get a Free Quote" button is oversized and too blocky
- **Goal**: Make the quote button visually premium — consider subtle gradient, inner glow, slight rounding, or a shimmer/shine effect. It should feel inviting, not like a plain rectangle. Think premium hotel booking button, not generic Bootstrap.
- All elements in the nav need proper vertical and horizontal alignment
- The "Pay Online" text should be much more subtle (it's already demoted but check sizing)

### 2. Alignment Audit on All Pages
Go through every page and ensure:
- Text blocks are properly aligned (no weird indents, no orphaned elements)
- Section spacing is consistent (padding between sections)
- Cards in grids align evenly
- Page headers have consistent height/padding
- Mobile responsive still works after changes
- The hero quote form fields on the homepage align cleanly in a row

### 3. Quote Form Fields (homepage hero)
Current fields: Trip Date, Pickup, Destination, Coaches (select). These are in a 5-column CSS grid (4 fields + button). May need fine-tuning on field widths and the button alignment.

### 4. Service Card Images on services/index.html
Just updated from old red circle icons to real photos. Verify they display correctly at the right aspect ratio.

### 5. Subpage Headers
Just added background images to all subpage headers (at 25% opacity behind navy). Verify they look good and the text remains readable.

### 6. Fleet Page Gallery Images
`fleet.html` still references `hero-bus.webp` and `bus-snow.webp` (the old low-res versions). Should use the HD versions: `bus-side-full.webp`, `bus-medium-angle.webp`, `bus-snow-hd.webp`, etc.

### 7. Future Considerations (from competitor research)
- Embed the actual multi-step quote form (from quote-widget.html) into a dedicated `/request-quote.html` page styled to match
- Client logos section on homepage uses text names — replace with actual logo images if available
- Google Reviews badge says "30+ five-star reviews on Google" — update number to match actual count
- Interior bus photos needed (Heath said he'll get one later)
- Consider a heritage/history page with old photos if available
- The "Trusted by" org names are placeholders — Heath needs to confirm which orgs to list

## Key User Preferences (Heath)
- Buses should be prominent, not shaded out (hero overlay was too dark, was fixed)
- No fake metrics — Google reviews badge must be truthfully worded
- Number of coaches matters more than passenger count (single vehicle size = 54)
- Quote form needs: Date, Pickup, Destination, Number of Coaches
- No email link on contact page — replaced with Request Quote button
- Tests on live Netlify site, always push changes
- Browser cache is aggressive — always test in private/incognito tab
