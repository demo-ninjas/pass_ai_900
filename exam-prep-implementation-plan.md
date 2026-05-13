# Exam Prep App — Implementation Plan (v2)

> Use this plan to build an interactive study app for **any** Microsoft certification exam.
> Start a new project for each exam. Replace `[EXAM-ID]` and `[EXAM-NAME]` throughout.
> Each phase builds on the previous one — don't skip ahead.
>
> **Proven on**: AI-900 (146 flashcards, 81 quiz questions, 5 mind maps, full redesign + coverage audit in ~3 hours)

---

## Phase 1: Research & Scaffold

### Goal
Build the knowledge base from official Microsoft sources.

### Prompt
```
I need to pass [EXAM-ID]: [EXAM-NAME]. My workspace is empty at c:\source\[exam-id].

1. Research the official exam page and study guide on learn.microsoft.com
2. Create a content_covered_in_the_exam.md with every testable objective from the official skills measured page (formatted with numbered bullets — this becomes the source of truth for Phase 4 coverage audit)
3. Create a README.md with exam overview, domains, weights, and key links
4. Create a detailed study-guide.md with every exam objective and MS Learn module links
5. Create a study-tracker.md with a day-by-day cram plan using READ → DRILL → RECALL methodology (make it generic — no hardcoded dates, use "Day 1, Day 2" etc. relative to exam day)
6. Create a cheat-sheets/ folder with one detailed cheat sheet per exam domain, including:
   - Exact service names, model names, API parameters, SDK classes
   - REST endpoint patterns and URL formats
   - "Numbers to remember" section (minimums, limits, defaults, timeouts)
   - Decision tables: "when to use A vs B" for every choice the exam tests
7. Create a practice-questions.md with 80+ scenario-based multiple choice questions with answers and explanations, including:
   - At least 5 multi-select questions ("Select two")
   - At least 5 "minimize effort" constraint questions
   - At least 1 question per testable objective

Focus on EXAM-LEVEL detail — exact parameter names, model versions, config values, CLI commands. Not conceptual overviews. The exam tests specifics.
```

### Expected Output
```
[exam-id]/
├── README.md
├── content_covered_in_the_exam.md
├── study-guide.md
├── study-tracker.md
├── practice-questions.md
└── cheat-sheets/
    ├── 1-[domain-name].md
    ├── 2-[domain-name].md
    └── ... (one per domain)
```

### Quality Check
- [ ] Every exam objective from the study guide has at least one cheat sheet entry
- [ ] Every cheat sheet has a "Numbers to Remember" section
- [ ] Every cheat sheet has at least one "When to Use A vs B" decision table
- [ ] MS Learn links are real and working
- [ ] Practice questions are scenario-based ("You need to..."), not definitional ("What is...")

---

## Phase 2: Expert Review & Traps

### Goal
Verify accuracy and build the "tricky stuff" content that separates pass from fail.

### Prompt
```
Review all the content we just created with an expert panel approach:

1. Verify all technical claims against the official Microsoft docs. Fix any errors.
2. Create a traps-and-distinctions.md covering:
   - "Sounds the same" service confusions (things easily mixed up)
   - Parameter traps (common wrong answers that sound right)
   - API endpoint traps (different URL patterns per service)
   - Lifecycle traps (what's immutable after creation, what requires rebuild)
   - "When to use A vs B" decision scenarios the exam loves to test
   - Numbers that trip people up (minimums, limits, defaults)
   - The exact format: scenario | correct answer | why NOT the other answer
3. Create a flashcards.md with 130+ Q&A cards across all domains:
   - Cover every "when to choose" decision
   - Include exact model names, parameter ranges, SDK classes, CLI commands
   - Include cards for every trap in the traps file
   - Instructions at top: cover answer column, say answer out loud, star wrong ones
```

### Expected Output
```
[exam-id]/
├── ... (existing files)
├── traps-and-distinctions.md    ← NEW
└── flashcards.md                ← NEW
```

### Quality Check
- [ ] Every "trap" has a scenario + correct answer + "why NOT the other"
- [ ] Flashcards cover all domains proportionally to exam weight
- [ ] No factual errors (verified against docs)
- [ ] At least 10 "when to choose A vs B" flashcards

---

## Phase 3: Build the Interactive App

### Goal
Create a single-file study app with all features, following the design specs in the Architecture section below.

