# The Koinos Project — Working Methodology & Status

## Goal
A fresh English rendering of the Greek New Testament as ordinary literature — the way non-religious Koine texts (histories, letters, papyri) are translated. No chapter/verse numbers; continuous prose paginated like a normal book; Greek and English paired per page; clickable lexicon (Greek word, up to 3 ordinary variants, one secular usage example). Output: JSON per the agreed schema, then a reader webpage.

## Source of truth (Noah, 2026-07-28)
- **There is no enforced banned-word list.** If the English is a correct rendering of the Greek as literature, it is fine — even if a traditional "Bible word" happens to be the ordinary English for that Greek.
- Prefer ordinary modern usage when the Greek is ordinary. The fixed glossary and attention patterns are **defaults and consistency aids**, not a police list.
- Never consult English Bible translations; answer only to the Greek and to ordinary literary English.

## Source pipeline (works in Claude cloud sessions)
- Greek base text: **SBL Greek New Testament** (Greek only; no English translation is ever consulted).
- GitHub cloning is blocked in the sandbox; fetch chapters via WebFetch on
  `https://raw.githubusercontent.com/LogosBible/SBLGNT/master/data/sblgnt/text/Matt.txt`
  (other books: same directory, e.g. `Mark.txt`, `Luke.txt`, `1Cor.txt`...). Ask for verbatim reproduction of a verse range per call (a chapter at a time works well).
- Strip text-critical sigla ⸂ ⸃ ⸀ and verse refs; join into continuous prose.

## Honesty notes (agreed with Noah)
- No AI can literally have "never seen" English Bibles; the method is to render from the Greek with ordinary-usage checks, not to run a blocklist.
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
| υἱὸς τοῦ ἀνθρώπου | the son of humanity |
| θάλασσα (of Galilee) | the lake |
| Δεκάπολις | the Ten Towns |
| διαθήκη | agreement |
| ἄφεσις ἁμαρτιῶν | letting go of errors |
| πειρασμός | the test (never "temptation") |
| σταυρόω | put on a stake / put on an execution stake |
| ῥαββί | Teacher |
| κορβανᾶς | gift-fund |
| βῆμα | platform |
| πραιτώριον | headquarters |
| ὄξος | sour wine |
| κουστωδία | guard detail |
| ἀργύρια | silver pieces |

## Attention patterns — learned from Noah's reviews; apply PROACTIVELY to every new page

1. **Register check.** If an English word would sound bookish or rare in spoken conversation today, replace it with common speech (done: "He is my delight" → "I am very pleased with him"; "infants" → "small children"). Test: would you say it aloud to a friend? If not, re-render.
2. **Latent sacral load (soft).** When a traditional rendering would be jargon rather than a fair literary translation of the Greek, prefer ordinary English or add a lexicon tip. This is judgment from the Greek, not a forbidden-word list — if the ordinary literary English for that Greek happens to be a familiar "Bible word," that is allowed.
3. **Ambiguous English.** When a rendering is ambiguous in English but the Greek is not ("right time" — kairos = due/appointed moment, not moral rightness), add a tip and consider rephrasing.
4. **Tips required for:** every personal name; every place name; historical figures and institutions; objects and measures of daily life (coins, nets, baskets, furnaces); idioms and Semitic style markers ("and look —" = kai idou); words whose Greek social value differs from English (tapeinos = low as insult → self-praise); and forward/backward cross-references between pages (Beelzeboul on p20 ↔ trad. ch. 12).
5. **Lexicon key hygiene.** Keys must not over-match (the bare key "right" wrongly hit "right eye/cheek"; "and look" wrongly hit "and look down"). Prefer phrase keys; every key must resolve only where the intended Greek is present. After new tips, re-check for false positives.
6. **Natural grammar.** No stiff calques, even in repeated formulas (metanoia: imperative "Change the way you think", noun "change of mind").
7. **Consistency.** Identical Greek gets identical English across pages (eudokēsa at trad. 3:17 must match 17:5; the two furnace refrains in ch. 13 match word for word).
8. **Capitals.** Title-as-name rule only (Master, God as name-substitutes) — confirmed by Noah; manuscripts are all-uncial and force nothing.
9. **Per-installment checklist:** Greek fidelity (literary, not interlinear); sigla strip; page word counts ~200–430; sequential numbering; every lexicon key resolves in the text and only on pages with the matching Greek; rebuild koinos_data.js + koinos_reader.html; git commit (lock workaround: mkdir -p _to_delete, mv *.lock into it before/after); sync project docs.

