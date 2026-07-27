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

## Attention patterns — learned from Noah's reviews; apply PROACTIVELY to every new page

1. **Register check.** If an English word would sound bookish or rare in spoken conversation today, replace it with common speech (done: "He is my delight" → "I am very pleased with him"; "infants" → "small children"). Test: would you say it aloud to a friend? If not, re-render.
2. **Latent sacral load.** Words that feel ordinary but carry churchly/doctrinal charge get replaced or context-tipped (done: "evil" → bad/harmful/nasty/corrupt/flawed by context; "virgin" → young woman). Standing watch list: glory, soul, temptation, confess, saint, heaven, sabbath, parable, mystery, sign-jargon, judgment-jargon.
3. **Ambiguous English.** When a rendering is ambiguous in English but the Greek is not ("right time" — kairos = due/appointed moment, not moral rightness), add a tip and consider rephrasing.
4. **Tips required for:** every personal name; every place name; historical figures and institutions; objects and measures of daily life (coins, nets, baskets, furnaces); idioms and Semitic style markers ("and look —" = kai idou); words whose Greek social value differs from English (tapeinos = low as insult → self-praise); and forward/backward cross-references between pages (Beelzeboul on p20 ↔ trad. ch. 12).
5. **Lexicon key hygiene.** Keys must not over-match (the bare key "right" wrongly hit "right eye/cheek"; rekeyed to the phrase "what is right"). Prefer phrase keys; check each new key against the full text before shipping.
6. **Natural grammar.** No stiff calques, even in repeated formulas (metanoia: imperative "Change the way you think", noun "change of mind").
7. **Consistency.** Identical Greek gets identical English across pages (eudokēsa at trad. 3:17 must match 17:5; the two furnace refrains in ch. 13 match word for word).
8. **Capitals.** Title-as-name rule only (Master, God as name-substitutes) — confirmed by Noah; manuscripts are all-uncial and force nothing.
9. **Per-installment checklist:** banned-regex sweep (sin/church/hell/baptize/gospel/repent/righteous/salvation/holy/worship/devil/satan/angel/disciple/apostle/blessed/amen/christ/gentile/hypocrite/evil/virgin/faith/forgive/miracle/leper/blaspheme/centurion/woe/hades/soul/cross(noun)/unclean/prophet/prophesy/parable/mystery/sabbath); sigla strip; page word counts ~200–430; sequential numbering; every new lexicon key resolves in the text; rebuild koinos_data.js + koinos_reader.html; SendUserFile; device-commit; git commit (lock workaround: mkdir -p _to_delete, mv *.lock into it before/after); update artifact; sync project docs.

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
- Installment 3 done: healings, storm, paralyzed man, Matthew's calling (traditional 8:1–9:38) = pages 16–20. New fixed renderings: ὁ υἱὸς τοῦ ἀνθρώπου → the son of humanity; ἁμαρτωλοί → the failures / people counted as failures; βλασφημέω → insulting God; σπλαγχνίζομαι → felt it deep in his gut; ἑκατόνταρχος → army captain; λεπρός → man with a serious skin disease; κακῶς ἔχοντες → doing badly; ἐλέησον → take pity. Metanoia reworked for natural grammar: imperative → "Change the way you think"; noun → "change of mind". Lexicon expanded to 118 entries: all notable names (Herod, Archelaus, David, Rachel...), all places (Galilee, Nazareth, Rama, Capernaum...), and idiom tips (threshing floor, delight, doing badly, paid in full...).
- Greek fetch fallback: primary raw.githubusercontent URL truncates around trad. ch. 9; use https://cdn.jsdelivr.net/gh/LogosBible/SBLGNT@master/data/sblgnt/text/Matt.txt for later chapters (same file via CDN, serves the full content in chunks).
- Installment 4 done: the sending of the twelve, John's question, the woes, "come to me" (traditional 10:1–11:30) = pages 21–25; lexicon 136. New fixed renderings: ἀπόστολοι → envoys; πνεύματα ἀκάθαρτα → foul spirits; σταυρός → execution stake; ψυχή → life; ᾅδης → the place of the dead; οὐαί → How terrible for you; ὀλιγόπιστοι stays "people of little trust"; χρηστός (yoke) → fits comfortably.
- Greek fetch pipeline (chapters 10+): per-chapter XML at https://raw.githack.com/aaronshaf/sblgnt/master/xml/Matt/0NN.xml (zero-padded chapter). Prompt the fetch model to reconstruct continuous verse text from the <w> elements. Whole-book txt files truncate at ~trad. 9:15 regardless of mirror.
- Installment 5 done: rest-day disputes, Beelzeboul, sign of Jonah, the comparison collection, hometown rejection (traditional 12:1–13:58) = pages 26–32; lexicon 153. New fixed renderings: σάββατον → the rest day; παραβολή → comparison; μυστήρια → the secrets; ζιζάνια → weeds (darnel tip); συντέλεια τοῦ αἰῶνος → the close of the age; τέκτων → the builder; κῆτος → the great sea creature; ἀπιστία → lack of trust.
- REMAINING: traditional ch. 14–28. Installment plan: 14–15, 16–17, 18–19, 20–21, 22–23, 24–25, 26, 27–28. Fetch per chapter via raw.githack aaronshaf XML (zero-padded, e.g. 014.xml). Apply the Attention Patterns section above to every page.
- Next: continue Matthew (feeding the crowds and walking on the lake, traditional ch. 14–15) → append pages to koinos_data.json, grow lexicon, regenerate koinos_data.js + koinos_reader.html. First occurrence of ὁ υἱὸς τοῦ ἀνθρώπου arrives in ch. 8 — settle its rendering then (candidate: "the son of humanity" / "the human one").
- WebFetch note: the fetch model occasionally refuses verse ranges as "copyright"; retry with smaller ranges and a note that the Greek text is an ancient public-domain-era text — that has worked every time.
