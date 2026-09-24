# PROVENANCE — how this rendering came to be

*Assamese, chair 84. Lit 2026-09-19. Floor 23,213 verses.*

This is the record of how the text in this repository was produced and
what went wrong with it. A machine-assisted rendering has no standing
unless you can see how it was made, so this file says both.

---

## The approach

Every verse is rendered from the Hebrew of that verse, under a written
discipline — `docs/methodology/translation-discipline/as.md` in the
Selah repository, itself written in Assamese, following the structure of
`xh.md` and `ti.md`, taking its name-form precedent from `bn.md` and
`hi.md` and its SOV rule from `am.md` and `ti.md`. Eight rules govern
it: the Hebrew letters pass letter by letter; the Name stays the Name; a
double faithfulness to Deut 6:4 (add no doctrine, flatten no plural); no
foreknowledge (Gen 22:1 does not know Gen 22:13); the Tanakh's own
vocabulary only; the four registers; numbers and marks stay put; and the
translator has no note of its own.

**Word order is Assamese, alignment is Hebrew's.** Assamese puts the
verb last; Hebrew often puts it first. So the `tokens` row holds Hebrew
order strictly, one gloss per token, while the assembled `translation`
obeys Assamese grammar — including the ergative **-এ** on a transitive
subject (এলোহিমে সৃষ্টি কৰিলে) and **-ক** on an animate object
(আভ্ৰাহামক)। Those are grammar; the Name's stem stays whole.

**The `⟨ ⟩` brackets do two different jobs.** `⟨את⟩` is the Hebrew
direct-object marker, which Assamese has no word for; it is left
standing so the reader sees it. `⟨শব্দ⟩` is a word Hebrew did not write
but Assamese grammar requires — visibly marked, so you can always tell
what the Hebrew said from what the grammar needed.

## The fight on this chair is the Name

| Hebrew | here | rejected |
|---|---|---|
| יהוה | **ইয়াহৱেহ** | যিহোৱা, প্ৰভু, সদাপ্ৰভু, ঈশ্বৰ / পৰমেশ্বৰ in the Name's place, ভগৱান |
| אלהים | **এলোহিম** | ঈশ্বৰ in the Name's place, আল্লাহ |
| אדני | **আদোনাই** | প্ৰভু, প্ৰভু যিহোৱা |
| שדי | **শ্বাদ্দাই** | সৰ্বশক্তিমান alone |
| אל | **এল** | ঈশ্বৰ / দেৱতা as a type-name |
| צבאות | **চেভাওত** | "of hosts" as a substitute |

The Assamese script carries all four letters of יהוה — ইয়া י · হ ה ·
ৱে ו · হ ה — so the final হ is written, matching the am and ti chairs.
The /w/ of ו takes Assamese **ৱ**, not the Bengali `ওয়` that the bn
chair uses: at this chair the Name itself carries the script's own mark.

প্ৰভু over a human lord and lowercase দেৱতা for the nations' gods remain
lawful; the census applies that distinction by the token's Hebrew
surface, never by spelling. For the sacred Name, the Vaishnava words
(*হৰি*, *ভগৱান*, *গোবিন্দ*) are never used — this chair's remnant grew
up with নামঘৰ and সত্ৰ, where *নাম* itself carries devotional weight,
and the rails say so in their own register section.

## The burn and the gate

The relay and the gleaning ladder brought the corpus to 23,213 of 23,213
across 2026-09-19 → 09-20. A first-hour gate (`dev/scripts/as_gate.clj`,
`fafd32d4`) — the Name, the closed `র` probe, Bengali whole words,
Latin, Devanagari — passed: Gen 1:1 verbatim, ইয়াহৱেহ at ~98%, no
Bengali.

The corpus was committed to git **as its first pass** (`f5650ecb`), with
the two known defects named in the commit message, so every repair below
is a diff you can read.

## Finding: this chair has a letter that proves the neighbour

Every chair before this one in the Indic and Ge'ez families had to work
by vocabulary alone. Here one letter closes the question: standard
Assamese never writes Bengali **`র`** (U+09B0); it writes **ৰ**
(U+09F0), and **ৱ** (U+09F1) for /w/ where Bengali writes `ওয়` or `ব`.
So a single `র` anywhere in the flow — inside a ⟨ ⟩ bracket too — is the
neighbour, and no whitelist is needed, because it is a letter and not a
word.

