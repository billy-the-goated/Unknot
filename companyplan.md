# Easily Uncomplicated: Company Plan

*Working draft v1. Written to be edited: change anything that doesn't fit.*

---

## 1. The Snapshot

| | |
|---|---|
| **Name** | Easily Uncomplicated |
| **What it is** | A small online company that builds easy-to-use, browser-based apps that make seemingly complicated things simple |
| **First app** | **Tracks**: a simple way to track where your money goes and export it |
| **Business model** | Free. No adverts. No paid tier. (See section 9 for how to keep costs near zero) |
| **Brand look** | Blue and red, minimal, friendly |
| **Platform order** | Browser first, then installable web app (PWA), then native apps if there's demand |
| **Accounts** | Not needed at first. Added once there is more than one app or a need for sync |

**Tagline:** *Simple on purpose.*

**One-line pitch (draft):** *Simple apps for things that feel harder than they should.*

*Other taglines considered: "Complicated things, made easy." and "Less hassle. More done."*

---

## 2. Mission, Vision, Values

**Mission:** Take everyday tasks that feel confusing or tedious and turn them into tools anyone can use in under a minute.

**Vision:** A small family of free, trustworthy apps that people open, use, and close, without being tracked, nagged, or sold anything.

**Core values**
1. **Simple first.** If a feature needs an explanation, simplify it or cut it.
2. **Respect the user.** No ads, no dark patterns, no selling data.
3. **Own your data.** Everything can be exported. Nothing is locked in.
4. **Fast and light.** Apps load quickly, work on old phones and slow connections, and work offline where possible.
5. **Ship small.** One finished small thing beats ten half-finished big things.

**The "Uncomplicated Test"** (apply to every feature before building it):
- Can a first-time user do the main task without instructions?
- Can it be done in 3 taps/clicks or fewer?
- Would removing this feature make the app worse? If not, remove it.

---

## 3. Brand

### Logo
- **Concept:** A tangled line that straightens out and ends in a red dot, inside a rounded blue square. It shows "complicated made uncomplicated" in one shape.
- **Wordmark:** lowercase "easily" in blue over "uncomplicated" in red.
- **Versions to produce:** full lockup (mark + wordmark), mark only, one-colour dark, one-colour white, favicon (16/32/48 px), app icon (512 px), social avatar, banner.

### Colours (starting palette)
| Role | Name | Hex |
|---|---|---|
| Primary | Royal blue | `#1E4BD2` |
| Accent / alert | Signal red | `#E5383B` |
| Dark | Deep navy | `#0B1B4D` |
| Surface | Soft blue-grey | `#F1F4FB` |
| Background | White | `#FFFFFF` |

**Colour rules**
- Blue is for the main actions and brand. Red is used sparingly: the logo dot, "money out" and warnings.
- Check text contrast. Red text is fine for large headings; use navy for small body text.
- Never rely on red vs. green alone to show meaning. Add icons or labels (important for colour-blind users).

### Typography
- **Headings and logo:** Outfit (free on Google Fonts), weights 500-600.
- **Body text:** a clean system font stack as a fallback so pages load fast.
- Keep line lengths short and font sizes generous (16px minimum for body).

### Voice and tone
- Plain, friendly, short sentences. No jargon.
- Say "Add money" not "Create credit entry".
- Errors should say what happened and what to do next.

---

## 4. Product Strategy

### How the apps relate
Each app is its own small tool but shares: the same style, the same top bar, the same export approach, and (later) the same account. The landing page shows each app as an easy tab or card.

### App 1: Tracks

**What it does:** You create a "track" (for example "Personal", "Holiday", "Business"). Inside it you can have **as many wallets as you like**, and every rand is recorded in detail: **what** it was spent on, **when**, **how much**, and **from which wallet**. You can always see where the money went and export it.

**Worked example:**
1. **Main** wallet receives **R6,000** (income, 1 Oct).
2. One transfer from Main is **split across several wallets**: **R2,000 to PC**, **R1,000 to Savings**, **R500 to Cash**.
3. Spend **R133** from Main on **Food** (2 Oct, 14:35, "Groceries").
4. Tracks shows: Main = 6,000 - 3,500 - 133 = **R2,367**; PC = **R2,000**; Savings = **R1,000**; Cash = **R500**; Food spending = **R133**. Every line can be opened to see exactly what it was.

**Key concepts**
- **Track:** a separate ledger/project (its own wallets, categories and history).
- **Wallet:** a place money sits. A track can have unlimited wallets (Main, PC, Savings, Cash, Holiday fund...). Each has a name, colour, optional icon and starting balance.
- **Entry:** one of three types:
  - **Income:** money coming into a wallet (with its source, e.g. Salary)
  - **Expense:** money spent from a wallet
  - **Transfer:** money moved from one wallet to **one or many** other wallets in a single entry, with an optional **fee** (bank or transfer charge)