### Prompt
```
Build a single-file HTML/JS interactive study app (index.html) that includes:

1. Sidebar navigation (Notion/Obsidian style) with icons for each section
2. Dashboard landing page with:
   - Study flow cards: Explore (Mind Maps) → Review (Cheat Sheets) → Practice (Flashcards) → Validate (Quiz)
   - Circular mastery ring (SVG) showing overall % mastered
   - 30-day activity heat map (GitHub contribution style)
   - XP badge showing total experience points
   - Domain mastery progress bars
3. Flashcards tab with:
   - Domain filter buttons
   - Click-to-flip card animation (CSS 3D transform)
   - "Got it" ✓ / "Again" ✗ / ⭐ Star buttons
   - All/Starred/Unmastered mode switcher
   - Progress bar showing position in deck
   - Keyboard shortcuts: Space/Enter=flip, ←=Again, →=Got it, S=Star
4. Quiz tab with:
   - Domain filter buttons, choose 10 or 25 question length
   - Immediate feedback with correct/wrong highlighting + explanation
   - Score shown as pass/fail (≥70%), quiz history saved
5. Mind Maps tab — see "Markmap Integration" section below for exact implementation
6. Cheat Sheets tab with:
   - Search bar (instant text filter across titles and content)
   - Domain filter buttons
   - Click to expand/collapse each section
7. Progress tab with:
   - Cards mastered, starred, total reviews, last quiz, day streak, quizzes taken
   - Domain mastery bars
   - Reset all progress button

Cross-cutting requirements:
- XP system: +5 per flashcard review, +10 per quiz answer
- Activity tracking: log review count per day for heat map
- Zen mode toggle (🧘): hides sidebar/nav for focused study
- Light/dark theme toggle with localStorage persistence
- Inter font from Google Fonts CDN
- Color palette: Deep Navy base (#0F172A), Sage Green success (#76BA99), Indigo accent (#818CF8), Muted Amber attention (#FF8C42)
- 12px border radius, soft shadows (0 4px 24px rgba(0,0,0,.3)), generous whitespace
- Mobile: sidebar becomes bottom tab bar at ≤768px
- localStorage keys prefixed with exam ID (e.g., [exam-id]_starred)
- All data embedded in JS arrays at the top of the script
```

### Content Data Structure
```js
const DOMAINS = [{id, name, weight, color}];
const FLASHCARDS = [{id, d, q, a}];
const QUIZ_QUESTIONS = [{d, q, opts, ans, exp}];  // ans: number (single) or array (multi-select)
const CHEATSHEETS = [{d, title, content}];  // content is HTML string
const MINDMAPS = [{id, title, color, md}];  // md is markdown string for markmap
```

> **Multi-select quiz questions**: Set `ans` to an array of 0-based indices, e.g. `ans:[1,3]`.
> The quiz renderer must handle both `typeof ans === 'number'` and `Array.isArray(ans)`.

### Quality Check
- [ ] All flashcards from flashcards.md are in the FLASHCARDS array
- [ ] All practice questions are in the QUIZ_QUESTIONS array
- [ ] All cheat sheet content is in the CHEATSHEETS array
- [ ] Mind maps cover every cheat sheet topic
- [ ] Domain filters work on all tabs
- [ ] Progress persists across page refreshes
- [ ] Looks good on mobile (test at 375px width)
- [ ] Mind maps render when expanded (not blank)
- [ ] Mind map text is readable on dark AND light themes
- [ ] XP increments on card review and quiz answers
- [ ] Dashboard heat map populates from activity data
- [ ] Zen mode hides sidebar/chrome
- [ ] Theme toggle persists across refreshes
- [ ] Cheat sheet search filters sections in real time
- [ ] Study flow cards on dashboard navigate to correct tabs

---

## Phase 4: 100% Coverage Audit & Gap Fill

### Goal
Achieve 100% coverage of every testable exam objective with both a flashcard AND a quiz question. Ensure proportionality across domains.

### Prompt
```
Do a systematic 100% coverage audit:

1. Read content_covered_in_the_exam.md and number every bullet point (the testable objectives)
2. For EACH numbered bullet, check:
   - Is there at least one flashcard covering it? (cite the FC ID)
   - Is there at least one quiz question covering it? (cite the quiz Q)
3. Produce a coverage table:
   | # | Objective | FC? | Quiz? | Status (✅/🟡/🔴) |
4. For every 🟡 (partial) or 🔴 (missing) item:
   - Add a flashcard to the FLASHCARDS array
   - Add a quiz question to the QUIZ_QUESTIONS array
   - For "minimize effort" scenarios, add a quiz Q where the constraint changes the answer
   - For "select two" scenarios, add a multi-select quiz Q (ans as array)
5. Count flashcards and quiz questions per domain
6. Check proportionality vs exam weight (±20% tolerance)
7. If any domain is significantly over/under-represented, rebalance
8. Ensure flashcard IDs are sequential
9. Update README with current content counts
```