The probe is exact in one direction only. ৰ and ৱ *present* prove
Assamese; ৰ and ৱ *absent* prove nothing. And ব, ও, ড়, ঢ় are shared
and are never counted — ড় and ঢ় are ordinary Assamese (পঢ়া, বাঢ়ি).
For Bengali words carrying no `র`, the rule is the fleet's:
**whitelist first, whole words only**. The gate's first read struck four
collisions — **এটা** and **এখন** (Assamese *one* plus a classifier),
**ও** as the enclitic `-ও`, and the **danda** out of the Devanagari
probe. Two words sit permanently on the never-count list, and they are
the ones a naive gate would have punished hardest: **আমি**, which is
Assamese *we* and Bengali *I* — Gen 1:26's plural is আমি, and counting
it would punish the plural the rails exist to protect — and **তিনি**,
Assamese *three* against Bengali's honorific *he*.

## Finding: the one mechanism — a letter from the wrong script, mid-word

The first-pass commit named it before any census: *~2% of Name seats
carry a foreign ה/ह inside ইয়াহৱেহ*. Counted, that is **133 of the 164
Name seats that do not read ইয়াহৱেহ** — Hebrew ה ×114, א ×13, ו ×2, and
Latin `Yahweh` ×4 — a foreign letter spliced into the middle of the
Name, everything around it correct. Only **four** of the 164 are
tradition in the Name's seat. The defect that looked like erasure was
almost entirely orthographic substitution, and the Name *looks* right,
which is why a word list would never have found it.

The same mechanism sits on the marker. Alongside 9,385 bare ⟨את⟩ the
flows carry **82 mixed-script markers** — ⟨אত⟩ ×29 (Hebrew alef,
Assamese ta), ⟨আת⟩ ×21 (Assamese a, Hebrew tav), ⟨מאת⟩ ×8 — plus **27**
fully transliterated (⟨আত⟩ ×26, ⟨এট⟩ ×1, which the rails forbid
outright) and **14** truncated. The marker does not arrive in one wrong
form; it arrives **partly converted**, exactly as at the ug chair, and a
count of the bare form alone reads every one of them as absent.

And it reaches Assamese words too: `2-chronicles/10/19` reads
`ঘৰante্বিৰুদ্ধে`, Latin inside an Assamese word, and `2-kings/1/9` and
`1/11` carry `<the king>` in ASCII angle brackets. Of the 561 flows with
Latin letters, 544 are English left untranslated *inside* a
⟨supplied-word⟩ bracket (`the` ×463, `is` ×141) — the lesson the tw
chair taught — and 17 are bare splices.

## Finding: the surface the chair overwrote, in the verse about the boundary

The gate reported a corrupt surface at `exodus/19/23`. Opened, it was
the **whole Hebrew row written in Assamese letters, হোৱেহ where יהוה
stands** — and the verse is the one that says *the people cannot go up …
set a boundary ⟨את⟩ the mountain and sanctify it*. The flow had lost
that very ⟨את⟩.

The surface has been restored from the record (`1f66279e`) and the row
now reads יהוה → ইয়াহৱেহক. The flow's marker is **not** restored: it is
written only where the Hebrew proves the placement, and here it did not,
so nothing was written. The verse is a crux in the project's own reading
as well — `docs/charge/the-roar-and-the-breaker.md` §206, experiment 824.

## The cure, in order

| pass | what |
|---|---|
| relay + gleaning ladder | 23,213 of 23,213 (`f5650ecb`) |
| surface restore | the floor's Hebrew back in `surface`; second run zero (`1f66279e`) |
| prune | present-but-wrong verse files removed for the relay to refill (`c3638626`) |
| refill | the pruned verses re-rendered; surfaces restored again (`806e209b`) |

`surface` is the Hebrew record and not the chair's to write. Where the
chair had written into it, the floor was authoritative.

## Open — declared, not repaired

- **No census has been run on this chair**, and no hand pass. The counts
  in `NOTES.md` are a read taken 2026-09-24, at the writing of these
  files.
- **164 Name seats** — 133 splices, 18 missing the initial ই, 6 with
  ৱ written হ্ব, 4 tradition, 2 mis-transliterated, 2 hollow.
- **109 damaged markers** (82 mixed-script, 27 transliterated) and 14
  truncated; plus the inflected family (⟨ואת⟩ 527 · ⟨אתם⟩ 116 · …),
  which is a fleet question, not a chair defect.
- **24 flows carrying Bengali `র`** — the closed probe convicts them.
- **561 Latin flows**, 544 of them English inside ⟨ ⟩ brackets.
- **`exodus/19/23`'s lost ⟨את⟩.**
- **A native ear.** Assamese is not the writer's language and the rails
  are not yet signed; `NOTES.md` names the load-bearing items, including
  the closed probe's own premise.

## Final

**23,213 / 23,213 verses · 305,507 token rows.** ইয়াহৱেহ in **6,664 of
6,828** Name seats, with the 164 above classed and declared. Read it
alongside the Hebrew.