- **Category and subcategory:** e.g. Food > Groceries. Presets plus your own.
- **Tags:** free labels for any extra grouping (e.g. "birthday", "work trip").

**What each entry can record (as much detail as you want, none of it forced)**

| Field | Required? | Notes |
|---|---|---|
| Amount | Yes | Stored as whole cents |
| What it was ("what was spent on what") | Yes | Short title, e.g. "Groceries", "Phone data" |
| Date | Yes (defaults to today) | Date picker, can backdate |
| Time | Optional | Useful for tracing a day |
| Wallet | Yes | Which wallet it came from / went into |
| Category / subcategory | Expenses: yes | Quick-pick buttons |
| Place / shop / person | Optional | Who you paid or who paid you |
| Payment method | Optional | Card, cash, EFT, etc. |
| Tags | Optional | Any number |
| Note | Optional | Longer free text |
| Receipt photo | Optional (v1.2) | Stored on the device |
| Transfer fee | Optional (transfers only) | A bank or transfer charge. Taken from the source wallet and counted as spending under "Bank fees" |
| Item breakdown | Optional | See below |

**Transfer fee:** when moving money, you can add a fee, for example R5 charged by the bank. It leaves the source wallet together with the transferred amount, shows up in your spending under a "Bank fees" category (so it is never lost), and appears in the entry detail and in exports. If there is no fee, leave it blank.

**Item breakdown (splits):** one purchase can be broken into lines. Example: a R450 shop = Food R300 + Household R150. Each line has its own *what*, category and amount, and the lines must add up to the total.

**Keeping it uncomplicated:** the "Add" screen shows only four things at first (amount, what, wallet, date). A "More details" section expands to everything else. Detail is there when you want it, hidden when you don't.

#### MVP (version 1.0): build this first
- Create, rename, delete tracks
- **Unlimited wallets per track**, each with a starting balance
- Add Income / Expense / Transfer with: amount, what, date (+ optional time), wallet, category/subcategory, place, payment method, tags, note
- **Split transfers:** move money from one wallet to several wallets in one entry
- **Optional transfer fee** on any transfer, counted as spending under "Bank fees"
- **Item breakdown** on expenses
- Balance per wallet and total, always up to date
- Click any entry to see its full detail
- History list with search, plus filters for date range, category, wallet, tag, type and amount
- "Where did it go?" view: totals per category, per wallet, per day/week/month
- Edit and delete entries (with undo)
- **Export to CSV** with all details
- Data saved in the browser (works offline)
- Currency defaults to ZAR (R) with a setting to change it
- Clean mobile-first layout, works on desktop

#### Version 1.1
- Export to **Excel (.xlsx)** and **PDF** (nicely formatted summary + table)
- Import from CSV
- Simple charts: spending by category, money in vs. out over time, wallet balances
- Backup and restore file (download/upload one file to move data between devices)
- Light and dark themes

#### Version 1.2
- Recurring entries (rent, salary, subscriptions)
- Spending limits per category and savings goals per wallet
- Optional PIN lock
- Receipt photo attachments (stored locally; keep file sizes small)
- Multiple currencies

#### Later (only if people ask)
- Sync across devices (needs accounts)
- Shared tracks (for couples or small groups)
- Installable app (PWA) and Android app
- More languages (Afrikaans is a natural second language)

#### Screens
1. **Home:** list of tracks, "New track" button
2. **Track overview:** total balance, wallet cards, recent entries, big "+ Add" button
3. **Add entry:** one simple form; type selector at the top (In / Out / Move). Four fields up front, a "More details" section for the rest. Move lets you add several destination wallets.
4. **History:** filterable list; tap an entry to see everything recorded about it
5. **Wallets:** all wallets with balances; tap one to see its own history
6. **Insights:** charts (v1.1)
7. **Export:** choose format and date range
8. **Settings:** currency, theme, backup/restore, about

#### Data model (simple)
```
Track     { id, name, currency, createdAt }
Wallet    { id, trackId, name, startingBalance, color, icon, archived }
Category  { id, trackId, name, parentId, type }
Tag       { id, trackId, name }

Entry     { id, trackId, type: income|expense|transfer,
            what, date, time, note, place, paymentMethod, tagIds[],
            createdAt, updatedAt,

            // income / expense
            walletId, amount, categoryId,
            splits[]  { what, categoryId, amount },   // optional item breakdown

            // transfer (one source, one or many destinations)
            fromWalletId,
            legs[]    { toWalletId, amount },
            fee       { amount, categoryId } }          // optional, defaults to the "Bank fees" category
```
Balances are **calculated** from starting balance + entries, never stored separately. This avoids drift and bugs.