### Coverage Targets
| Metric | Minimum |
|--------|---------|
| Exam objectives with ✅ (FC + Quiz) | **100%** |
| Flashcards per domain | Proportional to exam weight ±20% |
| Quiz questions total | **80+** (at least 1 per objective) |
| Multi-select quiz questions | **At least 5** |
| "Minimize effort" constraint questions | **At least 5** |
| Scenario-based (not definitional) quiz questions | **≥75%** |

### Lessons Learned (AI-900 Build)
- Initial build produced 142 flashcards and 33 quiz questions — seemed like plenty
- Coverage audit revealed 2 objectives with **zero** coverage (🔴) and 9 with only partial coverage (🟡)
- Missing: model management/deployment capabilities, language modeling, several Responsible AI quiz scenarios
- Multi-select and "minimize effort" question types were completely absent
- After audit: 146 flashcards, 81 quiz questions, 6 multi-select, 10 minimize-effort — 100% coverage
- **Key insight**: Always audit against the official skills-measured doc, not against your own content
- **Bug found**: One quiz entry in index.html had `{id:4,...}` instead of `{d:4,...}` — always verify the `d` (domain) property exists on every quiz entry
- **Sync matters**: flashcards.md, practice-questions.md, AND index.html FLASHCARDS/QUIZ_QUESTIONS arrays must all be updated together

### Quality Check
- [ ] Coverage table shows ✅ for every bullet in the skills measured doc
- [ ] Zero 🔴 (missing) items remain
- [ ] Zero 🟡 (partial) items remain
- [ ] Flashcard count per domain is proportional to exam weight (±20%)
- [ ] Quiz includes both single-answer and multi-select question types
- [ ] Quiz includes "minimize effort" constraint questions
- [ ] README content counts match actual counts
- [ ] Flashcard IDs are sequential (no gaps or duplicates)
- [ ] index.html FLASHCARDS array count matches flashcards.md count
- [ ] index.html QUIZ_QUESTIONS array count matches practice-questions.md count
- [ ] Every QUIZ_QUESTIONS entry has `d` (domain), not `id`

---

## Phase 5: Final Expert Panel Review

### Goal
Catch remaining errors, validate methodology, confirm exam readiness.

### Prompt
```
Final expert panel review across all content:

1. Certification exam coach: Are quiz questions scenario-based like the real exam? Are distractors realistic? Any missing question types?
2. Cognitive scientist: Does the study method support active recall and spaced repetition? Is the READ → DRILL → RECALL cycle sound?
3. Technical expert: Verify all facts against current Microsoft docs. Flag anything outdated or incorrect.
4. UX designer: Is the app mobile-friendly? Any friction in the flashcard flow?

Fix everything found. Also:
- Update study-tracker.md to reference the app (e.g., "Open index.html → Flashcards tab → filter to Domain 1")
- Ensure study tracker uses generic dates (Day 1, Day 2...)

Then give me a summary of:
- Total flashcards, quiz questions, cheat sheet sections, mind maps
- Content coverage per domain vs exam weight
- Any remaining gaps and whether they matter for passing
```

### Quality Check
- [ ] No factual errors remaining
- [ ] Quiz distractors are realistic (not obviously wrong)
- [ ] Study tracker references the app (not stale file references)
- [ ] Study tracker uses generic dates (Day 1, Day 2...)
- [ ] All content counts in README are accurate

---

## Phase 6: Ship It

### Goal
Deploy to GitHub Pages and share with team.

### Prompt
```
1. Initialize git repo if needed
2. Push to https://github.com/[org]/pass_[exam-id].git
3. Update README.md with:
   - Link to the live GitHub Pages app at the top
   - Feature table (dashboard, flashcards, quiz, mind maps, cheat sheets, progress) with counts
   - Full repository file structure
   - "How to Study" section with READ → DRILL → RECALL instructions referencing the app
   - Contributing note
4. Give me a short Teams message I can share with colleagues about the app
5. Give me a prompt I can use to evaluate whether this app + Microsoft Learn combined is superior to Microsoft Learn alone
```

