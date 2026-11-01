# LangBleu — fresh build (2026-11-01)

Free language-learning site: **50 languages**, a complete original course of
**125 lessons / 1,025 phrases** in every language, 8 vocabulary games,
pronunciation practice, local progress & account (on-device), AdSense slots.

## Files to upload (repo root, all of them)

| File | What it is |
|---|---|
| `index.html` | The whole site (design + app code) |
| `lang-img-1.jpg` … `lang-img-5.jpg` | Landmark photo sheets: 50 original images (10 per sheet), one famous place per language, shown on the home + languages photo grids |
| `data-lessons.js` | Lesson index (125 lessons, EN + FR titles) |
| `data-px.js` | Phrase translations, part 1 (25 languages) |
| `data-px2.js` | Phrase translations, part 2 (25 languages) |
| `data-uix.js` | Interface translations, all 50 languages |
| `sitemap.xml` | SEO sitemap (langbleu.com) |
| `robots.txt` | SEO robots file |

Every file is under 1 MB. Upload with **Add file → Upload files** (never paste code).

## The 50 languages

af, sq, de, en, ar, hy, be, bg, ca, zh, ko, hr, da, es, et, fi, fr, gl, el, ka,
he, hi, hu, id, is, it, ja, lv, lt, mk, ms, nl, no, ur, fa, pl, pt, ro, ru, sr,
sk, sl, sv, sw, fil, cs, th, tr, uk, vi — every language works both as
"I speak" and as "I want to learn" (all 2,450 pairs).

## Audio

Listen buttons currently use the visitor's device voices (phone/browser TTS),
with an online voice fallback. Recorded voices (ElevenLabs) are the LAST phase:
when the audio files are ready they plug into per-language `audio-<code>.js`
sprite files — no other change needed.

## Notes

- All lessons, phrases and code are original LangBleu content.
- Progress, favorites and the account are stored only in the visitor's
  browser (localStorage, `langbleu_` prefix) — no server, no database.
- AdSense: the grey "Advertisement" boards are placeholders; paste the real
  AdSense units there after approval.
