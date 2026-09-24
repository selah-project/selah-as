# NOTES — selah-as, আসন ৮৪

*এই ফাইলে অনুবাদটো য'ত হাতে বা কোনো সিদ্ধান্তে চুইছে সেই ঠাইবোৰ
ধৰি ৰাখে — কঠিন পদ, ৰায়, আৰু এতিয়াও মুকলি হৈ থকা কথা। তলৰ
লেখাবোৰ ইংৰাজীত, কাৰণ আসনবোৰৰ সৰ্বসাধাৰণ অনুশাসন ইংৰাজীত চলে;
পাঠকৰ দলিল (`README.md`, `CONTRIBUTING.md`, `LICENSE.md`) অসমীয়াতে
আছে।*

Lit 2026-09-19 (selah `b1c08282`), chair 84. Corpus first-pass commit
2026-09-20 (`f5650ecb`). Floor 23,213 verses.

The **Assamese-script** chair, beside Bengali — and unlike its Nguni and
Ge'ez predecessors, this one *does* have a closed letter probe: standard
Assamese never writes Bengali `র`.

---

## Burn signature

| | |
|---|---|
| model · tier | `glm-5.3` · `glm-5.2` |
| relay | `batch/relay-move-on! [:as]`, engine-side |
| burn | 2026-09-19 → 09-20, relay + the gleaning ladder |
| final | **23,213 / 23,213 verses · 305,507 token rows** |

## The Name

Assamese Bibles print **যিহোৱা** and **প্ৰভু**. This chair writes
**ইয়াহৱেহ**, and keeps D1 for the rest: এলোহিম · আদোনাই · শ্বাদ্দাই ·
ইয়াহ · এল · এলোৱাহ · চেভাওত.

The Assamese script carries all four letters of יהוה — **ইয়া** (י)
**হ** (ה) **ৱে** (ו) **হ** (ה) — so the final হ is written, as at the am
and ti chairs. The /w/ of ו is written with Assamese **ৱ**, not Bengali `ওয়`:
at this chair **the Name itself carries the script's own mark**. ইয়াহৱে
without the final হ is a slip, not an erasure, and is repaired.

প্ৰভু keeps its lawful seat over a human lord and lowercase দেৱতা over
the nations' gods; the token's Hebrew surface applies that distinction,
never the spelling.

## The thermometer

**One closed letter probe, and it is the script's own.** Bengali `র`
(U+09B0) in the flow — inside ⟨ ⟩ too — is a defect, no whitelist
needed. ৰ (U+09F0) and ৱ (U+09F1) are Assamese-only, but their *absence*
proves nothing. ব, ও, ড়, ঢ় are shared and are never counted. Latin
letters, Devanagari letters, and Hebrew outside the ⟨את⟩ family are the
other closed probes.

For the Bengali words that carry no `র`, the rule is **whitelist
first — whole words only**. `dev/scripts/as_gate.clj` (`fafd32d4`)
passed its first hour: Gen 1:1 verbatim, ইয়াহৱেহ ~98%, no Bengali. Four
collisions were struck on the gate's first read, and each is the
whitelist-first lesson:

- **এটা** and **এখন** — Assamese *one* plus a classifier.
- **ও** — the Assamese enclitic `-ও`; counted only standing alone
  between nouns.
- **the danda (।)** — struck out of the Devanagari probe; it is Assamese
  punctuation.

The two load-bearing never-count words are **আমি** (Assamese *we*,
Bengali *I* — Gen 1:26's plural is আমি; counting it would punish the
plural the rails exist to protect) and **তিনি** (Assamese *three*,
Bengali honorific *he*).

## State — a read taken 2026-09-24, not a census

**No census has been run on this chair, and no hand pass.** The
first-pass commit named two things as known, and both are addressed
below. What follows was counted at the writing of these files.

| | |
|---|---|
| verses · token rows | 23,213 · 305,507 |
| rows whose Hebrew surface carries יהוה | 6,828 |
| of those, reading **ইয়াহৱেহ** | **6,664** — 164 open, classed below |
| flows carrying Bengali `র` | 24 |
| flows carrying Latin letters | 561 — 544 only inside ⟨supplied-word⟩ brackets |
| flows carrying Hebrew outside the marker family | 76 |
| bare ⟨את⟩ in the flows | 9,385 |

## The one mechanism

This chair's defects are not a list. They are **one behaviour**: it
splices a letter from another script it holds into the middle of a word,
and stops partway. The first-pass commit already named it —
*"~2% of Name seats carry a foreign ה/ह inside ইয়াহৱেহ"* — and the count
bears it out exactly.

**164 Name seats do not read ইয়াহৱেহ**, and they class cleanly:

| class | count | what stands there |
|---|---|---|
| a foreign letter spliced inside the Name | **133** | Hebrew ה ×114 · א ×13 · ו ×2 · Latin `Yahweh` ×4 |
| য়াহৱেহ — the initial ই lost | 18 | য়াহৱেহ, য়াহৱেহে, য়াহৱেহৰ |
| ইয়াহ্বেহ — ৱ written হ্ব | 6 | the Bengali habit for /w/ |
| tradition in the Name's seat | 4 | `2-chronicles/5/7` · `2-kings/18/15` · `2-kings/18/16` (যিহোৱাৰ / যিহোৱাহৰ) |
| a wrong transliteration | 2 | `2-kings/12/5` — য়েহৱেহৰ, twice |
| the gloss empty | 1 | `jeremiah/35/13` |
| the gloss displaced | 1 | `proverbs/3/7` — ভয় কৰা on a יהוה row |