### Post-Deploy
- [ ] Enable GitHub Pages: repo Settings → Pages → Source: main, folder: / (root) → Save
- [ ] Test the live URL: `https://[org].github.io/pass_[exam-id]/`
- [ ] Test on mobile
- [ ] Share with team
- [ ] Clean up backup files (index-v1.html, index-backup.html) if present

---

## Exam-Specific Tips

When using these prompts, emphasize the key "decision areas" for each exam:

| Exam | High-Value "A vs B" Decisions to Focus On |
|------|-------------------------------------------|
| **AZ-104** (Azure Admin) | NSG vs ASG vs Firewall vs WAF, Storage tiers, VM availability sets vs zones vs scale sets, VPN Gateway vs ExpressRoute vs peering, Azure Policy vs RBAC vs Blueprints, Load Balancer vs App Gateway vs Front Door vs Traffic Manager |
| **AZ-204** (Azure Developer) | App Service vs Functions vs Container Apps vs AKS, Cosmos DB consistency levels, Blob lease vs snapshot vs versioning, Service Bus vs Event Grid vs Event Hub vs Queue Storage, Managed Identity vs SAS vs connection string |
| **AZ-305** (Azure Architect) | Availability Zones vs Sets vs Regions, RTO/RPO strategies, Azure AD B2B vs B2C, Hub-spoke vs mesh networking, SQL Database vs SQL MI vs SQL on VM vs Cosmos DB, Synapse vs Databricks vs HDInsight |
| **AZ-400** (DevOps) | Deployment slots vs blue-green vs canary vs rolling, YAML vs Classic pipelines, Artifacts vs Packages, Branch policies vs pull request triggers, SonarQube vs WhiteSource vs OWASP ZAP |
| **AZ-500** (Azure Security) | Key Vault vs managed identity vs service principal, Defender for Cloud plans, Sentinel workbooks vs analytics rules vs playbooks, Conditional Access vs MFA vs PIM, Private Link vs Service Endpoint vs Firewall rules |
| **DP-203** (Data Engineer) | Dedicated SQL vs Serverless SQL vs Spark pool, Star schema vs snowflake, Partition strategies, Data Factory vs Synapse pipelines, Delta Lake vs Parquet vs CSV, SCD Type 1 vs 2 vs 3 |
| **DP-300** (Database Admin) | Azure SQL DB vs Managed Instance vs SQL on VM, DTU vs vCore, Active geo-replication vs failover groups, TDE vs Always Encrypted vs Dynamic Data Masking |
| **AI-900** (AI Fundamentals) | "Which service for which task" and Responsible AI principles. Service confusion: Azure AI Vision vs Face vs Document Intelligence, Azure AI Language vs Speech vs Translator |
| **SC-900** (Security Fundamentals) | Authentication vs authorization, Azure AD vs on-premises AD, Conditional Access vs MFA, Defender vs Sentinel vs Monitor, Zero Trust principles |

---

## Architecture & Design Notes

### Why Single HTML File?
- Zero install friction (just open in browser)
- Works offline (no server needed)
- GitHub Pages deploys instantly
- Works on phone for study-on-the-go
- All state in localStorage (survives page refresh)
- Easy to fork and customize

### localStorage Key Strategy
Prefix all keys with exam ID to avoid conflicts if studying for multiple exams:
```
[exam-id]_starred, [exam-id]_mastered, [exam-id]_reviews
[exam-id]_quizHistory, [exam-id]_streak, [exam-id]_theme
[exam-id]_xp, [exam-id]_activity
```

### Visual Design Specifications

Based on cognitive science research for learning tools:

| Element | Spec | Rationale |
|---------|------|-----------|
| **Font** | Inter (Google Fonts CDN) | Highly legible at all sizes, modern/clean |
| **Base dark** | #0F172A (Deep Navy) | Blue linked to focus/productivity |
| **Base light** | #FDFDFD (Off-white) | Less eye strain than pure white |
| **Success** | #76BA99 (Sage Green) | Calm progress feeling |
| **Attention** | #FF8C42 (Muted Amber) | Grabs attention without panic |
| **Primary accent** | #818CF8 / #6366F1 (Indigo) | Primary actions |
| **Error/wrong** | #FB7185 (Soft Red) | Not harsh, but clear |
| **Border radius** | 12px | Modern, friendly feel |
| **Shadows** | `0 4px 24px rgba(0,0,0,.3)` dark / `.06` light | Cards "float" to signal focus |
| **Line height** | 1.55–1.6 | Prevents text crowding |
| **Spacing** | 24–28px content padding, 12px card gaps | Generous whitespace reduces cognitive load |