**Rules that keep the numbers honest**
- Store amounts as whole cents (integers), not decimals, so there are no rounding errors like 0.1 + 0.2.
- What leaves the source wallet in a transfer is the legs added together **plus the fee** (the app shows the running total as you add legs and the fee).
- A fee is always taken from the source wallet and counted as an expense, so category totals and wallet balances both include it.
- An expense's item breakdown must add up to its total.
- Deleting a wallet that has entries is not allowed; it can only be archived.

#### CSV export format (example)
One row per entry line (a split transfer or itemised expense produces one row per leg/line, grouped by `EntryID`; a transfer fee gets its own row with Type = Fee):
```
EntryID,Date,Time,Type,What,Amount,Wallet,From,To,Category,Subcategory,Place,PaymentMethod,Tags,Note
1,2026-10-01,08:00,Income,October pay,6000.00,Main,,,Salary,,,EFT,,
2,2026-10-01,09:10,Transfer,Move to wallets,2000.00,,Main,PC,,,,,,Saving for PC
2,2026-10-01,09:10,Transfer,Move to wallets,1000.00,,Main,Savings,,,,,,
2,2026-10-01,09:10,Transfer,Move to wallets,500.00,,Main,Cash,,,,,,
2,2026-10-01,09:10,Fee,Transfer fee,5.00,Main,,,Bank fees,,,,,
3,2026-10-02,14:35,Expense,Groceries,133.00,Main,,,Food,Groceries,,Card,,
```
Use UTF-8 with a BOM so Excel opens special characters correctly. The Excel export adds one sheet for entries, one for wallet balances and one for category totals.

#### PDF export
One clean page header (track name, date range), summary box (total in, total out, balances), spending-by-category table, then the full entry list. Use the brand colours lightly.

### Future app ideas (brainstorm, not commitments)
Pick only apps that pass the Uncomplicated Test, where a normal person says "finally, something simple":
- Simple budget planner
- Bill and due-date reminder
- Unit and currency converter
- Quote / invoice maker
- Habit or checklist tracker
- Document and file tidy-up tools (merge/split PDFs, resize images)

Rule: **do not start app #2 until Tracks is live and people are using it.**

---

## 5. The Website

### Landing page
- Minimal. White background, lots of space, brand blue and red used sparingly.
- **Top bar:** logo on the left; on the right, "Apps" and "About".
- **Hero:** logo mark, one-line pitch, one button ("Open Tracks").
- **App tabs:** easy tab or card view, one per app. Tracks is active; others show "Coming soon".
- **Promise strip:** three short points: *Free. No ads. Your data stays yours.*
- **Footer:** about, contact, privacy, small "made by" line.

### Other pages
- **About:** the story and the promise (short).
- **Privacy:** plain-language explanation of what is and isn't stored.
- **Support/Contact:** one email address.
- **Changelog:** what's new, shows life and progress.

### Accessibility and quality checklist
- Works at phone width first
- Keyboard-navigable; visible focus outlines
- Real buttons and labels, alt text on images
- Contrast checked (aim for WCAG AA)
- Page loads fast (aim for under 1 second on a good connection, under 3 on slow)

---

## 6. Technical Plan

### Stack options

**Option A: Plain web (HTML + CSS + JavaScript)**
- Lowest cost, fastest to load, easiest to host free
- Great for the landing page and a simple Tracks MVP
- Good for learning

**Option B: Flutter (web + Android)**
- One codebase for browser and mobile later
- Heavier initial load on the web
- Good if native Android is a firm goal

**Recommendation:** Build the **landing page in plain HTML/CSS/JS**. For Tracks, either plain JS (lightest and quickest to ship) or Flutter web (if you want one codebase for the future Android app). Decide before writing Tracks code, and don't mix.

### Suggested libraries
- CSV: write it yourself (simple)
- Excel: SheetJS (xlsx)
- PDF: jsPDF (+ autoTable plugin)
- Charts: Chart.js
- Storage: IndexedDB (via a tiny wrapper such as `idb`), with `localStorage` for settings only

### Storage and offline
- **Phase 1:** everything lives in the user's browser. No server, no cost, works offline.
- Make it a **PWA** (manifest + service worker) so it can be installed on a phone's home screen.
- Warn users clearly that clearing browser data deletes their tracks, and make **backup/restore** easy and prominent.

