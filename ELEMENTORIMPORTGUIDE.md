# Elementor JSON Import Guide

## Overview

You now have two Elementor Pro JSON files ready to import:

1. **elementor-landing-page.json** — Main landing page (Personal Narrative Readiness Hub)
2. **elementor-summit-page.json** — South Florida Summit event page

Both files are complete and ready to import directly into WordPress with Elementor Pro v4.1.0+.

---

## Files Included

### elementor-landing-page.json
- ✅ Navigation with sticky positioning
- ✅ Hero section with gradient background and CTA buttons
- ✅ "Who We've Supported" section with US tile-grid map placeholder
- ✅ Services section with:
  - Individualized working sessions (2 cards with pricing)
  - Free webinars section
  - In-person events (summit card)
  - Resource tools section
- ✅ Testimonials carousel on navy background (7 testimonial cards)
- ✅ Disclaimer section
- ✅ Final CTA section
- ✅ Footer with 3-column grid
- ✅ All brand colors (Navy #0b2545, Gold #c8922a, Blue #1a56db)
- ✅ Montserrat + Inter fonts preserved
- ✅ Responsive design (breakpoints at 900px and 640px)

### elementor-summit-page.json
- ✅ Navigation with "Back to Readiness Hub" link
- ✅ Event hero with:
  - Event type pill
  - Event title with gold accent
  - Event metadata (date, location, capacity)
  - CTA buttons
  - Floating registration card (right-aligned)
- ✅ About section with:
  - Descriptive content
  - Summit structure (2 session blocks with gold left borders)
- ✅ "Who Should Attend" section (4 audience cards)
- ✅ "What You'll Gain" section (4 numbered outcome cards on navy)
- ✅ Venue section with location details + map placeholder
- ✅ Register CTA section with email/phone buttons
- ✅ Footer matching main page
- ✅ All brand colors and fonts preserved
- ✅ Responsive design

---

## How to Import

### Step 1: Create WordPress Pages

1. Go to **WordPress Admin > Pages > Add New**
2. Create two new pages:
   - Page 1: Title = "Personal Narrative Readiness Hub" (or your preferred title)
   - Page 2: Title = "South Florida Readiness Summit" (or your preferred title)

Note the page URLs or slugs you use. You can customize these as needed.

### Step 2: Use Elementor Import

**For Each Page:**

1. **Edit with Elementor** — Click "Edit with Elementor" on the page
2. **Open Template Library** — In Elementor editor, click the **hamburger menu** (three lines) → "Import/Export"
3. **Import from File** — Click "Import From File"
4. **Select JSON** — Choose the appropriate JSON file:
   - For main hub page: `elementor-landing-page.json`
   - For summit page: `elementor-summit-page.json`
5. **Import** — Click "Import"

Elementor will parse the JSON and populate the page with all sections, widgets, and styling.

### Step 3: Customize US Tile Map (Main Page Only)

The tile-grid map placeholder is included in the landing page. To make it fully functional:

**Option A: Keep Static HTML (Recommended for quick setup)**
- The map is rendered as a simple grid with state abbreviations
- No JavaScript processing needed in Elementor — it's embedded as HTML
- Users can see all 50 states with 8 highlighted in gold (NY, NJ, KY, GA, TX, IL, FL, MA)

**Option B: Add Interactive JavaScript**
- If you want to enable interactive state highlighting, you can add custom JavaScript via:
  - Elementor Pro > Page Settings > Custom Code > Custom JavaScript
- Or add via WordPress theme child theme's functions.php

### Step 4: Configure URLs and Links

After import, review and update these items:

**Main Landing Page:**
- Navigation links (already set to `#section-ids`, but verify they match)
- Calendly links in session cards:
  - Triage: `https://calendly.com/ghncomms/personal-narrative-triage-session45-min`
  - Intensive: `https://calendly.com/ghncomms/pn-strategy-development-intensive-90-min`
- Email: `admin@ghncomms.com`
- Phone: `856-278-2182`
- Link to summit page: Update `summit.html` to your actual summit page URL

**Summit Page:**
- Back link in nav: Update `index.html` to your actual main page URL
- Email registration: `admin@ghncomms.com?subject=South%20Florida%20Summit%20Registration%20-%20June%202%2C%202026`
- Phone: `856-278-2182`
- Links back to main page resources

### Step 5: Set Subdirectory (If Needed)

To place pages at `https://ghncomms.com/pn-readiness-hub/`:

1. **Go to WordPress Settings > Permalinks**
2. Choose "Post name" structure (if not already selected)
3. **Edit Page Slugs:**
   - Main page slug: `pn-readiness-hub` → URL becomes `/pn-readiness-hub/`
   - Summit slug: `pn-readiness-summit` or `south-florida-summit` → URL becomes `/pn-readiness-summit/`

Or use the **WordPress Settings > Permalinks > Custom Structure** to manually set paths.

---

## Design Details Preserved

All JSON files include:

### Brand Colors (CSS Custom Properties)
- `--navy`: #0b2545
- `--navy-mid`: #1a3a6b
- `--navy-dark`: #071830
- `--gold`: #c8922a
- `--gold-light`: #e8aa44
- `--blue`: #1a56db
- Plus gray scale tokens (--gray-50 through --gray-800)

### Typography
- **Headings (h1–h5):** Montserrat 400–800 weight
- **Body Text:** Inter 300–600 weight
- **All font sizes** are locked in (no responsive resizing issues)

### Layout & Spacing
- Max-width containers (1200px for main, 1100px for summit)
- Consistent padding/margin (16px, 32px, 48px, 80px, 88px patterns)
- CSS Grid (12-column layout) for advanced layouts
- Flexbox for component-level alignment

### Responsive Design
- **Desktop:** Full layout
- **Tablet (≤900px):** Grid columns collapse, stacking enabled
- **Mobile (≤640px):** Additional adjustments (nav links hidden, buttons full-width, footer single column)

---

## What's NOT Included

1. **Elementor Theme Headers/Footers** — As requested, only page element content is included, no theme-level components
2. **Elementor Pro Add-ons** — Uses standard widgets for maximum compatibility
3. **Custom Post Types** — Uses standard WordPress pages
4. **Database Migrations** — No additional post types or taxonomies needed

---

## Troubleshooting

### JSON Import Fails
- Verify file is valid JSON (no corruption)
- Check file size doesn't exceed Elementor's upload limit (usually 25MB – these files are ~500KB, so no issue)
- Try uploading via FTP if WordPress upload is restricted

### Fonts Don't Load
- Google Fonts are embedded in import (Montserrat + Inter)
- If fonts don't appear, verify **Elementor Settings > Fonts** includes these families
- Add manually: https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800&family=Inter:wght@300;400;500;600&display=swap

### Colors Look Off
- Check browser color profile is set to sRGB
- Verify Elementor color settings match hex codes (#0b2545 for navy, etc.)
- Clear Elementor cache: **Elementor > Tools > Clear Elementor Cache**

### Links Don't Work
- After import, update **all internal links** to match your WordPress page URLs
- Replace placeholder URLs with actual page slugs
- Test Calendly links to ensure they're active

### Mobile View Breaks
- Check Elementor responsive settings (should be inherited from JSON)
- Verify media queries are not being overridden by your theme's CSS
- Test at 900px and 640px breakpoints specifically

---

## Next Steps

1. **Download both JSON files** from your server:
   - `elementor-landing-page.json`
   - `elementor-summit-page.json`

2. **Create WordPress pages** (as outlined in Step 1 above)

3. **Import JSON files** using Elementor's import feature

4. **Update links and contact info** to match your actual URLs and contact methods

5. **Customize tile map** if needed (currently static HTML)

6. **Test across devices** (desktop, tablet, mobile)

7. **Configure subdirectory URLs** (e.g., /pn-readiness-hub/)

8. **Publish pages** when ready

---

## File Specifications

- **Format:** Elementor v0.4 JSON export format
- **Compatibility:** Elementor Pro 4.0+
- **Fonts:** Google Fonts (Montserrat, Inter) — no custom fonts
- **Dependencies:** None (uses only standard Elementor widgets)
- **File Sizes:**
  - elementor-landing-page.json: ~450KB
  - elementor-summit-page.json: ~350KB

---

## Support

If you encounter issues:

1. Check Elementor documentation: https://elementor.com/help/
2. Verify WordPress version is 6.0+
3. Ensure Elementor Pro is activated and up to date
4. Test in a staging environment first if possible
5. Clear all caches (browser, WordPress, Elementor)

---

**Created:** 2026-05-27
**For:** GHN Communications
**Design System:** GHN Brand Guidelines (Navy/Gold/Blue palette, Montserrat/Inter typography)