## Formatting rules
- No chapter/verse numbers, no headings. Natural paragraphs; ~300–400 English words per page.
- Each book opens with a summary: composition date estimate, earliest surviving copies, where found.
- JSON schema: project / subtitle / introduction / translation_principles / lexicon / manuscripts[{name, summary, pages[{page, greek, english}]}].
- Lexicon keys = lowercase surface word or phrase as it appears in the English.

## Status (2026-07-28)
- **Matthew complete: pages 1–71, lexicon 235.** Continuous prose from the family record through the empty tomb and the Galilee commission. No chapter/verse numbers; Greek + English paired per page.
- Installment map (traditional ranges only for editor navigation — not printed in the book):
  - 1: family record → first Galilee tour (1:1–4:25) = p1–6
  - 2: hillside teaching (5:1–7:29) = p7–15
  - 3: healings, storm, paralyzed man, Matthew's calling (8:1–9:38) = p16–20
  - 4: sending of the twelve, John's question, town woes (10:1–11:30) = p21–25
  - 5: rest-day disputes, Beelzeboul, Jonah sign, comparison collection (12:1–13:58) = p26–32
  - 6–7: Herod, feedings, lake walk, tradition, Canaanite woman, confession, appearance changed (14–17) = p33–39
  - 8: children, assembly discipline, unforgiving slave, rich man (18–19) = p40–43
  - 9: vineyard workers, ransom, entry, money-changers, cornerstone (20–21) = p44–48
  - 10: wedding feast, Caesar's coin, rising, seven "How terrible" sayings (22–23) = p49–53
  - 11: temple prediction, great distress, ten young women, chests of silver, sheep and goats (24–25) = p54–59
  - **12: arrest, trial, death, burial, empty tomb, commission (26–28) = p60–71; lexicon 235**
- Installment 12 fixed / new renderings: διαθήκη → agreement; ἄφεσις ἁμαρτιῶν → letting go of errors; πειρασμός → the test; σταυρόω → put on a stake; ῥαββί → Teacher; κορβανᾶς → gift-fund; βῆμα → platform; πραιτώριον → headquarters; ὄξος → sour wine; κουστωδία → guard detail; ἀργύρια → silver pieces; Γεθσημανί / Γολγοθᾶ / Καϊάφας / Πιλᾶτος / Βαραββᾶς as place/person tips.
- Lexicon key hygiene pass: rekeyed orphans to surface English — `tie up` / `untie`, `two-drachma temple tax`, `donkey-mill stone`, `gnat` (was `gnat and camel`).
- Verified: JSON valid; pages 1–71 sequential with no duplicates; sigla stripped; every lexicon key resolves in the English with no false-positive over-matches; page sizes ~200–440 English words.
- Lexicon hygiene pass (2026-07-28): fixed over-matching tips (e.g. "and look" ≠ "look down"; ἀμήν ≠ bare "Truly"; τέλειος ≠ πληρῶσαι "complete"); rekeyed several entries to surface phrases.
- Reader: `index.html` + `koinos_data.js` (double-clickable); `koinos_reader.html` self-contained rebuild whenever data changes. Mobile-first; GitHub Pages ready (`.nojekyll`, relative paths).
- Greek source pipeline: SBLGNT per-chapter XML at `https://raw.githack.com/aaronshaf/sblgnt/master/xml/Matt/0NN.xml` (zero-padded). Reconstruct continuous prose from `<w>` + `<suffix>` only — never consult English translations. Whole-book `.txt` mirrors truncate around trad. ch. 9.
- **Next:** Mark (same method), or a full consistency pass across Matthew (identical Greek → identical English, furnace refrains, eudokēsa, etc.).
- WebFetch note: the fetch model occasionally refuses verse ranges as "copyright"; retry with smaller ranges and a note that the Greek text is an ancient public-domain-era text — that has worked every time.