### Accounts and sync (later)
- Only added when needed (second app, or sync demand).
- Use a managed service with a free tier (e.g. Supabase or Firebase) instead of building login yourself.
- Keep it **optional**: the app must still work without an account.
- Store the minimum: email, hashed login via the provider, and the user's data. Nothing else.
- Always provide **Export everything** and **Delete my account and data**.

### Repository structure (suggestion)
```
easily-uncomplicated/
  site/            landing page
  apps/
    tracks/        Tracks app
  shared/          shared styles, logo files, small utilities
  docs/            this plan, design notes, changelog
```

### Hosting and domain
- **Decision for now:** host on **GitHub Pages** using the free `github.io` address. No domain yet. Buy one (e.g. at Porkbun) only once there are signs of a small market, then add it to GitHub Pages with a `CNAME` file and DNS records. The site and apps don't need to change.
- **Home hosting** (own server with a Cloudflare Tunnel) is parked until the project has traction.
- **Hosting:** GitHub Pages or Cloudflare Pages (free, fast, HTTPS included).
- **Domain:** one short, brandable domain (roughly R150-R300 per year). Check availability for the exact name plus variants. Register the matching social handles at the same time.

### Quality and safety
- Test on a cheap Android phone, an iPhone, and desktop (Chrome, Firefox, Safari).
- Add automated tests for the money logic (balances, transfers, rounding), because that is where bugs hurt most.
- Keep dependencies few and pinned to exact versions.
- Use HTTPS only and a strict Content Security Policy.

---

## 7. Privacy, Data and Legal Basics

*This is general information, not legal advice. Check with a qualified person before launch, especially once accounts exist.*

- **Privacy by design:** in Phase 1, financial data never leaves the user's device. That is a strong selling point. Say it on the landing page.
- **Analytics:** if used at all, choose a privacy-friendly option (e.g. a cookie-free, self-hostable one) and never record financial data. No third-party ad or tracking scripts.
- **Privacy policy and terms:** plain-language, short, written before accounts launch.
- **Data-protection law:** if you're in South Africa (the rand examples suggest so), POPIA applies once you handle personal information such as emails for accounts. If you have users elsewhere, other laws (like GDPR) may apply.
- **Business registration:** decide whether to start as a sole proprietor or register a company. A free product with no income has simpler obligations, but you must revisit this the moment you accept donations or any money.
- **Disclaimer:** Tracks is a personal tracking tool, not financial advice or an accounting system. State this.
- **Licensing:** note licenses of every library used. Choose a license for your own code (or keep it private).

---

## 8. Marketing and Launch

### Positioning
*"Free, ad-free, simple apps that respect you."* The no-ads, no-paywall, own-your-data promise is the differentiator.

### Before launch
- Landing page live with a clear promise
- A 30-60 second demo video or GIF of Tracks
- A short "how Tracks works" section on the page
- 5-10 friends or family testing it, watching them use it without helping

### Launch
- Share on social channels and communities where people discuss budgeting, privacy tools, and free software
- Post a short build-in-public story: *what I made, why, what's next*
- Make the first-time experience flawless: open the app, add first entry within 30 seconds

### Growth (no-ads friendly)
- Word of mouth and a "Share" button
- A helpful blog/guide section (for example "How to track spending without a spreadsheet")
- Keep a public changelog and roadmap
- Respond to every piece of feedback in the first months

---

## 9. Money: Keeping It Free and Sustainable

### Core idea
Keep the running cost close to **zero** so the "free, no ads, no paid tier" promise is sustainable.

### Expected costs
| Item | Estimate | Notes |
|---|---|---|
| Domain | ~R150-R300 / year | Only unavoidable cost |
| Hosting | R0 | GitHub/Cloudflare Pages free tiers |
| Local-first app storage | R0 | Data lives on user devices |
| Accounts/sync backend | R0 to start | Free tier; costs begin only if usage grows |
| Email for support | R0 | Free mailbox |
| Design tools | R0 | Free tools |

### What if costs start to appear?
In order of preference:
1. Optimise: store less, reduce backend calls.
2. Optional donations ("Buy me a coffee", GitHub Sponsors), never nagging, never blocking features.
3. Cap free sync storage per account, but keep local use unlimited.
4. As a last resort, reconsider the promise openly and honestly with users. Never switch to ads quietly.

### Decision to make early
Which of these you're willing to do. This protects the promise later.

---

## 10. Roadmap

Assumes part-time work (evenings and weekends). Adjust dates to your real pace.

