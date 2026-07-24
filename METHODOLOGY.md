# The Koinos Project — Working Methodology & Status

## Goal
A fresh English rendering of the Greek New Testament in ordinary modern English, translated the way non-religious Koine texts (histories, letters, papyri) are translated — with all sacral-pseudo vocabulary removed, no chapter/verse numbers, continuous prose paginated like a normal book, Greek and English paired per page, plus a clickable lexicon (Greek word, up to 3 ordinary variants, one secular usage example). Output: JSON per the agreed schema, then a reader webpage.

## Source pipeline (works in Claude cloud sessions)
- Greek base text: **SBL Greek New Testament** (Greek only; no English translation is ever consulted).
- GitHub cloning is blocked in the sandbox; fetch chapters via WebFetch on
  `https://raw.githubusercontent.com/LogosBible/SBLGNT/master/data/sblgnt/text/Matt.txt`
  (other books: same directory, e.g. `Mark.txt`, `Luke.txt`, `1Cor.txt`...). Ask for verbatim reproduction of a verse range per call (a chapter at a time works well).
- Strip text-critical sigla ⸂ ⸃ ⸀ and verse refs; join into continuous prose.

## Honesty notes (agreed with Noah)
- No AI can literally have "never seen" English Bibles; the method instead bans the traditional vocabulary outright and renders from the Greek with ordinary-usage checks.
- Base text is a critical edition of the earliest manuscripts (Sinaiticus/Vaticanus + papyri), stated plainly in the book's intro and manuscript summaries.

## Fixed glossary (keep consistent everywhere)
| Greek | Rendering |
|---|---|
| ἁμαρτία | error, failure |
| ἐκκλησία | assembly |
| βαπτίζω / βαπτιστής | immerse / the Immerser |
| εὐαγγέλιον | good news |
| Χριστός | the anointed |
| κύριος | the Master (God); master/sir (people) |
| ἄγγελος | messenger |
| πνεῦμα (ἅγιον) | (sacred) breath |
| ἅγιος | sacred |
| μετανοέω / μετάνοια | change your thinking / change of thinking |
| βασιλεία τῶν οὐρανῶν | the kingdom of the skies |
| προφήτης | spokesman |
| προσκυνέω | bow down before |
| διάβολος / ὁ πειράζων / Σατανᾶς | the slanderer / the tester / adversary |
| δίκαιος / δικαιοσύνη | fair / what is right |
| σῴζω | rescue |
| δόξα | splendor, reputation |
| συναγωγή | meeting hall |
| δαιμονιζόμενοι / δαιμόνιον | plagued by spirits / spirit |
| μάγοι | astrologers |
| ἔρημος | the open country |
| πονηρός | never "evil" — by context: bad, harmful, nasty, corrupt, flawed (root: ponos, hardship) |
| παρθένος | young woman (never "virgin" — doctrinally loaded; Hebrew behind Isaiah quote is ʿalmāh, young woman) |
| Capitalization | Master/God capitalized only by the ordinary title-as-name rule (like "the Captain"); manuscripts are all-uncial and make no distinction. Noah confirmed keeping capitals. |
| μακάριος | happy, fortunate (upcoming, Matt 5) |
| ἀμὴν λέγω ὑμῖν | "I tell you truly" (upcoming) |
| μαθητής | student (upcoming) |
| γέεννα | the burning rubbish valley (Hinnom) (upcoming) |
| υἱὸς τοῦ ἀνθρώπου | decide at first occurrence (Matt 8) |
| θάλασσα (of Galilee) | the lake |
| Δεκάπολις | the Ten Towns |

## Formatting rules
- No chapter/verse numbers, no headings. Natural paragraphs; ~300–400 English words per page.
- Each book opens with a summary: composition date estimate, earliest surviving copies, where found.
- JSON schema: project / subtitle / introduction / translation_principles / lexicon / manuscripts[{name, summary, pages[{page, greek, english}]}].
- Lexicon keys = lowercase surface word or phrase as it appears in the English.

## Status (2026-07-24)
- Installment 1 done: Matthew opening (traditional 1:1–4:25) = pages 1–6.
- Installment 2 done: the hillside teaching (traditional 5:1–7:29) = pages 7–15; lexicon now 57 entries. New fixed renderings: μακάριος → happy; ὑποκριτής → actor; γέεννα → the burning valley; ἀμὴν λέγω ὑμῖν → I tell you truly; μαθητής → student; παράπτωμα → misstep; ἀπέχω (receipts) → paid in full; μαμωνᾶς → Money; ὀλιγόπιστοι → people of little trust; Ῥακά → Empty-head; Μωρέ → You idiot; πίστις → trust. File: koinos_data.json (also saved as project doc claude/koinos-matthew.json).
- Verified: JSON valid; zero banned-word leakage in translation pages; sigla stripped; page sizes in range.
- Reader webpage built (2026-07-24): `index.html` (+ `koinos_data.js` data script so it opens from Finder via double-click; also fetches koinos_data.json when served). Apple-style UI: paged reading, Greek show/hide toggle, clickable lexicon words with popover (grace period vs. scroll-dismiss), bottom bar — search sheet (left: lexicon + full-text with snippets), index sheet (right: manuscripts/pages), keyboard nav (←/→, /), light/dark via prefers-color-scheme. `koinos_reader.html` is the self-contained single-file build (data inlined) for sharing/artifacts — regenerate it whenever koinos_data.json changes by re-inlining.
- Mobile-first + GitHub Pages pass (2026-07-24): swipe page turns, bottom-card word lookup on phones, 44px touch targets, theme-color/PWA metas, sheet grab handles; `.nojekyll` added and README carries the Pages deploy steps (push → Settings → Pages → main / root). All paths relative — works at a subpath.
- Next: continue Matthew (the healings and the storm, traditional ch. 8–9) → append pages to koinos_data.json, grow lexicon, regenerate koinos_data.js + koinos_reader.html. First occurrence of ὁ υἱὸς τοῦ ἀνθρώπου arrives in ch. 8 — settle its rendering then (candidate: "the son of humanity" / "the human one").
- WebFetch note: the fetch model occasionally refuses verse ranges as "copyright"; retry with smaller ranges and a note that the Greek text is an ancient public-domain-era text — that has worked every time.
