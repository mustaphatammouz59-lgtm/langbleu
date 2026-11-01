# LangBleu.com — Language Learning Platform (V2 — classic lesson-index homepage layout)

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
- 67 selectable languages; complete verified 120-phrase course (15 topics × 8) in EN, ES, FR, DE, IT, PT, AR
- Lessons with audio (device TTS), pronunciation guide, examples, favorites, mark-done
- 8 games, all functional + scored: Flashcards, Matching, Memory, Tic-Tac-Toe, Listening, MCQ Quiz, Word Writing, Letter Ordering
- Pronunciation: listen, record (MediaRecorder), replay, compare; auto-assessment via Web Speech Recognition where supported (Chrome)
- Optional local account, progress %, favorites, achievements, game history (localStorage = DB layer)
- Admin at `#/admin` — password `admin123` (change it in Admin → Security): add/edit/delete custom phrases, add languages, stats, AdSense publisher ID, architecture notes
- AdSense slots: home top + in-feed, lessons, lesson pages, between games (never during play)
- SEO: meta, Open Graph, JSON-LD schema, sitemap.xml, robots.txt; light/dark mode; RTL when Arabic is the native language; fully responsive

## Honest limits
- Translations are complete and verified only for the 7 course languages. Other languages are selectable and ready; the site labels them "content growing" and never invents translations. Grow them in Admin → CMS.
- Audio quality depends on the learner's device voices. Speech recognition works mainly in Chrome and needs HTTPS + mic permission.
- The admin password gate is a demo gate for static hosting. Before heavy public promotion, protect admin with real backend auth.

## Roadmap (steps 1–15 from the brief)
1–3. ✅ Analysis, brand, logo, DB schema (in Admin → Architecture)
4–9. ✅ Homepage, language system, lessons, games, audio/pronunciation, accounts
10–12. ✅ Admin dashboard, SEO, monetization slots
13. ✅ Tested in automated browser checks: all 22 routes render, 120 phrase rows, admin login flow — phone test still yours
14. ✅ One bug found in testing (lessons-page swap button) and fixed before delivery
15. ⏳ Your steps: upload 3 files → test on phone → change admin password → add AdSense ID after approval → buy langbleu.com last

## Scaling path
Same schema → Supabase (Postgres + Auth + Storage) or Firebase; static front-end behind CDN; per-lesson SEO URLs generated at build time. No API keys needed in V1; any future paid API key goes in server environment variables, never in index.html.