### Layout Pattern: "Multimodal Knowledge Hub"

The app follows the **Source-to-View** pattern — one dataset rendered in multiple modes:

| Mode | Pattern | UX Purpose |
|------|---------|------------|
| Dashboard | Learning Hub | Status overview + study flow guidance |
| Mind Maps | Infinite Canvas | Big-picture connections |
| Cheat Sheets | High-Density Grid | Quick reference review |
| Flashcards | Minimalist Overlay | Active recall focus |
| Quiz | Progressive Disclosure | Validation testing |

**Study Flow** (shown on dashboard):
1. **Explore** → Mind Maps (see connections)
2. **Review** → Cheat Sheets (familiarize)
3. **Practice** → Flashcards (active recall)
4. **Validate** → Quiz (test mastery)

### Navigation Pattern

**Desktop**: Fixed left sidebar (220px) with icon + label buttons
**Mobile (≤768px)**: Bottom tab bar with icons only, sidebar hidden

Features:
- Dashboard as landing page (not flashcards)
- Zen Mode toggle (🧘): hides sidebar + top bar chrome for deep focus
- XP badge in top bar for quiet gamification
- Theme toggle (🌙/☀️) in top bar

### Markmap Integration — Pitfalls & Solutions

> These lessons were learned the hard way during the AI-900 build. Follow this guide exactly to avoid blank mind maps.

**Pitfall 1: markmap-autoloader doesn't work with dynamic content**
- `markmap-autoloader` scans for `<script type="text/template">` in the DOM
- `<script>` tags inserted via `innerHTML` are **inert** — the browser ignores them entirely
- Even `document.createElement('script')` works for the DOM node, but the autoloader still fails because it renders at 0×0 inside `display:none` containers
- **Solution**: Don't use `markmap-autoloader`. Use the programmatic API instead.

**Pitfall 2: Correct CDN URLs**
```html
<!-- Load in this exact order via sequential promise chain -->
<script src="https://cdn.jsdelivr.net/npm/d3@7"></script>
<script src="https://cdn.jsdelivr.net/npm/markmap-view"></script>
<script src="https://cdn.jsdelivr.net/npm/markmap-lib@0.18.12/dist/browser/index.iife.js"></script>
```
- `markmap-view` needs `d3` as a global — load d3 first
- `markmap-lib` browser build is at `dist/browser/index.iife.js` (NOT `dist/browser/index.js`)
- Both libraries expose their API on `window.markmap`
- **Do NOT guess CDN paths** — verify with `https://data.jsdelivr.com/v1/packages/npm/PACKAGE@VERSION`

**Pitfall 3: SVG needs explicit dimensions BEFORE render**
- markmap measures the SVG to calculate layout
- If the SVG is inside a hidden (`display:none`) container, it measures as 0×0
- **Solution**: Only call `Markmap.create()` AFTER the container is `display:block` and SVG has `height:600px` (not `min-height`, not `auto`)

**Pitfall 4: Dark theme text is invisible**
- markmap renders text in dark colors by default (designed for white backgrounds)
- On a dark theme, the text is invisible
- **Solution**: Override with CSS `fill` on `svg text` elements. Also update inline fills when theme toggles.

