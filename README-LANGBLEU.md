# LangBleu.com — Language Learning Platform (V7.6 — SUB-1 MB SPLIT FILES 2026-11-01: Mustapha's phone truncates transfers at exactly 1 MiB (his index.html copy measured 1,048,578 bytes, cut mid-UIX; the live site hung on "Loading LangBleu…" because the main script was incomplete). The site data moved out of index.html (now 90 KB) into data-p.js (100 KB), data-px.js (547 KB), data-px2.js (524 KB), data-uix.js (938 KB), and each audio sprite was cut at phrase boundaries into 5 part MP3s under 945 KB (audio-mr-1..5.mp3, audio-ta-1..5.mp3) with a parts manifest in audio-<code>.js; spriteSpeak picks the part by phrase index. Every deliverable file is now under 1 MB. V7.4 — EVERYTHING IN ONE FILE 2026-11-01 (Mustapha: «جمعهم في ملف واحد»): the Marathi + Tamil sprites were re-encoded at 24 kbps (6.1 + 6.8 MB) and EMBEDDED into index.html as base64 with their timing tables; spriteSpeak decodes the embedded audio once to a blob URL and plays segments from it — the upload is now the single index.html (19.4 MB, under the 25 MB GitHub/Cloudflare file limits). The external audio-<code>.mp3 path remains for any language added later. V7.3 — READY AUDIO FILES, LANGUAGE BY LANGUAGE 2026-11-01 (Mustapha’s proposal, LingoHut’s method): gen_audio.py fetches every phrase’s Google-TTS MP3 server-side (no Referer — the endpoint 404s with any Referer, which was the true cause of the on-phone failures) and packs one language into audio-<code>.mp3 (all 1,028 phrases in order, 0.30s lead + 0.45s tail silence, mono 32kbps) + audio-<code>.js ([start,dur] table). speak() tries the sprite first (segment-accurate, same-origin), the live chain remains as fallback; adding a language later needs only its 2 files, no index.html change. DONE: mr (8.1 MB, 2030s, 0 missing) and ta (9.0 MB, 2253s, 0 missing), segment loudness verified. V7.1 — AUDIO HARDENED 2026-11-01 after his phone test showed the toast “Audio is not available on this device”: voices are awaited once when the list is still empty, device-utterance errors fall through to the online voice, the online voice tries translate.googleapis.com then translate.google.com (play() rejection AND media error), one shared Audio element is created on first touch so timer-driven plays (lesson player, games) inherit the activation, and the final failure message names the remedies (internet / install the language voice in the phone TTS settings). V7 — FULL CONTENT IN ALL 67 LANGUAGES + PER-LANGUAGE VOICES 2026-11-01, at Mustapha’s request after his Tamil/Marathi screenshots: all 1,028 phrases translated into the other 60 languages (content/cnt_1..20.json merged as PX by apply_px.py) so both lesson columns render in any language and the English-source content note is gone; every language carries the Full course badge; About/FAQ updated. Audio reworked: speak() preloads device voices (voiceschanged) and picks the voice matching the phrase language; when the device has no voice for that language it falls back to Google’s TTS voice for exactly that language (online) — foreign words are never read with the default English voice again. V6 — whole interface follows the “I speak” language 2026-11-01 at Mustapha’s request: ~186 UI strings (nav, home incl. long paragraphs, lessons index, lesson page, games incl. gameplay text, pronunciation, profile, languages page, footer) translated in all 67 languages via UIX dictionary with per-key English fallback; RTL for ar/he/fa/ur; static legal/about bodies remain English; V5 — 125-lesson curriculum lessons page rebuilt lessons page rebuilt to the FR→EN reference picture (no search box, error link + ad between sections, 3-col cells, → arrow, exact FR headings); NEW template, admin removed, homepage contains ONLY the reference sections in order (Lesson categories + Your progress extras deleted 2026-11-01 at Mustapha correction: never add unbriefed sections); based on V4.1 2026-11-01, at Mustapha's request: classic lesson-site layout in original code — white top bar with 2px purple bottom border (72px/48px), uppercase nav + LEARN picker + flag button, light #FAFAFA background, 1024px column, H1 + “I speak / I want to learn” boxes (5/5/1) + 58px cyan arrow, picture grid of 67 languages with original landmark-emoji scene tiles, Advertisement-style ad boards, purple footer (#7B1FA2) with Donate/social outline boxes + darker copyright bar. Home H1/intro/2 SEO sections fully localized in EN/FR/ES/DE/IT/PT/AR. V3 file kept as index-v3-backup.html (do NOT upload the backup).

Original platform by Mustapha (Bleu family: CalcBlue, PdfBleu, TempBleu). Not affiliated with LingoHut; no copied content, code, images or branding.

## Files to upload (repo root)
- `index.html` — the complete platform (one file)
- `sitemap.xml`
- `robots.txt`

Upload exactly like CalcBlue: GitHub repo → upload files → Cloudflare Pages/Worker. Buy the domain LAST (your TempBleu rule).

## Brand
- **Name:** LangBleu.com (alternatives kept: Lingora, PolySpeak, TalkNova, MundoLingo)
- **Logo:** blue speech bubble with 3 language dots (inline SVG in the header)
- **Colors:** blue #2563EB, teal #0D9488, amber #F59E0B — original identity

## What works in V1
- 67 selectable languages; complete verified 1,028-phrase course across 125 lessons in EN, ES, FR, DE, IT, PT, AR
- Lessons with audio (device TTS), pronunciation guide, examples, favorites, mark-done
- 8 games, all functional + scored: Flashcards, Matching, Memory, Tic-Tac-Toe, Listening, MCQ Quiz, Word Writing, Letter Ordering
- Pronunciation: listen, record (MediaRecorder), replay, compare; auto-assessment via Web Speech Recognition where supported (Chrome)
- Optional local account, progress %, favorites, achievements, game history (localStorage = DB layer)
- No admin panel (removed 2026-11-01 at Mustapha's request): there is no `#/admin` page, no login and no CMS in the file. The AdSense publisher ID is set in the code (constant `ADSENSE_ID` at the top of the script) once LangBleu's own AdSense is approved.
- AdSense slots: home top + in-feed, lessons, lesson pages, between games (never during play)
- SEO: meta, Open Graph, JSON-LD schema, sitemap.xml, robots.txt; light/dark mode; RTL when Arabic is the native language; fully responsive

## Honest limits
- Translations are complete and verified only for the 7 course languages. Other languages are selectable and ready; the site labels them "content growing" and never invents translations; the course grows language by language in new file versions.
- Audio quality depends on the learner's device voices. Speech recognition works mainly in Chrome and needs HTTPS + mic permission.

## Roadmap (steps 1–15 from the brief)
1–3. ✅ Analysis, brand, logo, DB schema (localStorage layer in the code)
4–9. ✅ Homepage, language system, lessons, games, audio/pronunciation, accounts
10–12. ✅ SEO, monetization slots (admin dashboard removed in V4.1)
13. ✅ Tested in automated browser checks: all 21 public routes render, 120 phrase rows, `#/admin` falls back to home — phone test still yours
14. ✅ One bug found in testing (lessons-page swap button) and fixed before delivery
15. ⏳ Your steps: upload 3 files → test on phone → add AdSense ID in the code after approval → buy langbleu.com last

## Scaling path
Same schema → Supabase (Postgres + Auth + Storage) or Firebase; static front-end behind CDN; per-lesson SEO URLs generated at build time. No API keys needed in V1; any future paid API key goes in server environment variables, never in index.html.
