# Wander Sales Tools — Build Specification

## Deployment
- **Repo**: ~/.openclaw/workspace/wander-sales-tools/ (git remote: jamesprecaswell-tech/wander-sales-tools)
- **Live URL**: https://jamesprecaswell-tech.github.io/wander-sales-tools/
- **After building**: `cd ~/.openclaw/workspace/wander-sales-tools && git add -A && git commit -m "Ship [product name]" && git push origin main`
- **GitHub Pages** is already enabled on the main branch, root path.

## Product #1: WanderOS ROI Calculator (`index.html`)

### What it is
An interactive single-page web app where a property manager inputs their portfolio details and sees projected revenue impact of switching to WanderOS.

### Inputs (3 sliders/fields)
1. **Number of units** (range: 1-500, default: 25)
2. **Average nightly rate** (range: $50-$1000, default: $250)
3. **Current direct booking %** (range: 0-100%, default: 15%)

### Outputs (calculated live as inputs change)
1. **Current annual revenue** = units x ADR x 365 x avg_occupancy(65%)
2. **OTA commission lost** = revenue x (1 - direct_booking%) x 15% (avg OTA take rate)
3. **WanderOS projected direct booking %** = current + 25% lift (capped at 85%)
4. **WanderOS annual savings** = reduction in OTA commissions minus 3% WanderOS fee
5. **Net annual benefit** = savings from OTA reduction - WanderOS cost
6. **ROI %** = net benefit / WanderOS annual cost x 100
7. **"What if you added 50 units?"** growth projection row

### Visual design
- **Primary**: #1B2838 (dark navy, Wander's brand)
- **Accent**: #FF6B35 (coral/orange, Wander energy)
- **Secondary**: #2EC4B6 (teal, positive numbers)
- **Background**: #F7F8FA (light gray)
- **Font**: Inter (Google Fonts) or system sans-serif
- **Layout**: Clean, modern, single-column centered (max-width 720px)
- Top: Wander logo area (text "WanderOS" in brand font), tagline "See what direct bookings could do for your portfolio"
- Middle: Input section with styled range sliders + number displays
- Bottom: Results cards with big numbers, comparison table (Current vs. WanderOS), growth projection
- Footer: "Built by James Caswell — AI Sales Automation for Vacation Rental SaaS"
- **Mobile responsive** — must work on phone screens
- **No frameworks** — pure HTML/CSS/JS, single file is fine

### Key copy points
- WanderOS replaces direct booking sites, preserves SEO, charges 3% fee
- Average OTA take rate is 15-18% (Airbnb/VRBO)
- WanderOS customers see 20-35% lift in direct bookings within 6 months
- "Every 1% shift from OTA to direct saves you $X per year"

---

## Product #2: Personalized Outreach Portfolio (`outreach.html`)

### What it is
A showcase page displaying 20 fully personalized cold outreach emails targeting real SMB property managers — demonstrating James's AI outreach system working on Wander's actual ICP.

### Structure
- **Header**: "AI-Powered Outreach Portfolio — Built for Wander" 
- **Subtitle**: "20 personalized emails targeting SMB property managers. Each enriched with real data: PMS, market, portfolio size, seasonality."
- **Stats bar**: "20 prospects | 9 markets | 6 PMS platforms | 100% personalized"
- **Email cards** (20 total): Each card shows:
  - Prospect name (can be realistic fictional names)
  - Company name
  - Market (e.g., "Destin, FL", "Gatlinburg, TN", "Scottsdale, AZ")
  - PMS (one of: Guesty, Hostaway, Lodgify, Escapia, Streamline, Track, LiveRez, OwnerRez, Hospitable)
  - Portfolio size (10-150 units)
  - Email subject line
  - Email body (3-4 paragraphs, personalized to their market/PMS/size)
  - Tags showing what data was used for personalization
- **Methodology section**: "How this works" — brief explanation of the AI enrichment pipeline
- **Footer**: Same as ROI calculator

### Email content guidelines
- Each email should feel hand-written, NOT template-blasted
- Reference specific market dynamics (e.g., "Destin's summer surge", "Gatlinburg's steady year-round demand")
- Reference their PMS (e.g., "Since you're on Guesty, WanderOS integrates natively — no migration needed")
- Reference portfolio size (e.g., "At 45 units, you're losing roughly $67K/year to OTA commissions")
- CTA: "Worth a 20-minute chat?" with Zoom link placeholder
- Tone: Professional but conversational, not salesy

### Visual design
- Same color palette as ROI calculator (brand consistency)
- Card-based layout, 1 column on mobile, 2 columns on desktop
- Each card is expandable (click to see full email body)
- Collapsed view shows: name, company, market, PMS, subject line
- **Mobile responsive**
- **No frameworks** — pure HTML/CSS/JS

---

## Navigation
- `index.html` = ROI Calculator (landing page)
- `outreach.html` = Outreach Portfolio
- Both pages should have a nav bar linking to each other
- Nav: "WanderOS Sales Tools" brand on left, "ROI Calculator | Outreach Portfolio" links on right

## Quality bar
- **Must work in Chrome, Safari, Firefox**
- **Must be mobile responsive**
- **Must load fast** (no external dependencies except Google Fonts)
- **Numbers must be mathematically correct**
- **No console errors**
- This will be shown to the CEO of a $40M company in an interview. It must look professional.