**Working implementation pattern**:
```js
// Lazy-load scripts on first use
function loadScript(url) {
  return new Promise((res, rej) => {
    const s = document.createElement('script');
    s.src = url; s.onload = res; s.onerror = rej;
    document.head.appendChild(s);
  });
}

// Load deps once, cache the promise
let depsPromise = null;
function loadDeps() {
  if (!depsPromise) {
    depsPromise = loadScript('https://cdn.jsdelivr.net/npm/d3@7')
      .then(() => loadScript('https://cdn.jsdelivr.net/npm/markmap-view'))
      .then(() => loadScript('https://cdn.jsdelivr.net/npm/markmap-lib@0.18.12/dist/browser/index.iife.js'));
  }
  return depsPromise;
}

// Track rendered maps to avoid re-rendering
const mmRendered = {};

// Render one mind map (call ONLY when container is visible)
function renderMindmap(id, containerId, markdown) {
  if (mmRendered[id]) return;
  const body = document.getElementById(containerId);
  body.innerHTML = '<p>Loading mind map…</p>';
  loadDeps().then(() => {
    const { Transformer, Markmap } = window.markmap;
    const { root } = new Transformer().transform(markdown);
    body.innerHTML = '';
    const svg = document.createElementNS('http://www.w3.org/2000/svg', 'svg');
    svg.style.width = '100%';
    svg.style.height = '600px';  // MUST be explicit, not min-height
    body.appendChild(svg);
    const mm = Markmap.create(svg, { initialExpandLevel: -1 }, root);
    setTimeout(() => mm.fit(), 100);  // auto-zoom after layout
    mmRendered[id] = true;
  }).catch(e => {
    body.innerHTML = '<p>Failed to load. Check internet connection.<br>' + e + '</p>';
  });
}
```

**Required CSS for theme compatibility**:
```css
.mm-body svg text { fill: var(--text) !important; font-size: 14px !important; }
.mm-body svg .markmap-link { stroke-opacity: .6 !important; }
```

**Theme toggle must also update mind map text**:
```js
// In the theme toggle click handler:
const textColor = getComputedStyle(document.documentElement).getPropertyValue('--text').trim();
document.querySelectorAll('.mm-body svg text').forEach(t => { t.style.fill = textColor });
```

### Gamification Without Distraction

| Feature | Implementation | Purpose |
|---------|---------------|---------|
| XP Badge | Top bar, `+5` per card, `+10` per quiz answer | Sense of progress |
| Day Streak | Consecutive days with activity | Consistency motivation |
| Heat Map | 30-day grid on dashboard, color-coded by activity | Visual consistency tracking |
| Mastery Ring | SVG circular progress on dashboard | "How close am I?" at a glance |

All gamification is **non-blocking** — no pop-ups, no level-up screens. Just quiet counters that accumulate.

### Verification & Quality Check Process

> Run these checks after Phase 4 (coverage audit) and before Phase 6 (ship). Every check must pass before pushing.

#### 1. Flashcard Count & Sequential IDs
```powershell
# Count total flashcard rows in markdown
Select-String -Path flashcards.md -Pattern "^\| \d+ \|" | Measure-Object | Select-Object -ExpandProperty Count

# Verify IDs are sequential with no gaps
$nums = @(); Select-String -Path flashcards.md -Pattern "^\| (\d+) \|" | ForEach-Object {
    $nums += [int]$_.Matches[0].Groups[1].Value
}
Write-Host "Range: $($nums[0])-$($nums[-1])"
$ok = $true; for ($i = 1; $i -lt $nums.Count; $i++) {
    if ($nums[$i] -ne $nums[$i-1]+1) { $ok = $false; Write-Host "Gap: $($nums[$i-1])->$($nums[$i])" }
}
if ($ok) { Write-Host "Sequential: OK" }
```

#### 2. Quiz Question Count & Sequential Numbering
```powershell
# Count total questions in markdown
Select-String -Path practice-questions.md -Pattern "^### Question" | Measure-Object | Select-Object -ExpandProperty Count

# Verify sequential numbering
$nums = @(); Select-String -Path practice-questions.md -Pattern "^### Question (\d+)" | ForEach-Object {
    $nums += [int]$_.Matches[0].Groups[1].Value
}
Write-Host "Range: $($nums[0])-$($nums[-1])"
$ok = $true; for ($i = 1; $i -lt $nums.Count; $i++) {
    if ($nums[$i] -ne $nums[$i-1]+1) { $ok = $false; Write-Host "Gap: $($nums[$i-1])->$($nums[$i])" }
}
if ($ok) { Write-Host "Sequential: OK" }
```

#### 3. index.html Data Array Counts Match Markdown
```powershell
# Flashcards in FLASHCARDS array
$c = Get-Content index.html -Raw
$s = $c.IndexOf('const FLASHCARDS=['); $e = $c.IndexOf('];', $s)
$sec = $c.Substring($s, $e - $s + 2)
Write-Host "FLASHCARDS array: $(([regex]::Matches($sec, '\{id:\d+')).Count)"

# Quiz questions in QUIZ_QUESTIONS array
$s2 = $c.IndexOf('const QUIZ_QUESTIONS=['); $e2 = $c.IndexOf('];', $s2)
$sec2 = $c.Substring($s2, $e2 - $s2)
Write-Host "QUIZ_QUESTIONS array: $(([regex]::Matches($sec2, '\{d:\d')).Count)"
```

