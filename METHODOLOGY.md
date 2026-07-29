# The Koinos Project — Working Methodology & Status

## Goal

An English rendering of the Greek New Testament that a careful modern reader can meet as **ancient literature in ordinary words** — continuous prose, no chapter or verse numbers, Greek and English paired per page, with a clickable lexicon (Greek form, ordinary range, one secular or period usage note).

This is a **specialized literary reconstruction**, not a claim to be the only true translation. Every translation is a theory. Ours is stated below so it can be followed, challenged, and improved.

---

## What this method is (and is not)

### It is
- **Greek-first.** English Bibles are not consulted as sources or models. The base is the Greek text and ordinary usage of Koine (and, where the Greek forces it, Jewish Greek / LXX resonance).
- **Period-oriented.** Prefer what first-century speakers could get from the words in ordinary use, not what later ecclesiastical English made of them.
- **Literature-shaped.** Continuous prose, natural paragraphs, modern spoken register where the Greek is ordinary speech.

### It is not
- A **banned-word police list.** If ordinary English for that Greek happens to be a familiar “Bible word,” that English is allowed.
- A claim of **innocent ears.** Translators (and models) have heard traditional English. The safeguard is Greek + usage + stated rules, not purity of mind.
- A claim that **one hearer** stood for the whole ancient world. See “Who is listening?” below.
- A claim that **secular shop-Greek** exhausts every line. These authors also write inside Jewish scripture and Jesus-movement argument. See “Two layers of meaning.”

---

## Who is listening? (compromise on the single-hearer problem)

There was no single first-century audience. A pagan in Corinth, a Greek-speaking Judean steeped in the LXX, and a Pharisee’s student could hear the same sentence differently.

**Working compromise — two default ears, in order:**

1. **Primary ear: non-specialist Greek speaker**  
   What would the plain vocabulary mean in ordinary Koine (contracts, letters, histories, medical prose)? This is the default gloss.

2. **Secondary ear: Greek-speaking Judean**  
   When the Greek itself is Hebraizing, cites or echoes scripture, uses loanwords (*pascha*, *satana*, *amēn*), or depends on LXX usage, allow that resonance in the English **or** in a lexicon tip. Do not invent later Christian dogma; do not erase Jewish Greek either.

**Rule of thumb:**  
Start with ordinary Greek sense. Add Jewish/scriptural color only when the **Greek wording or context** forces it — not when later tradition wants it.

---

## Two layers of meaning (compromise on “flattening”)

| Layer | Question | English should… |
|---|---|---|
| **A. Lexical** | What did this word normally mean? | Carry ordinary range (assembly, immerse, trust, messenger…). |
| **B. Discourse** | What is this author doing with it here? | Allow argument, echo, and idiom the Greek is performing — without importing post-biblical theology as if it were vocabulary. |

**Failure modes to avoid:**
- **Over-secularizing:** stripping every word to shop-Greek until the text cannot mean what a Judean hearer would have heard from *this* Greek.
- **Over-sacralizing:** using later English jargon (*sin*, *church*, *gospel* as genre labels, *faith* as belief-system) as if that were first-century vocabulary.
- **Anti-church reflex:** choosing a gloss because it debunks tradition, not because it fits the Greek. Period fit beats polemical fit.

---

## English as a target language (compromise on “ordinary modern English”)

Ordinary modern English is still a choice with its own connotations. We are not a transparent window onto 30 CE; we are building a **readable modern literary English** that tracks period sense as closely as natural speech allows.

**Priorities, in order:**
1. **Period sense** of the Greek (layers A–B above).
2. **Natural modern English** you would say aloud — not stilted calque, not interlinear.
3. **Consistency** of defaults (glossary) so the book coheres.
4. **Pedagogy** (lexicon tips) where English cannot carry the full range.

When (1) and (2) conflict: prefer natural English **plus a tip**, rather than an ugly calque that only a glossary can love. When (1) and (3) conflict: allow **context-bound variants** (see glossary rules).

---

## Source text (honesty about “the Greek”)

- Base: **SBL Greek New Testament** (modern critical edition; Sinaiticus, Vaticanus, papyri among witnesses).
- Sigla stripped; no verse numbers in the reading text; continuous prose.
- This is already a reconstructed text, not a single first-century autograph. State that in book intros/manuscript notes; do not pretend otherwise.

### Fetch pipeline
- Prefer per-chapter XML: `https://raw.githack.com/aaronshaf/sblgnt/master/xml/Matt/0NN.xml` (zero-padded chapter). Rebuild continuous prose from `<w>` + `<suffix>` only.
- Whole-book `.txt` mirrors often truncate around trad. ch. 9; do not rely on them for later chapters.
- If a fetch refuses a range, retry smaller chunks and note that the Greek is public-domain ancient text.