| Phase | Time | Goal | Done when |
|---|---|---|---|
| **0. Foundations** | Weeks 1-2 | Name checked, repo, logo files, palette and fonts (domain comes later, see section 6) | Repo created, logo exported in all sizes |
| **1. Landing page** | Weeks 2-3 | Minimal site live | Page online with app tab for Tracks |
| **2. Tracks MVP** | Weeks 3-8 | Tracks 1.0 working in the browser | Tracks + wallets + entries + balances + CSV export, works offline |
| **3. Testing** | Weeks 8-10 | Real people use it | 5-10 testers, top issues fixed |
| **4. Public launch** | Week 10-11 | Tracks announced | Live link shared, feedback channel open |
| **5. Tracks 1.1** | Weeks 11-16 | Excel/PDF export, charts, backup/restore, themes | Features shipped and documented |
| **6. Tracks 1.2** | Weeks 16-22 | Recurring entries, limits, goals, PIN | Shipped |
| **7. Accounts** | When app #2 is close | Optional login and sync | Login, sync, delete-account, export all working |
| **8. App #2** | After Tracks is stable | Second app | Chosen by feedback, built with the Uncomplicated Test |

**Milestone rule:** each phase ends with something a real person can see or use.

---

## 11. Success Measures

**Market check before spending money (domain, etc.):** launch Tracks on the free `github.io` address, share it with a small group, and watch for real signs of interest, for example people coming back to use it again, unprompted messages or feature requests, and shares. Decide your own bar beforehand (for instance, a set number of returning users after a few weeks). If it's met, buy the domain; if not, improve Tracks or try a different app idea.

Keep these simple and privacy-respecting.

- **Does it work?** Entries saved correctly, exports open in Excel/Sheets without errors.
- **Is it simple?** A new user adds their first entry within a minute (test with real people).
- **Is it used?** Number of visits and returning visits (privacy-friendly analytics only).
- **Is it liked?** Feedback messages, shares, and unprompted compliments.
- **Is it sustainable?** Monthly cost stays within what you're happy to pay.

**First-year goals (example, adjust to taste):**
- Tracks 1.0 launched and stable
- A few hundred real users
- Tracks 1.1 and 1.2 shipped
- Accounts live
- App #2 chosen and in progress

---

## 12. Risks and How to Handle Them

| Risk | Impact | What to do |
|---|---|---|
| Users clear browser data and lose tracks | High: trust loss | Prominent backup/restore, regular "back up now" reminder, PWA install |
| Money calculation bug | High | Integer cents, tests for all balance logic, import/export round-trip tests |
| Too many features, never finishing | High | Strict MVP; Uncomplicated Test; one app at a time |
| Costs grow with accounts/sync | Medium | Free tiers, caps, optional donations, optimise storage |
| Name or domain conflicts | Medium | Check early; register handles; consider trademark search |
| Privacy or legal mistakes | Medium | Short policy, minimum data, take advice before accounts |
| Burnout (building alongside other commitments) | Medium | Small weekly goals, public changelog for motivation, protect rest days |
| Competition from big budgeting apps | Low-Medium | Win on simplicity, no ads, own your data, speed |
| Browser quirks (Safari storage limits, etc.) | Medium | Test early on iPhone/Safari; keep data small; export reminders |

---

## 13. Working Routine (suggestion)

- **Weekly rhythm:** one planning session (pick 1-3 tasks), build sessions, one review (what shipped, what's next).
- **Keep a log:** short notes on decisions and why you made them.
- **Document as you go:** README, changelog, screenshots. It helps users and also builds a portfolio and CV.
- **Version everything** in Git with clear commit messages.

---

## 14. Open Decisions Checklist

Tick these off as you decide:

- [x] Final tagline: Simple on purpose.
- [ ] Domain name and social handles (deferred until there are signs of a market)
- [ ] Tech for Tracks: plain JS or Flutter web
- [ ] Which exports in MVP (CSV only, or CSV + Excel)
- [ ] Sole proprietor or registered company (and when)
- [ ] Donation option: yes or no
- [ ] Analytics: none or privacy-friendly
- [ ] Source code: public (open source) or private
- [ ] Languages: English only at launch, Afrikaans later?
- [ ] First 3 candidates for app #2

---

## 15. Immediate Next Steps (this week)

1. Check that the name is free on the social platforms you care about. Skip buying the domain for now.
2. Finalise the logo files (full lockup, mark, favicon, one-colour versions).
3. Create the GitHub repo and folder structure.
4. Sketch the landing page and the Tracks "Add entry" screen on paper.
5. Decide the tech for Tracks.
6. Build the landing page.

---

*Keep this file in the `docs/` folder and update it as decisions are made.*
