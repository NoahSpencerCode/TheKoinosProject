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
- Installment 1 done: Matthew opening (traditional 1:1–4:25) = 6 pages, 32 lexicon entries, intro (~615 words). File: koinos_data.json (also saved as project doc claude/koinos-matthew.json).
- Verified: JSON valid; zero banned-word leakage in translation pages; sigla stripped; page sizes in range.
- Reader webpage built (2026-07-24): `index.html` (+ `koinos_data.js` data script so it opens from Finder via double-click; also fetches koinos_data.json when served). Apple-style UI: paged reading, Greek show/hide toggle, clickable lexicon words with popover (grace period vs. scroll-dismiss), bottom bar — search sheet (left: lexicon + full-text with snippets), index sheet (right: manuscripts/pages), keyboard nav (←/→, /), light/dark via prefers-color-scheme. `koinos_reader.html` is the self-contained single-file build (data inlined) for sharing/artifacts — regenerate it whenever koinos_data.json changes by re-inlining.
- Next: continue Matthew (the hillside teaching, traditional ch. 5–7) → append pages to koinos_data.json, grow lexicon, regenerate koinos_data.js + koinos_reader.html.