**Never consult English Bible translations** as rendering models. Secular Greek parallels and ordinary-usage checks are allowed.

---

## Decision ladder (use on every hard word)

For each contested Greek item, walk this ladder and stop at the first adequate step:

1. **Ordinary Koine range** (dictionaries + secular authors + papyri).
2. **This author’s immediate context** (same page / argument).
3. **Jewish Greek / LXX** only if the wording or citation structure invites it.
4. **English that a non-specialist can say aloud** without sounding like a tract or a textbook.
5. **Lexicon tip** for residue (names, measures, idioms, double senses, loans).
6. **Glossary default** if nothing in 1–5 forces a variant.

If a traditional English “Bible word” wins at steps 1–4, use it. If only tradition wants it, do not.

---

## Fixed glossary — defaults, not handcuffs

Defaults keep the book consistent. They are **starting points**, not a vow.

### Consistency rule (softened)
- Prefer the same English for the same Greek **in the same sense**.
- When context clearly shifts the sense (e.g. πνεῦμα as wind vs breath vs animating spirit; βασιλεία as reign vs territorial kingdom; κύριος as sir vs divine Master), **change the English** and, if helpful, tip the range.
- Repeated formulas that are intentionally identical in Greek (e.g. the two furnace refrains; εὐδόκησα) should stay identical in English.

### Core defaults

| Greek | Default English | Notes |
|---|---|---|
| ἁμαρτία | error, failure | miss / fault; not later “sin” system-language unless English truly needs it |
| ἁμαρτωλός | failure(s) | people counted as missing the mark |
| ἐκκλησία | assembly | civic “called gathering”; not “church” as institution |
| βαπτίζω / βαπτιστής | immerse / the Immerser | action-word, not sacrament name |
| εὐαγγέλιον | good news | report of good; not “Gospel” as genre label |
| Χριστός | the anointed | title/description; not untranslated *Christ* as default name |
| κύριος | Master (God); master / sir (people) | hierarchical address; title-as-name capitals OK |
| ἄγγελος | messenger | human or divine; tip when clearly heavenly |
| πνεῦμα (ἅγιον) | breath; sacred breath | also wind / spirit by context — allow variants |
| ἅγιος | sacred | set apart; not “saint” as later office |
| μετανοέω / μετάνοια | change your thinking / change of mind | change of mind, not penitential jargon |
| βασιλεία | reign (royal rule) | **kingdom** when a territory or political unit is meant |
| βασιλεία τῶν οὐρανῶν | the reign of the skies | Judean circumlocution for God’s reign; *ouranos* = sky |
| γραμματεύς | scribe | lettered clerk / law-handler; not modern “scholar” |
| προφήτης | spokesman (for a god) | god-speaker; tip if thin in context |
| προσκυνέω | bow down before | physical prostration; “worship” only if English needs the package |
| διάβολος | the slanderer | noun of function; not automatic “Devil” mythology |
| ὁ πειράζων | the tester | |
| Σατανᾶς | adversary | loan-name meaning; tip that it is a foreign name |
| δίκαιος / δικαιοσύνη | just, fair / what is right | prefer **just** when moral-legal uprightness is clear |
| σῴζω | rescue | save-from-danger range; not “salvation” system-language |
| δόξα | splendor, reputation | context-split; “glory” allowed if ordinary English fits |
| συναγωγή | meeting hall | gathering-place; tip Jewish institution |
| δαιμόνιον | spirit | not always malevolent “demon” |
| πνεύματα ἀκάθαρτα | foul spirits | |
| μάγοι | astrologers | |
| ἔρημος | the open country | |
| πονηρός | bad / harmful / nasty / corrupt / flawed / rotten | by context; avoid cosmic “evil” unless forced |
| παρθένος | young woman | virgin only if context forces; Isaiah background is ʿalmāh |
| μακάριος | happy, fortunate |
| πτωχοὶ τῷ πνεύματι | those who are poor in breath | |
| ἀμὴν λέγω ὑμῖν | I tell you truly | translating the loan’s force; *Amen* optional as sound |
| μαθητής | student | pupil of a teacher |
| γέεννα | the burning valley (Hinnom) | place-image; not “hell” cosmology |
| ᾅδης | place of the dead / Hades | name or sense; not “hell” |
| υἱὸς τοῦ ἀνθρώπου | the human one | Semitic “human being”; not abstract “humanity” |
| διαθήκη | covenant | binding disposition / solemn compact; stronger than casual “agreement” |
| ἄφεσις ἁμαρτιῶν | letting go of errors | release of faults/debts |
| πειρασμός | the test | proving; not “temptation” as default |
| σταυρός / σταυρόω | execution stake / put on a stake | execution gear, not later holy symbol |
| ῥαββί | Teacher | or keep *Rabbi* as loan title where the Greek keeps it |
| κορβανᾶς | gift-fund | dedicated treasury |
| μαμωνᾶς | wealth | ordinary riches; avoid capital-M personification unless Greek forces it |
| λαμπάδες (procession) | torches | vs λύχνος = lamp |
| φυλακτήρια | law-boxes | written law lines bound on; not “scripture” book |
| ὑποκριτής | actor | stage-player → pretender |
| παραβολή | comparison | |
| μυστήριον | secret(s) | |
| σάββατον | the rest day | sense-gloss of the Jewish seventh day; tip the loan *sabbaton* |
| ἀπόστολος | envoy | one sent |
| πίστις | trust | reliability / credit / trust; not “faith-system” by default |
| οὐαί | How terrible for you | cry of disaster |
| τάλαντον | chests of silver | kept as value-picture (huge sum); tip the weight-unit |
| θάλασσα (Galilee) | the lake | |
| Δεκάπολις | the Ten Towns | |
| ἀργύρια | silver pieces | |
| βῆμα | platform | |
| πραιτώριον | headquarters | |
| ὄξος | sour wine | |
| κουστωδία | guard detail | |
| Capitalization | Master / God as title-as-name only | manuscripts are all-uncial; Noah: keep capitals |