Only **four** of the 164 are erasure. The rest is the splice, which is
why a word list would never have found them: the Name *looks* right.

**The marker shows the same mechanism.** Alongside 9,385 bare ⟨את⟩ the
flows carry:

- **82 mixed-script markers** — ⟨אত⟩ ×29 (Hebrew alef, Assamese ta),
  ⟨আת⟩ ×21 (Assamese a, Hebrew tav), ⟨מאত⟩ ×8, and stragglers. The
  marker arrives **partly converted** — the lesson the ug chair taught,
  and the reason a count of the bare form alone reads them as absent.
- **27 transliterated markers** — ⟨আত⟩ ×26 and ⟨এট⟩ ×1, which the rails
  forbid outright.
- **14 truncated** — ⟨א...⟩.
- the inflected family: ⟨ואת⟩ 527 · ⟨אתם⟩ 116 · ⟨אתו⟩ 109 · ⟨אתכם⟩ 58 ·
  ⟨אותם⟩ 52 · ⟨מאת⟩ 14. That is the fleet's standing question, not this
  chair's defect.

**561 flows carry Latin**, and 544 of them only inside a
⟨supplied-word⟩ bracket — English left untranslated (`the` ×463, `is`
×141), the lesson the tw chair taught. The other 17 are bare splices:
`2-kings/1/9` and `1/11` carry `<the king>` in ASCII angle brackets, and
`2-chronicles/10/19` reads `ঘৰante্বিৰুদ্ধে` — Latin inside an Assamese
word, the same mechanism in a third place.

## Cruxes

**`exodus/19/23` — the surface that was overwritten, and the marker the
flow lost.** The gate reported a corrupt surface here on 2026-09-19.
Opened, it was the **whole Hebrew row written in Assamese letters,
হোৱেহ where יהוה stands** — in the verse that says *the people cannot
go up … set a boundary ⟨את⟩ the mountain and sanctify it* — and the flow
had lost that very ⟨את⟩.

The Hebrew surface **has been restored** from the record by the fleet's
`surface_restore` (`1f66279e`); the row now reads יהוה → ইয়াহৱেহক. The
**flow still carries no ⟨את⟩**, and it is left for a re-press rather
than guessed: the marker is written only where the Hebrew proves the
placement. The verse is a crux in its own right — see
`docs/charge/the-roar-and-the-breaker.md` §206 and experiment 824
(יפרץ ×3 · וקדשתו ×2 · הגבל ×4).

## The passes this repo carries

| commit | pass |
|---|---|
| `f5650ecb` | first pass, 23,213 / 23,213, committed before anything touched it |
| `1f66279e` | surfaces restored to the floor's Hebrew (the fleet's `surface_restore`); a second run reports zero |
| `c3638626` | present-but-wrong verse files pruned for the relay to refill |
| `806e209b` | the pruned verses refilled; surfaces restored again |

## Held for a native ear

Assamese is not the writer's language, and the rails say so and are
**not yet signed**. The whole review list lives at the bottom of
`docs/methodology/translation-discipline/as.md`; the load-bearing items:

- **The closed probe itself** — that standard Assamese has no lawful use
  of `র` (quoted Bengali, older printing, loanword conventions).
- **D1 spellings** — ইয়াহৱেহ (that ইয়া-, not য়া- / যা-, is right for
  /ya/), এলোহিম, এল, এলোৱাহ, আদোনাই, শ্বাদ্দাই, ইয়াহ, চেভাওত. The
  **শ্ব for ש** convention (as in শ্বিলং) is inferred, since native শ is
  /x/; চ for צ and soft ব → ভ likewise.
- **Which forms the Assamese Bible actually prints** — যিহোৱা and ঈশ্বৰ
  are believed, সদাপ্ৰভু listed defensively.
- **Proper names** — word-initial য় is unusual; a reader may prefer
  ইয়াকোভ, ইয়েৰুশ্বালায়িম over য়াকোভ, য়েৰুশ্বালায়িম.
- **D3 terms** — হেচেদ, শ্বেওল, মাশ্বিয়াহ, তোৰা, শ্বাব্বাত are
  constructed. That মচীহ is the church title, that বিশ্ৰামবাৰ is the
  Bible's Sabbath word, and that চুক্তি should replace নিয়ম for ברית all
  need confirming.
- **Thermometer pairs** — `ও` standing alone, `নয়`, `মধ্যে`, `জন্য`,
  `খুব`, `সব`, `দশ`; and the grammar signals (-লেন, -টা, -কে), which
  are textbook contrasts untested on output.
- **The D4 audience paragraph** — its namghar/satra Vaishnava framing is
  the writer's, and should be read by someone who knows the community.
- **The coinages** — বন্ধ পৰীক্ষা (closed probe), কোমল চিন (soft
  signal), অনুমোদিত শব্দৰ তালিকা (whitelist), গ্লছ, কোদাল (shovel),
  সাক্ষীৰ স্তম্ভ (witness column) — and whether any Bengali has leaked
  into the rails' own Assamese prose.

## Next

Census (the Name classes above, Bengali whole words, the `র` probe,
foreign scripts), then one re-press carrying the 164 Name seats, the 109
damaged markers, the Latin-in-brackets class, and `exodus/19/23`'s lost
⟨את⟩ together.