#### 4. Multi-Select & Minimize-Effort Question Types
```powershell
# Multi-select questions (ans is an array)
$c = Get-Content index.html -Raw
$s = $c.IndexOf('const QUIZ_QUESTIONS=['); $e = $c.IndexOf('];', $s)
$sec = $c.Substring($s, $e - $s)
Write-Host "Multi-select: $(([regex]::Matches($sec, 'ans:\[\d')).Count)"

# "Minimize effort" / "least effort" constraint questions
(Select-String -Path practice-questions.md -Pattern "(?i)(minimum|least|minimize).*(effort|development|configuration)" |
    Measure-Object).Count
```

#### 5. Per-Domain Distribution
```powershell
# Quiz questions per domain
$lines = Get-Content practice-questions.md; $cd = 0; $dc = @{}
foreach ($l in $lines) {
    if ($l -match '^## Domain (\d)') { $cd = [int]$Matches[1] }
    if ($l -match '^### Question ') {
        if (-not $dc.ContainsKey($cd)) { $dc[$cd] = 0 }; $dc[$cd]++
    }
}
$dc.GetEnumerator() | Sort-Object Name | ForEach-Object { Write-Host "D$($_.Key): $($_.Value)" }
```

#### 6. Bug Check: Every QUIZ_QUESTIONS Entry Has `d` (Not `id`)
```powershell
# Should return 0 — any match means a bug
$c = Get-Content index.html -Raw
$s = $c.IndexOf('const QUIZ_QUESTIONS=['); $e = $c.IndexOf('];', $s)
$sec = $c.Substring($s, $e - $s)
$bugs = ([regex]::Matches($sec, '\{id:\d')).Count
if ($bugs -eq 0) { Write-Host "No id bugs found" } else { Write-Host "BUG: $bugs entries have {id:} instead of {d:}" }
```

#### 7. Domain Headers Match Actual Content
```powershell
# Flashcard domain headers
Select-String -Path flashcards.md -Pattern "^## Domain" | ForEach-Object { $_.Line }

# Quiz domain headers
Select-String -Path practice-questions.md -Pattern "^## Domain" | ForEach-Object { $_.Line }
```

#### Expected Results (AI-900 Reference)
| Check | Expected |
|-------|----------|
| Flashcard rows (markdown) | 146 |
| Flashcard IDs sequential | 1–146, no gaps |
| Quiz questions (markdown) | 81 |
| Quiz IDs sequential | 1–81, no gaps |
| FLASHCARDS array (index.html) | 146 |
| QUIZ_QUESTIONS array (index.html) | 81 |
| Multi-select questions | ≥5 (AI-900: 6) |
| Minimize-effort questions | ≥5 (AI-900: 10) |
| `{id:}` bugs in QUIZ_QUESTIONS | 0 |

---

## Estimated Build Time

| Phase | Time |
|-------|------|
| Phase 1: Research & Scaffold | 15–20 min |
| Phase 2: Expert Review & Traps | 10–15 min |
| Phase 3: Build App | 20–30 min |
| Phase 4: Coverage Audit & Gap Fill | 15–25 min |
| Phase 5: Final Review | 5–10 min |
| Phase 6: Ship | 5 min |
| **Total** | **~75–115 min per exam** |

> **Note**: Phase 4 took longer than expected on AI-900 because the initial build had only 33 quiz questions. The coverage audit added 48 new questions. Starting Phase 1 with a higher question target (80+) would reduce Phase 4 work.

---

## Final Repository Structure

```
[exam-id]/
├── index.html                          ← Interactive study app (open in browser)
├── README.md                           ← Exam overview, feature table, links
├── content_covered_in_the_exam.md      ← Official skills measured (audit source of truth)
├── study-guide.md                      ← Exam objectives + MS Learn links
├── study-tracker.md                    ← 7-day cram plan (references the app)
├── practice-questions.md               ← Scenario-based questions (80+)
├── flashcards.md                       ← Q&A flashcards (all domains)
├── traps-and-distinctions.md           ← Common exam traps
├── exam-prep-implementation-plan.md    ← This file
└── cheat-sheets/
    ├── 1-[domain-name].md
    ├── 2-[domain-name].md
    └── ... (one per domain)
```