---

## Attention patterns (every new page)

1. **Register.** Prefer speech you would say aloud. If a calque is accurate but unreadable, rephrase and tip.
2. **Period sense first; tradition never as authority.** Tradition may accidentally match ordinary English — that is fine.
3. **Jewish Greek when forced.** Citations, *kai idou*, loans, temple/law institutions: do not flatten.
4. **Context over glossary.** Same lemma, different sense → different English.
5. **Ambiguous English.** If English is ambiguous and Greek is not, rephrase or tip (*kairos* “right time” ≠ moral rightness).
6. **Tips for:** names, places, institutions, measures/objects, idioms, loans, social-value shifts (*tapeinos*), and double senses.
7. **Lexicon key hygiene.** Keys match surface English; no over-match (“and look” ≠ “look down”); every key resolves only where the intended Greek is present.
8. **Natural grammar.** No stiff formulas; *metanoeite* → “Change the way you think,” not wooden calque.
9. **Repeated intentional formulas** stay matched across the book.
10. **Anti-polemic check.** Before shipping a clever secular gloss, ask: is this what the Greek does, or only what debunks church English?

### Per-installment checklist
- Greek continuous prose; sigla stripped  
- Period ladder applied on hard words  
- Page size ~200–430 English words; sequential page numbers  
- Lexicon keys resolve; no false-positive tips  
- Rebuild `koinos_data.js` + `koinos_reader.html`  
- Sync this file + JSON `translation_principles`  
- Commit (lock workaround: `mkdir -p _to_delete`, move `*.lock` aside if needed)

---

## Formatting & schema

- No chapter/verse numbers, no section headings in the reading text.
- Natural paragraphs; ~300–400 English words per page as a soft target.
- Each document opens with composition estimate + earliest copies / find-spots.
- JSON: `project` / `subtitle` / `status` / `introduction` / `translation_principles` / `lexicon` / `manuscripts[{name, summary, pages[{page, greek, english}]}]`.
- Lexicon keys = lowercase surface English as printed.
- Lexicon entries: Greek + up to ~3 ordinary variants + one period/secular usage note. Where Jewish Greek matters, the note may say so briefly.

---

## Known limits (keep these visible)

1. **Audience pluralism** — we use a two-ear compromise, not a full sociology of every hearer.
2. **Critical text** — SBLGNT is a reconstruction.
3. **Modern English** — ordinary speech is still a contemporary dialect.
4. **Prior exposure** — traditional English cannot be unheard; process discipline substitutes for innocence.
5. **Glossary tension** — consistency vs context will always need judgment.
6. **This is one legitimate brief** — ordinary-language literary recovery — not the only faithful way to translate the NT.

---

## Status (2026-07-28)

- **Matthew complete: pages 1–71.** Continuous Greek/English prose through the commission; lexicon ~239.
- Period-meaning pass applied: reign of the skies; the human one; scribes; wedding torches; wealth; covenant; law-boxes; territorial *kingdom* kept where political.
- Lexicon hygiene: no orphan keys; false-positive tip pass done.
- Reader: `index.html` + `koinos_data.js`; `koinos_reader.html` self-contained rebuild on data change. Mobile-first; GitHub Pages ready.
- **Methodology revised** to the compromise above (two ears, two layers, soft glossary, anti-polemic check, stated limits).
- **Introduction rewritten** to match: sacral-pseudo critique retained; two-ear method, no banned list, critical-text honesty, stated limits; no em dashes.
- **Next:** methodology audit of Matthew against this brief, then Mark and/or consistency pass (εὐδόκησα, furnace refrains, πνεῦμα/ψυχή context splits).
