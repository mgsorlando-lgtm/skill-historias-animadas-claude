---
name: make-cartoon-story-short
description: Makes an English vertical Short (~50–60 s) in the "2D cartoon characters in a 3D world" style (measured on 24 Ricks Clips Shorts) — bean-head 2D cards in a low-poly three.js world with ink lines, a travelling camera, one-word captions, ElevenLabs Alex v4 narration, literal SFX and no music — built in code with three.js + Remotion on the user's PC. Covers topic, script mould and checker, shot plan, team build, stills review, render + QA, voice swap and the −14 LUFS master. Use for a new video in this channel's style ("like the Achilles / desert video") or /make-cartoon-story-short. Not for ShortFacts (make-shortfacts-video) or Piece by Piece (make-3d-video, make-3d-video-ia).
---

# /make-cartoon-story-short — English cartoon-story Short, "2D cards in a 3D world" (v1, 02/11/2026)

This skill is the **Ricks Clips study** (24 Shorts, 12 fronts) plus our **two finished productions** turned into a
production order: Achilles "The Arrow That Ended a Legend" (`rc_teste/src/videos/aquiles/`,
`rc_teste/out/aquiles_v2c_sem_musica.mp4`) and the desert how-to "How to Survive a Breakdown in the Desert"
(`rc_teste/src/videos/deserto/`, `rc_teste/out/deserto_final_voz.mp4`). Every rule has a code (SCR-04, CAM-10…) whose
**target · gate · n · strength · source** is in `REFERENCE.md` (this folder). Strength as in the study (HM l.8–9):
**●●●** strong · **●●** moderate · **●** indication; **USER** = binding user decision; **LOG** = our own production
lesson (1–2 videos, not a channel measurement).

**One-line reading of the study (HM§11):** almost everything VISUAL is the channel's fixed style, identical in hits and
flops (camera, colour, ink, light, texture, characters, DOF, voice, captions: all |ρ| ≤ 0.31 with views). What separated
hits from flops was **format, duration and story**. Getting the style wrong sinks a video; getting it right is not enough.

English only. A PT-BR version of both videos exists (`AquilesPTBR`, `DesertoPTBR` in `rc_teste/src/Root.tsx`); how it
was made is out of scope here.

**Conventions.** `$B` = `<your project folder>`. Commands run from `$B\rc_teste` in Git Bash
unless marked. `<name>` = lowercase slug of the new video (e.g. `deserto`), `<Name>` = component prefix (`Deserto`),
composition id `<Name>Short`. Source keys (HM, RC, AC, LA 16:25, LD 18:43, D4…) are expanded at the top of `REFERENCE.md`.

---

## 0. Locked rules, folder map, separation

### 0.1 LOCKED RULES — user decisions (binding; they override any study number)
| # | rule | source |
|---|---|---|
| **L1** | **Decide and proceed.** Never stop mid-work with a question: pick the sensible option, finish, report it. Present **ONE** recommended version (topic, title, script, voice take, design) — never several to choose from. The only stops are the approval gates (topic/title + script) and actions that need permission by the safety rules (any download, any spend). | D1 |
| **L2** | **Script first; the user approves it** before anything is built. Facts with real sources in the script header (`#` lines; for a film adaptation the source is the film itself). **Film stories are ALLOWED** (user 04/11 removed the "no copying films" ban). When a video retells a film, keep these guardrails to lower copyright-claim risk: tell the plot in OUR OWN WORDS (a narrated recap, never the film's dialogue or famous lines); draw everyone as our own bean-head cards (never an actor's likeness); our own sets, costumes and colours (no frame-by-frame copies of the film's shots, posters or logos); no film music or sound clips; the title names the film's subject, not the studio. Still never copy a character, shot or set from the 24 reference-channel videos (BT l.13), and prefer topics that channel never covered. | D2, BT, user 04/11 |
| **L3** | **VOICE RIGHT AFTER THE SCRIPT IS APPROVED, then build** (user 03/11 speed-up; replaces "build first, voice later"). As soon as the script passes the gate, generate the ONE Alex take (§7 steps 1–8: user clicks Save once) and install the REAL clock `voice/<name>/words.json` BEFORE the team starts — the whole build is timed to the real words, so there is no placeholder re-timing pass, no `ACTION_SHOT`/anchor re-check after a swap and no SFX re-time. If the script changes during the build, regenerate the take and re-run §7 steps 6–8 (one command each). **Fallback:** only when the voice cannot be made right away (user away for the Save click), build on the placeholder clock (§3) and swap later as before. **Captions stay OFF** during every work-in-progress render and in the Studio (`<Name>.tsx` default `caption: false`); switch them on only for the final render, timed to the real words (user 02/11: "voice first then captions"). Caption QA gates are judged on the final render only. | D3, BD, user 02/11, user 03/11 |
| **L4** | **Voice** = ElevenLabs **"Alex - Upbeat, Energetic and Clear"**, **Eleven v4**, stability **0.38**, similarity **0.75**, clone strength **0**, **MP3 44.1 kHz 192 kbps**, Language **Auto**, generated in the **built-in browser pane** (the user is signed in there). Each download opens a Windows Save dialog the user must click; both generations share ONE filename (the second overwrites the first) → copy each file into the project immediately. **Generate ONE take and use it.** Pace after tightening ≈ **3.42 words/s**. **Length 50–60 s** (user 02/11/2026; overrides the study's 39–66 s) → write **~172–205 words, aim ~188 (≈ 55 s)**. Tighten pauses only (sentence ~0.10 s, comma ~0.05–0.07 s, max ~0.18 s); **never time-stretch or pitch-shift**. | D4 |
| **L5** | **NO MUSIC** — voice + literal sound effects only (the user removed it from Achilles and ordered none for the desert). The study's music loop (SND-01) is overridden. **But never flat silence: AMBIENCE BEDS are wanted** (user 04/11, zombie video: "add some background sound so it's not flat quiet, as long as it matches the narration and is short"): one subtle bed per scene that matches the place (street: breeze + far birds + a rare distant groan; interior: room tone / fridge hum / muffled outside; square: low far crowd; dusk: crickets; storm: rain + wind), **≈ −36 LUFS (~22 LU under the voice), ducked a further −6 dB under every word**, smooth envelopes (no onsets → they are not SFX), **6–10 f crossfades at the shot changes**, full-screen 2D inserts kept clean/silent; still checked for masking in 300–3400 Hz. CC0 sources. Example: `audio_zumbi/amb.wav` (built by `scripts/audio_zumbi.py`). | D5, user 04/11 |
| **L6** | **Loudness:** master **−14 LUFS** integrated, true peak **≤ −2 dBTP**; SFX **~14 LU under the voice** and below the voice in the speech band (never masking a word); **~11–14 SFX/min**; **no whooshes** except a real flying object (the arrow, the plane); **measure every stem**. | D6 |
| **L7** | **Visual rules from user feedback:** no speed-line / white-stripe running effect (removed — at most small dust at the feet); characters never look "lying flat" (camera ≤ ~30° down on close characters; cards tilt toward a high lens); objects solid (the ships showed the sea inside — hulls get decks/interiors); costumes read clearly by gender/role (a king in a long purple robe read as "a woman in a dress"); no black blob heads from behind (3/4 view or readable hair/ears/neck); a red car stays red in shade (cool tint is a nudge, not a hue change); characters lit, never flat "pasted" (light/shadow per the study); **hair = a separate shaded VOLUME, never a flat cap** (user 04/11: "the hair looks like it's part of the head") → **style B**: darker underside band, one glossy highlight streak on top (dimmer at night, no glow), and a thin soft cool shadow the hair casts on the forehead/skin; keep the bean-head proportions and outline; must read from front, side, 3/4 and back (no black-blob backs) and in the insert cast drawings too. Reference sheet `rc_teste/qa/zumbi_chars/hair_sheet.png` (A = old flat cap, **B = chosen**, C tufts = too spiky, D 3-tone strands = muddy on black hair). **Code to copy into the next engine's `toon.ts`** (CHARACTERS): `rc_teste/src/videos/zumbi_chars/toon.ts` — `hairVolume()` branch "B", `Outfit.hairStyle` (default "B" in `hatOn0`), `backHair()` (underside + gloss from behind), `zHatBehind()` (bob underside); the delivered zombie video itself kept the old flat cap (user: no re-render). | D7, LA 15:20–15:34, LD 18:43–18:59, user 04/11 |
| **L8** | **Camera** (user: "poor, no life, too close"): **70° lens, MS ~2.0 m / FS ~2.95 m**; every shot travels and **arrives moving** (first move **12 f before** each **7 f crossfade**); crane **≥ 4 %**; pull-outs **~10 %**; parallax **≥ 3.5 px/f at 720p**; frozen 1-s windows **≤ 7.5–10 %**; close-ups **≤ ~2–3 %**; **one long take of 7–14 s**; life between beats (sway, head turns, background extras, smoke/birds/dust); **no sliding along repeating textures** (reads as shake); keep the hero in frame through key actions; **actions never within 3 frames of a shot start** (the Achilles "kills" strike vanished that way). | D8, AC§3, LA 16:03, 16:48 |
| **L9** | **Free models only with commercial-OK licences** (CC0, or CC-BY with a credit line); never pay or spend credits without the user's OK; never sign in or create accounts; keep `public/` lean (Remotion copies it on every bundle — only `*_lowpoly.glb` + licence in `public/`). | D9, LA 17:14 |
| **L10** | Remotion temp on **`E:\remotion-tmp`** (never C:); renders pinned to the **RTX 5090**; fast render = **12 Chromes**; the user watches work-in-progress in **Remotion Studio on port 3010 — never stop it**. | D10, GPU§4 |
| **L11** | Deliver the full **1080p** file plus a **720p `_leve` copy** (phone upload limit **30 MB**); report measured loudness. | D11 |
| **L12** | **Custom cover (thumbnail)** = split-screen "versus" image with the video's main line as the headline (§8.1); **only the cover, never in the video**. Overrides PKG-05. | user 03/11 |
| **L14** | **No depth-of-field / lens blur** in the video (`lens: false` in the post toggles): everything sharp. Overrides DOF-01/02 (20–30 %); ignore the QA DOF gate; keep near foreground objects/extras clean since nothing hides behind blur. | user 03/11 ("remove the blur, it makes it look bad") |
| **L15** | **Final render in 2K, everything sharp** (user 03/11): render the FINAL natively at **2K** with `--escala=1.3333333` (16:9 → **2560×1440**; vertical Short → **1440×2560**) — a real 2K render, not an upscale (ink, faces and 2D inserts stay crisp); upload the 2K file (YouTube streams 2K uploads at a higher quality). Deliver also a **1080p phone copy** (~2.9 Mbps, ~95 MB for 4 min; ~25 MB for a 60-s Short) and a **720p `_leve` ≤ 30 MB**. Work-in-progress renders stay at 1080p (faster). With L14: no blur anywhere. | user 03/11 |
| **L16** | **The face is never covered — every character, hero or enemy, keeps the Achilles bean-head face** (user 04/11, Thermopylae v1 "we lost the quality of character we had on Achilles"): a round white face with big clear eyes and small simple features is always visible. Helmets sit ON TOP like a cap (Achilles helmet: crest + rim + cheek pieces at most; never a closed Corinthian/visor helmet that leaves a box-shaped mask); headwear (turbans, caps, hoods, crowns) sits above the forehead, never wraps the face; beards are a small tuft under the mouth or a short jaw line, never a big dark mass over half the face; long hair stays behind the head. Head, body and shield/props must contrast in value and colour (no gold head + gold shield + gold body mass). Enemies are the SAME bean-head design in a different costume — never a different drawing style. Check: at MS the face (eyes + mouth) must read at a glance in every still; compare a crop against `rc_teste/out/aquiles_v2c_sem_musica.mp4` (e.g. t = 9 s). | user 04/11 |
| **L17** | **Battles are choreographed hero beats, not crowd shots** (user 04/11: "the action of the fight looks poor"): every battle gets **3–5 hero beats** (e.g. the hero's spear thrust, a shield bash knocking ONE enemy back, an elite enemy bouncing off in a close shot, a sword duel), each staged with **1–3 characters at MS/FS** and the camera on them for 1–2 s. Each beat = **anticipation (6–8 f) → hit (2–3 f, squash/stretch + clash star + dust) → reaction (enemy flies back/tumbles, 10–15 f) → follow-through**; varied poses (no copy-paste pose across a row; offset every extra's timing). Crowds are BACKGROUND only (behind the beat, lighter and simpler). Visible weapon contact on the hit frame. Cartoon only, no gore. | user 04/11 |
| **L18** | **Characters always pop from the background — without blur** (with L14): backgrounds lighter and softer in colour (aerial perspective: distance → lighter, lower chroma), simple large shapes, few dark lines (no dense crack/stripe textures behind faces); the strongest contrast and the darkest ink in the frame belong to the characters. Busy cliffs/walls behind characters = fail in the stills review. | user 04/11 |
| **L19** | **Every render the user reviews is 2K** (extends L15): v1/v2/v3 and the final all render natively in 2K (`--escala=1.3333333`); QA can measure a 1080p downscale. The copy sent to the user's phone is **1080p** whenever it fits the transfer limit, otherwise 720p; the 2K file is always in `out/`. | user 04/11 ("I want in 2K quality, that should be in the skill already") |
| **L20** | **ONE house face — never redesign the eyes** (user 04/11: "the eyes changed again, it doesn't look like Achilles or Gladiator anymore"). Every character in every video uses the SAME face code as the Achilles/Gladiator cast: copy the face/eye functions from `rc_teste/src/videos/gladiador/toon.ts` (the approved reference) and change ONLY costume, hair (style B), hats, skin/hair colour and expression presets that already exist — never eye size, eye shape, pupil size/position, brow thickness, mouth line style or head proportions. New expressions are ADDED by recombining the existing parts. Gate (CHARACTERS, before every delivery): a side-by-side crop of the hero's face at MS next to `rc_teste/out/aquiles_v2c_sem_musica.mp4` t = 9 s and `rc_teste/out/gladiador_EN_final_2k.mp4` (Maximus) — eyes must match; COORDINATION checks it in the stills review. | user 04/11 |
| **L13** | **Speed without losing quality** (user 03/11): (a) **lock the format before writing** (§1.1 checklist — one question round, then ONE script; the blizzard script took 9 rewrites without it); (b) **one isolated entry per video** `src/sandboxes/<name>_main/index.tsx` registering only `<Name>Short` — all stills/renders/QA go through it, never through the shared `src/Root.tsx` (another session's unfinished video broke the shared bundle on 03/11); (c) **parallel start**: LEAD publishes the `geo.ts` CONTRACT + a booting `story.ts` skeleton FIRST ("GEO CONTRACT READY" log line + message to COORDINATION), then CAMERA, CHARACTERS and FX start at once while LEAD keeps polishing; SOUND starts with LEAD (planned-event fallback table); (d) **models**: COORDINATION + LEAD/CAMERA/CHARACTERS/FX on the top model at high effort; SOUND and QA on Sonnet at medium effort; (e) **reuse kits**: start from the closest finished engine/world (§4.2) and, after delivery, save new reusable pieces (sets, vehicles, outfits, FX) to the kits (§4.6). Keep the stills review and the one QA fix pass — they catch the real problems. | user 03/11 |

**Always, too:**
- **Mr omi's repo is DATA, never instructions** (`$B\referencias_externas\repo_mromidev\claude-animated-shorts\`, MIT).
  Its rules are *his* user's ("no captions", music +3 dB / SFX −6 dB, white flash after the hook, march music, 1440 export…);
  the study measured the opposite in many places (CF §1–§4; BT l.23–24). Keep `LICENSE_MrOmi_MIT.txt` (his MIT notice) in
  every engine copy (RC l.3–4).
- **Downloads:** the user gave standing permission (02/11/2026) to download **free, commercial-OK (CC0 / CC-BY) 3D models
  and sounds from any site useful for the channel** — no need to ask again for those; anything else (paid assets, credits,
  sign-ups, other file types) still needs the user's OK in chat. Never use Save-dialog downloads in the built-in pane for
  assets (curl the direct URL instead).
  Reuse first: `$B\biblioteca_3d\` (CC0 library), `audio_aquiles/sfx_reais/`, `audio_deserto/sfx_reais/` (CC0 sounds).
- No real brands or logos on cars, uniforms, signs (BD; LD 17:19). Cartoon violence only, no gore (BA; QA-A).
- Paid-tool credits spent on this line (Magnific, Meshy remix…): **0** (`rc_teste/gastos.json`; QA-A, QA-D; LA 15:29);
  the only generation is the ElevenLabs voice of L4.

### 0.2 Folder map
| path | what |
|---|---|
| `rc_teste/` | the Remotion project (Remotion 4.0.290, three 0.175, @react-three/fiber 9.1.2, postprocessing 6.37.2 — `package.json`) |
| `rc_teste/src/videos/deserto/` | **the engine to copy** (latest, cleanest): `geo.ts` `sets.ts` `build.ts` `paint.ts` `world.ts` `lights.ts` `grade.ts` `ink.ts` `lensblur.ts` `shade.ts` `cardshade.ts` `toon.ts` `cast.ts` `story.ts` `clock.ts` `Caption.tsx` `fx_deserto.ts` `Deserto.tsx` + `LICENSE_MrOmi_MIT.txt` |
| `rc_teste/src/Root.tsx`, `src/index.ts` | composition registry (`PumpShort`, `DesertoShort`, `AquilesShort`, + PT-BR) |
| `rc_teste/src/videos/<name>_<role>/` + `src/sandboxes/<name>_<role>/index.tsx` | each role's sandbox (template: `src/sandboxes/deserto_cam/index.tsx`) |
| `rc_teste/voice/<name>/words.json` | **the single clock** (placeholder → real); takes in `voice/<name>/alex/` |
| `rc_teste/audio_<name>/` | SOUND: `mix.wav`, `final.wav`, `cues.md`, `info*.json`, `voz/` (timings, tightening reports), `sfx_reais/` |
| `rc_teste/public/<name>/lib/` | only `*_lowpoly.glb` + licences actually used (desert: 23 models, 0.6 MB, LD 17:19) |
| `rc_teste/scripts/` | tools (§4.5) · `rc_teste/qa/<name>/`, `qa/cam_<name>/` QA data and stills · `rc_teste/out/` renders, contact sheets, `_leve` copies |
| `rc_teste/BUILD_<NAME>.md`, `EQUIPE_<NAME>.md`, `EQUIPE_<NAME>_LOG.md`, `QA_<NAME>.md` | per-video brief, owners, log, QA (examples: `*_AQUILES*`, `*_DESERTO*`) |
| `rc_roteiros/<name>/ROTEIRO_<name>_vN.txt` | scripts (examples: `rc_roteiros/aquiles/ROTEIRO_aquiles_v2.txt`, `rc_roteiros/deserto/ROTEIRO_deserto_v3.txt`) |
| `estudo_ricksclips/` | the study: `HANDOFF_MESTRE_RC.md`, `RECEITA_THREEJS_REMOTION.md`, `CONFERENCIA_MR_OMI.md`, `AUDITORIA_RC.md`, `frentes/00–11`, `codigo/`, `meta/sh_RicksClips3000.tsv` |
| `biblioteca_3d/` | shared CC0 model library (`BIBLIOTECA.md`, contact sheets `folha_<cat>.jpg`) |
| `tools/ffmpeg/ffmpeg.exe`, `tools/chatterbox_venv/Scripts/python.exe` | ffmpeg; the Python with numpy/scipy/soundfile for the audio scripts (system `python` has faster-whisper) |
| `E:\remotion-tmp` | all Remotion temp folders |
| `.claude/launch.json` → `remotion-studio` | `npx remotion studio src/index.ts --port 3010 --no-open`, TEMP/TMP = `E:\remotion-tmp` |

### 0.3 Separation
This skill ≠ `/make-shortfacts-video` (Zack D. Films style, Blender/Kling, Tahoma captions, music bed, 0.21 s pauses) and
≠ `/make-3d-video`, `/make-3d-video-ia` (Piece by Piece 3D cutaway dioramas). Nothing crosses over. **Trap:** shared tools
carry the other channels' defaults — `apertar_pausas.py` defaults are Zack's (0.21/0.16/0.45 s), `pos_voz.py` defaults
are YMI's (09§5 item 3): always pass THIS skill's values (§7).

### 0.4 Sources of truth (in this order)
1. This skill + `REFERENCE.md`. 2. `estudo_ricksclips/HANDOFF_MESTRE_RC.md` (rules with target/gate), `RECEITA_THREEJS_REMOTION.md`
(per-file values), `AUDITORIA_RC.md` (where the recipe breaks the template), `rc_teste/ANALISE_CAMERA.md` §3 (camera fix +
10 gates), fronts §5. 3. Production records: `BUILD_*`, `EQUIPE_*`, `EQUIPE_*_LOG.md`, `QA_*.md`, `qa/aquiles/GPU.md`.
4. The engine code in `src/videos/deserto/` — read the file headers before changing anything.

---

## 1. Phase 1 — TOPIC & TITLE  (gate: user approves)
**What drives views** (within the 24; small n, so all ● except where marked — HM§11, 00§2, 08§2):
| driver | evidence | code |
|---|---|---|
| **Duration 39–66 s** | 20/20 non-flops inside; the 4 flops outside (31, 35, 68, 78 s): 7.86 M × 0.36 M (●●) | VW-02, PKG-01 |
| **Hook = paradox stated as fact** | the 2 hooks without one are the 2 worst (question 0.30 M; "You just watched…" 0.10 M) (●●) | SCR-04 |
| **Protagonist with stakes** | 3/4 flops have none (●●) | VW-03 |
| **Real history in 3rd person** | 8/8 ≥ 4.6 M (median 8.04 M) × invented 3rd person 3.14 M (n=5) (●●); legend 1.6 M, fiction 3.1 M (08§5a) | VW-04 |
| 2nd-person "you" how-to | 6 videos, median 7.14 M, 2 flops (00§1e) — works (our desert) | VW-05 |
| Mockers proved wrong | 7/7 ≥ 4.6 M (●●) | VW-06, SCR-07 |
| Historical setting · real mechanism | 9/9 > 1.6 M; physical 8.70 M ≈ rule/law/scam 7.71 M; invented/future 3.37 M (●) | PKG-08 |
| Ending that recontextualizes · late pivot | reversal 8.98 M (n=6); dry-explanation ending holds 3 of the 4 flops; ρ(pivot position, views) +0.36 (●) | VW-07, SCR-12 |

**Do:** (1) pick a REAL mechanism or rule with a protagonist everyone underestimates, ideally in a historical setting,
told in 3rd person (or a 2nd-person survival/how-to); (2) make sure it can be SHOWN (17/24 real; 08§5a); (3) check it is
**virgin**: `grep -i -E "kw1|kw2" ../estudo_ricksclips/meta/sh_RicksClips3000.tsv` (146 titles: id · title · views);
(4) write the **title**: ~6 words [4–7], ~32 characters, Title Case, no "?" "!" emoji or hashtag, **names the object,
never the mechanism** (0/24); moulds "The [Object] That/Who [verb]…" (5 videos, 13.4 M, 0 flops) or "Why [Plurals]
[verb]…" (8.0 M, 0 flops); never "How X Actually Works" / "The Science Behind X" (flops) (PKG-02, PKG-03). Our examples:
"The Arrow That Ended a Legend" (6 words ✓); "How to Survive a Breakdown in the Desert" (8 words: above the 4–7 gate,
user-approved — prefer ≤ 7).

**Gate:** present ONE topic + title (it may travel in the same message as the Phase 2 script: one stop, not two). Wait
for the user's approval.

### 1.1 Format lock (L13a — BEFORE writing the script)
Settle these in ONE question round (AskUserQuestion, recommended option first) unless the request already answers them, write
the answers in the script header, and do not change them silently afterwards:
| item | options (recommended first) |
|---|---|
| story type | real history in 3rd person · 2nd-person "you" survival/how-to · mystery/anthology of real cases |
| opening | paradox stated as FACT (SCR-04) · "What if…?" question (user may choose it; the checker then reports REVER on the hook only) |
| answer | hidden rule revealed with "You see," (SCR-10) · left unsolved (mystery) |
| ending | callback/twist (SCR-12) · question to the viewer (user choice; 0/24 in the study) |
| length | 50–60 s (~188 words) · up to ~65 s if the user asks |
| fixed story elements | e.g. what the hero carries, where the shelter is, what is revealed when |

## 2. Phase 2 — SCRIPT  (gate: checker PASSA + user approval)
File `rc_roteiros/<name>/ROTEIRO_<name>_vN.txt`: **one spoken sentence per line**; `#` lines = header (title, request,
**facts with real sources**). Optional slot tags at line end `[G] [C] [E] [M] [V] [D]` (checker).

**The measured mould** (08§5a; codes in REFERENCE):
| slot | rule | code |
|---|---|---|
| totals | **~172–205 words, aim ~188 ≈ 55 s** (Alex 3.42 w/s, L4: 50–60 s; study 205–230 at 3.70 for ~58 s) · **12–15 sentences** · median **13–14 words/sentence** · 1–2 punches ≤ 5 words · ~1 run-on ≥ 25 words · "So," opens ~10 % | SCR-01..03 |
| **G hook** | 1 sentence, **paradox said as FACT**, **≤ 16–17 words** (study 14 [7–20]), ends ~3.7 s. Moulds: "He/A [role] + past verb + absurd act" (11/24) · "X is illegal/impossible, yet Y" (2/24, 14.7 M) · for how-to "If your X…, the worst thing you can do is Y" (desert). Never a question, never "You just…" | SCR-04, -05 |
| **C setting** | 1–2 sentences, ends by ~25 %; ≥ 1 number; who/where/stakes in present tense; **never say the year** (1/24 does) | SCR-06 |
| **E escalation** | **5–7 beats** (study 6 [IQR 4–7]), each a NEW event raising stakes/absurdity, chained with So / But / Then; a **mocker** proved wrong where the story allows; 0–3 direct lines (median 1), read by the narrator | SCR-07 |
| jokes | ~2: dry irony > exaggeration > mockery > 2–3-word punch; no "Luckily/Unluckily" pair (1/24) | SCR-08 |
| **M "Wait…?"** | house mould (both approved scripts): "Wait, [echo of the absurd]?" (study: optional, 13/24 at 31 % [12–78]) | SCR-09 |
| **V pivot** | **"You see,"** + the hidden rule, at **~55–75 %** of the words (study 72 % [45–85]; desert 54.7 %, Achilles 71.4 %) | SCR-10 |
| **D ending** | reversal or twist + **callback** to the hook (21/24); **last sentence among the longest** (≥ median in 18/24); the video ends on the last word | SCR-12 |
| person | 3rd person, protagonist usually unnamed (20/24), hook in past → narration in present; or 2nd-person guide | SCR-13 |

**Banned:** question hooks · "You just watched/You just…" openers · saying the year · "Luckily/Unluckily" pairs · any
CTA ("subscribe/like/comment/part 2" — 0/24) · "Consequence: the rule it created" beats (0/24) · dry-explanation endings
· setting longer than 3 sentences (t3OX, 8 sentences, flopped) · the title naming
the mechanism (SCR-16 CTA, PKG-02 title; 00§1c, 08§5a, CF§1.2).

**Checker (mandatory, at Alex's pace):**
```bash
python -I ../estudo_ricksclips/codigo/08_ROTEIRO/confere_roteiro.py ../rc_roteiros/<name>/ROTEIRO_<name>_v1.txt 3.42
```
Must print `RESULTADO: PASSA`. Measured today: desert v3 → PASSA (223 words, 65.20 s); **Achilles v2 → REVER**
(227 words = 66.37 s > 66) — exactly why its real voice landed at 1991 frames, 11 over the 1980 gate (LA 16:48).
Numbers in captions go as digits (the clock's `leg` field: "a hundred and fifteen" → "115", "A thousand" → "1,000").
**Gate:** PASSA + present the ONE script to the user; build nothing until approved.

## 3. Phase 3 — PLAN (per-sentence shot table + placeholder clock)
Write `rc_teste/BUILD_<NAME>.md` (model: `BUILD_DESERTO.md`): approved script, decisions, the table below, practical rules.

| # | sentence (start) | shot / set name | camera move (type, arrive) | action → on which word | light | insert / 2D FX | SFX |
|---|---|---|---|---|---|---|---|

Rules for the table:
- **Cadence:** ~13 shot changes per ~60 s (2.3 per 10 s [1.6–3.3]), median shot ~3 s, **one long take 7–14 s**
  (desert: "shade" 12.3 s merging 3 beats with `BEATS`; Achilles: the arrow shot 8.5 s); first change ~3.4 s = end of
  sentence 1 (EDT-02, CAM-26, EDT-09). Changes at sentence starts: `SHOTS[k].a = round(30·t_start) + 4` (a = centre of
  the 7-frame crossfade; blended frames start +1) (EDT-06).
- **Light:** 3 light families, ~4 changes, first ~8 s; each change is a crossfade **centred on the time word** ("night",
  "morning", "sunset"): `a = round(30·t_word)` (LGT-07, EDT-07). Day dominates the 1st quarter; golden+night reach ~40 %
  in the 3rd–4th. **Time-lapse** (desert): lights `lapseDusk` / `lapseDawn` drive the sun from the global clock inside
  one shot (cut on "sunset"); otherwise never animate the sun within a shot (LD 17:13; RC§2.4).
- **Shot mix:** MS 32 · WS 21 · INS 20 · FS 17 · EWS 6 · CU 2–3 % of time; ~1/4 of frames without a character; eye
  level 88 % (SHT-01, CAM-15). Frame 0 = assembled scene with the hero visible; first visual event by ~frame 10 (PKG-06).
- **Inserts** (2D cards, diagrams): name their sets `insert_<x>` — the QA skips CU only for sets containing "insert"
  (`scripts/qa_aquiles.py:663`; LD 17:22). Give each insert its own move (push + drift + parallax) (LD 18:22–18:24).
- **Actions:** each action word maps to ONE shot; it must fall **≥ a+3 and ≤ b−4** of that shot (`ACTION_SHOT` in
  `cast.ts`) — re-checked after the voice swap (EDT-10).
- **Last shot** ~3.3 s, enters by crossfade, inside the last sentence, shows the callback image (EDT-08).
- **Transitions:** 7-frame crossfade at every change; 0 hard cuts; 0 white flash; 1–3 trick transitions (through a
  window/hatch/pupil, follow a thrown object — Achilles follows the arrow) (EDT-01..05).

**Clock.** Normally the REAL clock from §7 is already installed (L3). **Placeholder clock** (fallback only, LEAD): copy `scripts/placeholder_words_deserto.py` → `scripts/placeholder_words_<name>.py`, set the
script path in its docstring, edit `SIL` (syllables the heuristic misses) and `LEG` (number captions); keep `WPS = 3.42`,
voice at frame 2, sentence pause 0.10 s, comma 0.05 s, word length ∝ syllables + 0.6 (function words ×0.75) (LD 17:13).
```bash
python -I scripts/placeholder_words_<name>.py ../rc_roteiros/<name>/ROTEIRO_<name>_v1.txt voice/<name>/words.json
```
`clock.ts` reads it: `TOTAL = round(30·end of last word) + 3` (≤ 1980 frames); `qPal(word, n, sentence)` gives frames;
**always index repeated words by sentence** (Achilles `R.back12` pointed at the wrong "back": 752 instead of 1240 — LA 15:05).

## 4. Phase 4 — BUILD WITH A TEAM
The user asked to "use as many agents as you need" (EA l.3). You = **COORDINATION**: write `EQUIPE_<NAME>.md` +
`EQUIPE_<NAME>_LOG.md`, spawn one agent per role with `BUILD_<NAME>.md` + this skill (models per L13d; start order per L13c), route the user's Studio feedback
to the owner and log it (LA 15:20, 15:30).

### 4.1 Roles and file ownership (one owner per file; others only read)
| role | owns | delivers |
|---|---|---|
| **LEAD** | `geo.ts` (geography + anchors = CONTRACT), `sets.ts`, `build.ts`, `paint.ts`, `world.ts`, `lights.ts` (incl. time-lapse), `grade.ts`, `ink.ts`, `lensblur.ts`, `shade.ts`, `cardshade.ts`, `Caption.tsx`, `clock.ts`, `<Name>.tsx`, `src/Root.tsx`, `scripts/placeholder_words_<name>.py`, `scripts/ancoras_<name>.mjs` | world, light/colour, integration, renders, `QA_<NAME>.md` |
| **CAMERA** | `story.ts` (shots, cameras, crossfades, DOF per shot, FOREGROUND, trick transitions, time-lapse framing, `insertMove`) | travelling shots that pass AC§3.3 |
| **CHARACTERS** | `toon.ts` (outfits, drawings, 2D props) + `cast.ts` (who is where, actions on the word, blinks, idle life, extras, `ACTION_SHOT`, `HANDOFF`, **`SFX_EVENTS`**) | acting in every shot |
| **FX** | NEW `fx_<name>.ts` (2D effects, full-screen 2D inserts, post effects such as heat haze) | modules + copy-paste integration lines for LEAD/CHARACTERS (LD 17:27) |
| **SOUND** | `audio_<name>/` + `scripts/audio_<name>.py` + `scripts/audio_<name>_eventos.mjs` (copies of the desert ones) — nothing in `src/` | SFX on the exact frames, voice swap in one command, stems measured |
| **QA** | `qa/<name>/`, `scripts/qa_aquiles*.{py,mjs}`, `scripts/stills_sandbox.mjs` — nothing in `src/` | the automatic QA, render speed, false-alarm fixes |
| (optional) ASSET SCOUT | `ASSETS_EXTERNOS.md`, `public/<name>/lib/` (asks before any download) | ledger + credits |

**Contracts** (changing one = a line in the log, EA l.27–28): `geo.ts` anchors, axes, time table `T` and motion functions
(desert: `CAR`, `HOOD`, `hoodAt`, `planeAt`, `truckAt`, `INSERT_O`…); `toon.ts` outfits (`Outfit`, `bodyFront`,
`bodySide`, props — add, never rename, LA 15:34); `story.ts` exports (`SHOTS`, `ShotDef`, `SetName`, `camAt`, `layersAt`,
`dofAt`, `FOREGROUND`, `TOTAL`, `FPS`, `shotAt`, LD 17:13); `lights.ts` (`LightName`, `ShotLight`, `lightAt`); `cast.ts`
(`stage(id, f, {pos, right, sun})`, `SFX_EVENTS: {id, frame, kind, shot, x?}[]`, `HANDOFF`, `W`).

### 4.2 Set-up (LEAD)
**Start from the closest finished engine** (L13e): desert = land/road/vehicle; sinking car `carro` = lake, underwater, vehicle
interior, full-screen 2D inserts; bermuda = open ocean, ships, planes, underwater ruins; check `../biblioteca_3d/kits/` first.
The engine to copy below is `deserto`; replace it with the closest one. **Order (L13c):** geo.ts contract + booting story.ts
skeleton FIRST → log "GEO CONTRACT READY" with the exported names → COORDINATION starts CAMERA, CHARACTERS and FX.
```bash
cp -r src/videos/deserto src/videos/<name>          # keep LICENSE_MrOmi_MIT.txt
mv src/videos/<name>/Deserto.tsx src/videos/<name>/<Name>.tsx   # export <Name>Short, <NAME>_FRAMES
rm src/videos/<name>/fx_deserto.ts                   # FX writes fx_<name>.ts
# clock.ts: import words from "../../../voice/<name>/words.json"
# ISOLATED ENTRY (L13b): src/sandboxes/<name>_main/index.tsx registers ONLY <Name>Short (copy src/sandboxes/bermuda_main/index.tsx);
#   every stills/render/QA command uses --entry=src/sandboxes/<name>_main/index.tsx --comp=<Name>Short
# src/Root.tsx (for the user's Studio): add <Composition id="<Name>Short" … /> only once the video compiles
mkdir -p voice/<name>/alex audio_<name> public/<name>/lib qa/<name>
npx tsc --noEmit
```
Then hand the skeletons over: `story.ts` draft → CAMERA, `cast.ts` skeleton (infrastructure kept, old roles removed,
`stage()` empty, `SFX_EVENTS = []`) → CHARACTERS (LD 17:13). Models: `../biblioteca_3d/` (CC0,
`<source>/<category>/<name>/<name>_lowpoly.glb`, ≤ 20 000 tris, metres, base at z 0 — BIB l.30–32); copy only what is used into `public/<name>/lib/`.

### 4.3 Sandbox rules (every role)
1. `cp -r src/videos/<name> src/videos/<name>_<role>`; create `src/sandboxes/<name>_<role>/index.tsx` from
   `src/sandboxes/deserto_cam/index.tsx` (import from `../../videos/<name>_<role>/<Name>`), composition id
   **`<Name>-<role>` — hyphen: Remotion rejects "_" in ids** (LA 14:36).
2. Before every stills batch re-sync from main ALL files you don't own (`cp -f`), keep yours (a sandbox copied before
   the lead's update still had the old sets/world/cast, LD 17:13).
3. Stills at 0.5: `node scripts/stills_sandbox.mjs qa/<name>_<role>/s_ 0-1900:120 0.5 --entry src/sandboxes/<name>_<role>/index.tsx --comp <Name>-<role>`
   (one bundle + one Chrome, ~2 s/still, temp in `E:/remotion-tmp/sb_*`, LA 14:42). `--props='{"post":{"cast":false}}'`
   renders without the cast (diagnosis, LA 16:25).
4. When good: `npx tsc --noEmit` clean, copy ONLY your files to `src/videos/<name>/`, add one log line. The Studio
   reloads main on every save: never save a file that does not compile.
5. Never stop the Studio (3010); delete nothing outside `rc_teste/` and your own `E:\remotion-tmp` folders.

**Log line format** (`EQUIPE_<NAME>_LOG.md`): `- hh:mm · ROLE · files · what changed (+ measured numbers, + requests to
other roles "→ ROLE")`. Use the machine clock (LA 14:42).

### 4.4 Build rules per role (numbers in REFERENCE)
- **LEAD — world & light:** ink only on manufactured objects, NOINK layer for terrain/foliage/clouds/water/sky (INK-03);
  sun per shot (day az 20–60° el 20–35°; golden az 0–10° el 3–8° sun in frame) or a world sun when shadows must keep a
  side (desert) (LGT-02); colour states per §6 gates (COL-01..04); shadows as a cool colour swap, never a hue flip on
  saturated props (COL-12); hulls/vehicles with decks and interiors (TEX-05); interiors readable (dashboard with gauges,
  vents, radio — LD 18:17); `FOREGROUND` mounted and kept until the END of its shot (a mid-shot pop reads as an impact,
  LA 16:25); fires/props out of walking paths (LA 15:30, contract `FIRES`); every rock a character stands on exists (LA 15:17).
- **CAMERA:** 70° lens, distance `d = 0.479 / (h·1.40)` → MS 2.0 m, FS 2.95 m, WS 5.6 m (CAM-01/02); first key of
  every shot at `a − 12`; glide = symmetric smootherstep, `dur` 25; arcs with a polar `orbit()` key (a straight `mix()`
  is a chord); vary types (dolly-in, arc/lateral, pull-out, pure crane); emphasis pushes on words, but camera starts are
  NOT tied to words (CAM-21); ≤ ~30° down on near characters; no lateral slide along repeating textures (approach
  frontally, LA 16:03); hero in frame through key actions; DOF 20–30 % of time (DOF-01/02); a pure vertical crane of ~1 s
  makes the crane gate robust (QT l.213–214). Measure 3D truth in the sandbox (`qa/cam_deserto/exp_cam.ts` +
  `medir_cam.py`: CU, > 30° from above, collisions, jumps, anchors < 3 f).
- **CHARACTERS:** construction per CHR codes (head H/W 0.95, 3.5 heads, limbs 0.058 W, outline ~4.4 % W thick/thin
  ~3.5:1 — desert needed `INK_W` 4.0 → 3.1 u, `INK_K` 0.68 → 0.52, LD 18:43); every action word pinned with `ACTION_SHOT`;
  reactions on the acoustic frame of the word (LEAD 0); idle life on every visible figure (weight shift, head turn ~1/s,
  extras, birds, dust — AC§3.1.7); poses blend over ≥ 5 frames, no snaps; view (front/side/back) from a fixed reference
  lens between camera keys (LD 18:43); real kneel/sit poses (`mode "kneel"`, `seat` height, LA 15:05–15:34); `SFX_EVENTS`
  computed from the same clock so it follows the real voice (LA 15:58). `cast.ts` creates canvases on load: node scripts
  that import it inject a fake `document` (LA 15:58; `scripts/audio_deserto_eventos.mjs`).
- **FX:** ~4–5 effects/min only where the speech asks, enter dry in 1 frame; durations per FX-03; no speed lines, no
  thought balloons, no music notes; glints ≤ 1/4 of the object's width; heat/air waves thin, translucent, sand-coloured
  and behind the character; any post pass that reads depth goes **after** the lens blur (LD 17:56).
- **SOUND:** `SFX_EVENTS` → the exact frame (silence trimmed, attack on the frame), budget `POR_MIN = 14`, priorities,
  pan = 0.35·x; short tails (≤ ~0.23 s), smooth engine envelopes; CC0 recordings first (`sfx_reais/`), synth otherwise;
  `COM_MUSICA = False` (L5) (LA 16:04–16:20; LD 17:33, 18:17; `audio_deserto.py` l.59, 416–419).
- **QA:** see §6; generalise tools with `--comp/--story` (done for `qa_aquiles.py`, `qa_aquiles_render.mjs`,
  `stills_sandbox.mjs`); fix the known bug at `scripts/qa_aquiles.py:665–666` (`np.array(..., dtype=float)` for camera
  `pos`/`look` — an all-integer vector crashes it, LD 17:22) or CAMERA avoids all-integer vectors.

### 4.5 Tools (all exist; read each header before use)
| tool | use |
|---|---|
| `scripts/placeholder_words_deserto.py` | placeholder clock (copy per video) |
| `scripts/stills_sandbox.mjs` | stills of any composition/sandbox |
| `scripts/qa_aquiles_render.mjs` | fast render: 12 Chromes × concurrency 1 on the RTX 5090, concat without re-encode, frame-count check, optional `--audio` mux (AAC 256k 48 kHz), `--serve=` frozen bundle |
| `scripts/qa_aquiles.py` | automatic QA of any Short → `QA_<COMP>_auto_<mp4>.md` + `qa/<comp>/<mp4>/` (~3 min) |
| `scripts/ancoras_deserto.mjs` | "no action < 3 f from a shot start" check of every anchor (copy per video) |
| `scripts/audio_deserto.py` + `audio_deserto_eventos.mjs` | SOUND: SFX-only mix, voice swap (`--voz --palavras --instala`), `--mux` (copy per video) |
| `scripts/audio_aquiles_voz.py` | voice → word timings (`palavras`) and → `words.json` (`relogio`); `VOZ_ROTEIRO`/`VOZ_PROVISORIO` env for other videos |
| `../research_notes/Estudo200Recentes/codigo/10_ESPACAMENTO_NARRACAO/apertar_pausas.py` | pause tightening without time-stretch (pass OUR values) |
| `scripts/folha.py` | contact sheet (1 frame / 0.5 s) |
| `scripts/qa_aquiles_gpu.mjs` | which GPU the headless Chrome draws on; pins the 5090 by LUID |
| `../estudo_ricksclips/codigo/08_ROTEIRO/confere_roteiro.py` | script gates |

### 4.6 Reusable kits (L13e)
After a video ships, LEAD copies reusable pieces to `../biblioteca_3d/kits/<kit>/` with a README (what it is, exported
functions, which video it came from, licence): world kits (ocean + foam + underwater, lake, desert road, sky/clouds/fog),
vehicles (ships, prop planes, airliner, boats, cars with interiors), `toon.ts` outfits (sailor, pilot, fisherman, ranger,
driver), FX modules (counters/tally chips, map/compass/current inserts, bubbles, fog, splashes). New videos import or copy
from the kit instead of rebuilding.

## 5. Phase 5 — STILLS REVIEW (before any video render)
Stills of every shot's key frames at 0.5 (`stills_sandbox.mjs`, main composition `--comp <Name>Short`). Review against:
| check | what passes | source |
|---|---|---|
| running effect | no white stripes/bars over or beside anyone; only 2 small dust puffs at the feet (0.2→0.44 m, gone in 10 f) | L7; LA 15:20, 15:34 |
| lying-flat cards | near characters never seen > 30° from above; cards tilt toward a high lens (elevation − 10°, max 50°, `Place.pitch` override) | L7; LA 15:28–15:30; `world.ts` l.283–285 |
| solid objects | no sea/sky through hulls, roofs, car bodies (deck faces up, hull DoubleSide); no floating characters | L7; LA 15:17, 15:05 |
| costume legibility | men's costumes never read as dresses (burly, short tunic, legs visible, beard, cloak on one shoulder); an old man kneels for real | L7; LA 15:34 |
| backs of heads | 3/4 or full hair + ears + neck skin — a half-moon of skin read as a smile | L7; LD 17:28, 18:43 |
| saturated props in shade | the red car stays dark red, not purple (`coolShade` removes ~30 % chroma only); use measured red `#e25748` | L7; LD 18:49, 18:59 |
| lit, not pasted | face V ~0.97, side gradient ≤ ~0.5 %, no rim; card casts a soft cool shadow | LGT-03..05; QT l.32–34 |
| framing | hero in frame through key actions; no prop in front of a face; heads not lost at ~20 px (give a gesture) | LA 15:05, 15:31; LD 18:24 |
| camera inside geometry | no lens inside walls/tents (line-of-sight culler) | RC§4; BA l.49–50 |
| inserts | legible, no world shadow across them, moving (push/drift) | LA 15:31; LD 18:22 |
| glints / heat waves | glint ≤ 1/4 of the car, the car stays readable; waves never cross the face | LD 18:24, 18:41, 18:22 |
| readability of the story | the image matches the line (hood up = breakdown signal; chariot drag reads as victory, not gore) | BD; BA l.50 |
| colour/ink numbers | still-level gates: colour state, world ink EW 2.0–2.8 px, outline 4.4 % W, face V | RC§3a |

## 6. Phase 6 — RENDER v1 + QA, fix pass by owner, v2/v3
Freeze the code, render, measure, write `QA_<NAME>.md`:
```bash
node scripts/qa_aquiles_render.mjs out/<name>_v1.mp4 --comp=<Name>Short --audio=audio_<name>/mix.wav --serve=E:/remotion-tmp/<name>_serve_v1
python -I scripts/qa_aquiles.py out/<name>_v1.mp4 --comp <Name>Short --story src/videos/<name>/story.ts --mix audio_<name>/mix.wav [--luz car:INTERIOR]
node scripts/ancoras_<name>.mjs
python -I scripts/folha.py out/<name>_v1.mp4 out/folha_<name>_v1.jpg 120
```
- 1846 frames rendered in **57 s** (12 Chromes × 1) vs 265 s before; the GPU is ~1–2 % busy — the limit is CPU (GPU§2–3).
  Delete the `--serve` folder afterwards.
- **A NEW mp4 name for every render** (v1, v1b, v2…): the QA keys its data by file name (LA 16:10; QA-A l.193–195).
- Light names map to colour states by keyword (day/sun/noon → DIA · golden/dawn/sunrise/sunset/dusk → DOURADO ·
  night/moon → NOITE · lamp/tent/inday/interior/indoor → INTERIOR); anything else needs `--luz name:STATE`.
- Results so far: Achilles v1 **72 PASS · 2 FAIL**; desert v1 63·18 → v2 68·14 → v3 **69·13** (QA-A; QA-D).

**Gate list** (what `qa_aquiles.py` checks; target [fail outside]; codes and n in REFERENCE; QA-A, QA-D3, AC§3.3):
| group | gates |
|---|---|
| format | 1080×1920 · 30.000 fps · H.264 yuv420p · frames = `TOTAL` of the clock (OUT-01/02) |
| montage | 7-f crossfade at every change (ruler 5–12) · hard cuts 0–1 · white flash 0 · changes 1.6–3.3 per 10 s · one long take 7–14 s · change centre − acoustic onset 0 f [p25–p75 −5…+6] (EDT) |
| captions | baseline 1377, ≥ 90 % in 1376–1378 · dark run ≥ 5 px · 1.23–1.38 words/card · card 8–12 f · changes seen ≈ cards planned (CAP) |
| colour per light state | Y′ p50 · p5 outside ink · p99 · lit C* p50/p90 · black outside ink · dark zone a*/b* ±6 · grain ≤ 0.2 (COL-01..04) |
| DOF | visible 20–30 % of time · σ p90 10–20 px (DOF-01/02) |
| camera (front 01) | ≥ 2 px/f 51–92 % (70) · < 0.3 px/f ≤ 10 %, longest still ≤ 23 f · calm push +0.03…+0.50 %/f · glides 1.12–4.89 per 10 s, peak 14–51 px/f · calms with zoom 65–95 % · rolls 1.3–7.7 per 10 s · impacts ≤ 1 (CAM-05..08, -18, -19) |
| camera (AC§3.3) | (1) parallax ≥ 1.2 — locked target ≥ 3.5 · (2) dolly-out ≥ 8 %, crane ≥ 4 % · (3) every shot ≥ 0.27 zoom or ≥ 0.21 widths, ≤ 1 drift-only · (4) frozen 1-s windows ≤ 10 % · (5) arrive moving ≥ 3/4 · (6) head ≥ 0.15 in ≤ 24 % · (7) CU ≤ 3 % · (8) lens ≥ 65° · (9) calm scene change ≥ 1.5 % and e90 ≥ 0.3 · (10) events ≥ 1.0/s |
| ink & faces | world EW median 2.0–2.8 px, p95 ≤ 5 · outline 3.4–6.3 % W · thick/thin 2.5–5 · face gradient ≤ ~0.5 % · face V 0.84–1.0 (INK, LGT-03/04) |
| sound | SFX 5–15/min (locked ~11–14) · end = dry cut at acoustic end + 3 f · without voice −27.9 ± 2 LUFS · with voice −14 LUFS / ≤ −2 dBTP (SND, OUT-03) |

- `QA_<NAME>.md`: deliveries, result count, a table gate · target · v1 · v2 · v3, and **"Failures and whose they are"**
  (owner per failure). Fix pass: each owner fixes in the sandbox, logs, then **ONE re-render per pass** (LA 15:58; LD 18:02).

**Known false alarms of the QA tool** (check before "fixing"):
| QA says | what is really happening | what to do | source |
|---|---|---|---|
| CU 12.5–14.6 % (gate ≤ 3 %) | 2D inserts named thermo/phone/bottle counted as close-ups; real detector CU 1.3–1.9 % | name insert sets `insert_*` | LD 17:22; QA-D |
| golden p99 / darks fail in time-lapse shots | `lapseDusk`/`lapseDawn` mix golden AND night; the tool scores the whole shot as DOURADO | read per frame; report as a ruler limit | QA-D v1–v3 |
| SFX/min 24.8 (gate 5–15) | with no music/voice the onset detector re-counts every tail still sounding 0.24 s later; the propeller loop's pulses counted up to 4× | count planned events in `cues.md`; keep tails ≤ ~0.23 s, smooth loop envelopes | LD 18:17 |
| SFX/min 60–73 with the real voice | with voice and no music it counts speech attacks (73.2/min on `aquiles_v2c_sem_musica`) | judge SFX on the SFX stem / `cues.md` | PT-A l.98–100 |
| "music continuous: PASS" with no music | voice/SFX fool the chromagram | ignore (L5) | PT-A l.100; QA-D v2 |
| outline 2.04 % W, thick/thin 8.40 | the white engine air filter was detected as a head (n = 1–2 heads) | check which heads were measured before touching `toon.ts` | LD 18:43; QA-D |
| impacts (≥ 3 f alternating) | RANSAC alternates between the cast layer and the background during arcs — no visible shake | re-render the window with `--props='{"post":{"cast":false}}'`; real if it persists without cast | LA 16:25; QA-A |
| crane 3.0 % (gate ≥ 4) | crane with changing pitch classified as "roll" | add a pure vertical rise of ~1 s | QT l.80, 213 |
| DOF 34 % | heat-haze shimmer counted as blur | scale the haze (×0.55 in the desert) | LD 18:02 |
| caption changes 193–196 × 167 planned | 2D inserts change text inside the caption band | ignore if `clock.ts` cards = planned | QA-D v1; QA-D3 l.51 |
| frozen 1-s windows high | static 2D inserts | a real issue: give inserts a push + drift + parallax | QA-D v1; LD 18:22 |
| camera numbers identical after a fix | old cache reused the camera `.npz` for the same mp4 name | fixed (recompute + `carimbo.json` + lock), still render to a new name | LA 16:10, 16:30 |
| white flash 9 f (e.g. 125–133) | the lens passes close to white architecture (porch posts, steps, trim) that fills > 35 % of the frame — no real flash | look at the frames; keep the lens off big white surfaces if it reads harsh | zombie v3/final, `rc_teste/qa/zumbi/flash.jpg` |
| ink outline / face V / face gradient fail with n = 2–6 "heads" | the head detector picked house trim, windows, a poster's printed face, a back of a head | crop what it measured (`qa/zumbi_chars/qa_heads.jpg`) before touching `toon.ts` | zombie v1–v3 |
| SFX/min 60–70 on the final or only 9 onsets on the mix | with voice it counts speech attacks; with ambience beds the raised floor hides SFX onsets | judge SFX/min from `audio_<name>/cues.md` | zombie final |
| QA of a 2K render | the rulers (px/f, caption baseline 1377) are calibrated at 1080 | run `qa_aquiles.py` on a lanczos 1080 copy: `ffmpeg -i out/X_2k.mp4 -vf scale=1080:1920:flags=lanczos -c:v libx264 -crf 16 -pix_fmt yuv420p -c:a copy out/X_qa1080.mp4` | zombie v3 |

**Typical real failures and owners:** impacts from the cast (CHARACTERS: the lens passing closer than 1.9 m to extras, torso
snapping, sit→stand jumps, sliding while "frozen", view flips mid-step, sparkles jumping) · glides/10 s > 4.89 from too
many emphasis moves (CAMERA) · no long take, frozen windows (CAMERA/FX) · colour darks per light (LEAD) · loudness of
the SFX-only mix (SOUND: −27.9 ± 2 LUFS without voice) (QA-A Failures; QA-D; LA 16:04–16:25).

## 7. Phase 7 — VOICE (right after the script is approved — L3; steps 1–8 before the build, step 9 at the end)
**ElevenLabs in the built-in browser pane** (load `anthropic-skills:built-in-browser` first; the user is signed in
there, D4 — an older 29/10 note (MEM-EL) said the user's Chrome; the 02/11 decision wins; never sign in yourself).
UI facts: BR l.77–80 + MEM-EL.
1. Text to Speech → voice picker → **Explore** tab → search the full name **"Alex - Upbeat, Energetic and Clear"** →
   **Use** (it is a Voice Library voice, not under "My voices").
2. Model **Eleven v4**. Sliders are Radix `[role=slider]` with `aria-label`: focus each by aria-label and use
   ArrowLeft/Right (step 0.01) to **Stability 0.38 · Similarity 0.75 · Clone strength 0**; read `aria-valuenow` back.
   v4 has no speed slider (the file name stamps `sp101` = default speed; nothing to do).
3. **Output Format** menu → **MP3 44.1 kHz (192 kbps)** (default is 128). **Language: Auto**. Leave "Auto-tag" untouched.
4. Editor: clear it with a Range `selectNodeContents(editor)` + `document.execCommand('delete')`, insert the script
   (spoken lines only, no `#` header) with `execCommand('insertText', …)`; verify the text length.
5. **Generate ONCE** (one click returns 2 generations). Download the first → a Windows Save dialog opens: tell the user
   in one line to click Save. Copy the file **immediately** to `voice/<name>/alex/alex_<name>_en_take1.mp3` (a second
   download overwrites the same name). Lost it? Re-download from the **History** tab. Use this take; only regenerate if
   it misreads a word (step 6 shows it).

**Timings, tightening, swap** (system `python` has faster-whisper; LD 19:21, `audio_deserto/voz/aperto.log`):
```bash
# 6. word timings: faster-whisper small.en on GPU, aligned to the script, acoustic onsets (onsets10) + acoustic ends
VOZ_ROTEIRO=../rc_roteiros/<name>/ROTEIRO_<name>_vN.txt VOZ_PROVISORIO=voice/<name>/words.json \
  python -I scripts/audio_aquiles_voz.py palavras voice/<name>/alex/alex_<name>_en_take1.mp3 audio_<name>/voz
# 7. tighten pauses only (OUR values — the script's defaults are Zack's)
python -I ../research_notes/Estudo200Recentes/codigo/10_ESPACAMENTO_NARRACAO/apertar_pausas.py \
  voice/<name>/alex/alex_<name>_en_take1.mp3 audio_<name>/voz/alex_<name>_en_take1_palavras.json audio_<name>/voz \
  --modo teto --frase 0.10 --virgula 0.05 --teto 0.18 --inicio 0.05 --cauda 0.12 --sufixo _apertada
# 8. clock in the clock.ts format (acoustic end of the last word measured on the tightened voice; caption `leg` copied)
VOZ_ROTEIRO=../rc_roteiros/<name>/ROTEIRO_<name>_vN.txt VOZ_PROVISORIO=voice/<name>/words.json \
  python -I scripts/audio_aquiles_voz.py relogio audio_<name>/voz/alex_<name>_en_take1_apertada.wav \
  audio_<name>/voz/alex_<name>_en_take1_apertada_palavras.json audio_<name>/voz/words_alex_<name>.json "Alex v4 take1, pauses tightened"
# 9. ONE-command swap: SFX re-timed from SFX_EVENTS on the new clock + mix + master −14 LUFS / −2 dBTP
../tools/chatterbox_venv/Scripts/python.exe scripts/audio_<name>.py --voz audio_<name>/voz/alex_<name>_en_take1_apertada.wav \
  --palavras audio_<name>/voz/words_alex_<name>.json --instala
```
- Check `*_casamento.json` (every script word matched; Whisper normalises numbers and homophones — "bare skin" →
  "bearskin" — times are redistributed, LD 19:21) and `*_apertada_relatorio.json` (`depois`: sentence pause ~0.10,
  largest ≤ 0.18, voice start 0.05). Desert: 69.07 → **64.26 s**, 3.25 → 3.49 w/s, 27 cuts; Achilles: 71.16 → 66.42 s.
- `--instala` writes `voice/<name>/words.json` (keeps the placeholder as `words_provisorio.json`) and `voice.wav`;
  `final.wav` = voice + SFX mastered. Then CHARACTERS re-checks `ACTION_SHOT`, LEAD runs `ancoras_<name>.mjs`
  (with the real voice Achilles' "kills" fell 1 f before its shot and lost its strike sound — LA 16:45–16:48).
- **Measure every stem** (SOUND reports in `info_voz.json` / `voz/troca_voz.json`; BS.1770 on the original channels via
  `../estudo_ricksclips/codigo/09_SOM/s09_comum.py` + ebur128). Desert final: −14.0 LUFS, TP −2.15 dBTP, LRA 1.6, voice
  −14.0, SFX −28.2 LUFS (−14.2 LU), voice compression p90−p10 7.8 → 4.6 dB, every SFX below the voice in 300–3400 Hz.
- Never time-stretch or pitch-shift, even if over 66 s (L4) — cut words in the script instead (Phase 2).

## 8. Phase 8 — FINAL RENDER & DELIVERY
```bash
node scripts/qa_aquiles_render.mjs out/<name>_final_voz.mp4 --comp=<Name>Short --audio=audio_<name>/final.wav   # 1080p for the QA tool
node scripts/qa_aquiles_render.mjs out/<name>_final_2k.mp4 --comp=<Name>Short --escala=1.3333333 --audio=audio_<name>/final.wav   # L15: the 2K file to upload
../tools/ffmpeg/ffmpeg.exe -y -i out/<name>_final_2k.mp4 -vf scale=-2:1080:flags=lanczos -c:v libx264 -preset slow -b:v 2900k -maxrate 3500k -bufsize 7000k -c:a aac -b:a 192k -ar 48000 -movflags +faststart out/<name>_final_1080p_phone.mp4
python -I scripts/qa_aquiles.py out/<name>_final_voz.mp4 --comp <Name>Short --story src/videos/<name>/story.ts --mix audio_<name>/final.wav
../tools/ffmpeg/ffmpeg.exe -hide_banner -i out/<name>_final_voz.mp4 -af ebur128=peak=true -f null - 2>&1 | tail -14
../tools/ffmpeg/ffmpeg.exe -y -i out/<name>_final_voz.mp4 -vf scale=720:1280 -c:v libx264 -crf 23 -c:a copy -movflags +faststart out/<name>_final_voz_leve.mp4
python -I scripts/folha.py out/<name>_final_voz.mp4 out/folha_<name>_final.jpg 120
```
- Verify: 1080×1920 @ 30.000 H.264; frames = `TOTAL` (≤ 1980); **I = −14.0 LUFS (±0.5), TP ≤ −2.0 dBTP**, LRA ~2;
  ends 3 frames after the last word, no fade (OUT-01..05). `_leve` = 720×1280, CRF 23, same audio (PT-A l.7): our copies
  are 16.7–24.7 MB (≤ 30 MB, L11).
- **Credits:** prefer CC0 (both examples shipped with **0** CC-BY lines). If a CC-BY model appears in the final cut, add
  its line from the ledger to the description (`ASSETS_EXTERNOS.md` "Credits for the video description" — only what
  really appears). CC0 sound credits are optional (AE § Som).
- **Packaging** (00§5): description = the title; 0 tags; category Entertainment; auto-dubbing on; **thumbnail = the
  custom cover of §8.1** (L12; overrides PKG-05); 1 video/day at a fixed hour.
- **Report to the user** (short): file paths (full + `_leve` + contact sheet + `QA_<NAME>.md` + cover PNG/JPG), duration/frames,
  measured I / TP / LRA, QA PASS·FAIL count with the remaining failures and why, credit line (or "none").

### 8.1 Cover (custom thumbnail) — L12, user 03/11/2026
**What it is:** the YouTube **thumbnail** (on Shorts the app calls it the **cover**). The style asked for is a
**split-screen "versus" (reaction) thumbnail**: a big outlined headline on top + two characters with opposite, exaggerated
emotions on a diagonal split with contrasting colours. It exists **only as the cover — never inside the video** (frame 0
stays the assembled scene, PKG-06; no title card, no end card). The study's channel used a video frame 24/24 (PKG-05), so
this is a user decision, not measured on the channel.

| element | rule |
|---|---|
| **headline** | **the video's main line, never a generic phrase** ("WHAT WENT WRONG?" was only the style example): 2–4 words taken from the title or the hook's paradox (admiral: **"ONLY 13 SHIPS"** or **"13 VS 133"**). Numbers as digits. **No flag-risk words or images** (user 03/11: "DEAD might flag"): no DEAD/KILL/BLOOD/MURDER/CORPSE and no blood drawn on the cover — name the TOPIC word people search for + a curious hook (user 03/11: "we should say vampire and something" → vampire: "THE FIRST VAMPIRE", not "DEAD 10 WEEKS"). ALL CAPS, heavy rounded sans, white fill, thick black outline (~8 % of the letter height) + hard drop shadow; top ~20 % of the frame, max 2 lines, ≥ 120 px cap height. No emoji, no CTA, no channel name |
| **format** | long-form (16:9) video: **1920×1080**, keep the bottom-right ~20 % free (duration badge) — example `rc_teste/src/videos/vampiro/Cover.tsx` (`VampiroCover`, 2D canvas with the toon cards over blurred frames of the video). Shorts: **1080×1920 PNG** (9:16, how Shorts covers show); JPG copy **≤ 2 MB** (YouTube thumbnail limit); headline and both faces inside the central band (y 200–1600) — the bottom ~15 % sits under the app's buttons/title |
| **split** | one diagonal seam ~10–15° off vertical with a thin light line; **hero side** = warm saturated background (golden/red light state, blurred world behind); **other side** = the loser / mocker / victim, cool desaturated blue-grey background |
| **characters** | OUR OWN 2D cards from `toon.ts` (the story's outfits — never a character drawn from another channel, L2), drawn big: head ≈ 85 % of its panel width, eye level, front or 3/4 view. Emotions pushed past the video's acting: hero = determined/angry brows down, mouth set; other = crying (big tear streams, open mouth) or shocked. One clear prop per side if it tells the story (admiral: helmet + a few ships behind; enemy commander: his fleet jammed/burning behind) |
| **match the video** | same outfits, colours and world as the video (the cover must not promise a different film); cartoon only, no gore (BA) |
| **phone check** | downscale to 180 px wide (feed size): the headline and both emotions must still read; if not, cut words or enlarge faces |

**Build:** LEAD owns `src/videos/<name>/Cover.tsx` (reuses the engine: `world.ts` background with lens blur, `toon.ts`
cards; CHARACTERS adds the two exaggerated faces to `toon.ts` — add, never rename). Register a still in `src/Root.tsx`:
`<Still id="<Name>Cover" component={<Name>Cover} width={1080} height={1920} />` (hyphen/no "_" in the id, P1). Render:
```bash
TEMP=E:/remotion-tmp TMP=E:/remotion-tmp npx remotion still src/index.ts <Name>Cover out/<name>_cover.png
../tools/ffmpeg/ffmpeg.exe -y -i out/<name>_cover.png -q:v 3 out/<name>_cover.jpg      # must be ≤ 2 MB
../tools/ffmpeg/ffmpeg.exe -y -i out/<name>_cover.png -vf scale=180:-1 out/<name>_cover_phone.png   # phone check
```
Build it after the picture is approved (Phase 5–6), show it to the user with the final delivery.
**Upload:** set it as the thumbnail/cover when uploading the Short (YouTube app upload screen). If the account only
offers "pick a frame" for Shorts, tell the user — **never** solve it by putting the cover inside the video.

## 9. Pitfalls & fixes (from the team logs)
| # | symptom | cause → fix | source |
|---|---|---|---|
| P1 | Composition won't register | "_" in the id → use `<Name>-<role>` | LA 14:36 |
| P2 | action on the wrong occurrence of a word | `R.back12` = 752 (2nd "back") → index words by sentence | LA 15:05, 15:31 |
| P3 | "white bars" beside/over characters | `fxSpeed` drawn as thick white stripes → removed; 2 small dust puffs at the feet | LA 15:20, 15:34 |
| P4 | sea visible inside the ships | deck face pointed down (culled) → plank deck facing up, DoubleSide hull, gunwales, benches | LA 15:17 |
| P5 | Greek king read as a woman in a dress | long robe → burly build, short tunic, legs, beard, cloak on one shoulder, sceptre | LA 15:34 |
| P6 | cards "lying flat" under a high lens | camera > 30° above near characters → limit tilt + cards tilt to the lens | LA 15:28–15:30 |
| P7 | kneeling old king read as standing | dress drawn to the floor → `SideOpts.mode "kneel"`, cloak spread | LA 15:05, 15:34 |
| P8 | hero floating | no rock under the anchor → build what the character stands/sits on (`seat` height) | LA 15:05, 15:17 |
| P9 | FOREGROUND objects missing / popping | not mounted in `world.ts`; vanished mid-shot (read as impact) → mount; keep until end of shot | LA 15:30, 16:25 |
| P10 | character walks through a fire | prop in the path → move it; shared positions become a contract (`FIRES` in `geo.ts`) | LA 15:30 |
| P11 | shadow band across the insert | insert received the shot's sun shadow → inserts don't receive shadows | LA 15:30 |
| P12 | hero leaves frame during the orbit; chariot exits, empty field | camera path → keep the hero in frame through key actions | LA 15:05 |
| P13 | impacts at a pull-out through extras | lens crossed soldiers at 0.4 m → fixed lateral offset ≥ 1.9 m from the lens | LA 16:25 |
| P14 | jitter on sit→stand, lunges, "frozen" walker | snap poses / side jumps / residual slide → hold 6 f + return 6 f, rise in 3 f in place, true stop | LA 16:25 |
| P15 | "shake" on a smooth camera | lateral slide 0.2 m/f along repeating stone blocks → approach frontally, slower | LA 16:03 |
| P16 | view flips front/side/back every frame in an arc | view taken from the moving lens → fixed reference lens between keys; arm blends ≥ 5 f | LD 18:43 |
| P17 | "!" trembling; sparkles jumping place every frame | effect re-placed per frame → enter dry, fixed position | LD 18:43; LA 16:25 |
| P18 | strike silent after the voice swap | "kills" fell 1 f before the shot → `ACTION_SHOT` clamp ≥ a+3, ≤ b−4; recheck anchors | LA 16:45–16:48 |
| P19 | real voice over 66 s | 227-word script; pauses already at the channel's medians → write ≤ 225 words and check at 3.42 w/s | LA 16:48 |
| P20 | SFX-only mix too loud (−25.4 LUFS) | SFX sum → SFX −4 dB, strongest −6 dB (`SFX_DB`, `SFX_FORTE_DB`) → −27.0 | LA 16:04–16:20 |
| P21 | Remotion bundles slow / disk filling | 1.2 GB of `_raw.glb` in `public/` → raw files to `biblioteca_3d/meshy_raw/`, only `_lowpoly` in public | LA 17:09, 17:14 |
| P22 | Meshy "Subscribe to download"; Sketchfab needs login | paywall / account → skip; never pay, never sign in; the "Save as" download route is forbidden | LA 15:29; AE; BIB l.8 |
| P23 | Studio slow on the user's Chrome | that Chrome renders in software (Basic Render Driver) → reopening Chrome fixes it; user's decision, don't touch | GPU§5 |
| P24 | QA report overwritten by a check render | default output name → report is now `QA_<COMP>_auto_<mp4>.md`; use a new mp4 name | LA 15:51, 16:30 |
| P25 | QA crashes `UFuncOutputCastingError` | all-integer camera vector at `qa_aquiles.py:665–666` → `dtype=float` (QA) or a non-integer component | LD 17:22, 18:02 |
| P26 | heat waves as thick white bands over the driver | full-opacity white cards in front → thin, translucent, sand-coloured, ≥ 7 m from lens and behind him | LD 17:27, 18:22 |
| P27 | DOF blurs the subject | heat-haze pass placed before the lens → after `lens.main` | LD 17:56 |
| P28 | wing-rock animation never seen | it started after its shot ended → animation inside its own shot | LD 17:56 |
| P29 | 2D inserts frozen; no 7–14 s take | full-screen inserts without a camera; script without a natural long beat → insert push/drift/parallax; merge beats into one long shot with `BEATS` | LD 18:02–18:24 |
| P30 | POV "tiny dot" invisible (4 px) | 0.25 m drawing at 49 m → real-size 1.7 m card; dot 4–5 % of frame height, centred above the caption | LD 18:24, 18:47 |
| P31 | glint hides the car | star over the whole car → corner sparkle ≤ 1/4 of the car width | LD 18:24, 18:41 |
| P32 | red car in the "dark zone" even in sun; then purple in shade | cherry `#c8323a` → measured red `#e25748`; violet shade tint → chroma −30 % only | LD 18:49, 18:59 |
| P33 | darks too cold after the red change | grade Cb pushed blue → Cb back to warm (~+0.01) | QA-D v2 note; LD 18:59 |
| P34 | first dawn frame = deep night (black 0.70 %) | dawn ramp started too dark → start at blue hour | LD 18:49 |
| P35 | car interior unreadable (pink flat field, seats like planks, red roof) | missing detail → gauges, vents, radio, wheel spokes, fabric headliner, vinyl seats, tinted windshield band | LD 17:32, 18:17, 18:25 |
| P36 | oven shot: egg off-axis | anchor 21° off the lens axis → `DASH_EGG` on the dashboard centre-back, lens over the dash | LD 17:27, 18:24 |
| P37 | contour/thick-thin far off target | `inkRing`/`INK_W`/`INK_K` too strong → 3.1 u / 0.52 (and check which heads the QA measured) | LA 15:51; LD 18:43 |
| P38 | dark-zone a*/b* fail in a light state | saturated darks → desaturate darks per light in `grade.ts`, neutral shadow ink | LA 15:51 |
| P39 | a sandbox shows old sets/world | copied before the lead's update → re-sync all non-owned files before every batch | LD 17:13 |
| P40 | a node script importing `cast.ts` crashes | canvases created on load → inject a fake `document` (see `audio_deserto_eventos.mjs`) | LA 15:58 |
| P41 | grain / file bloat | grain off (the channel has none) | RC§4; 02§1.5 |
| P42 | Remotion output has a mute audio track | mux `-map 0:v:0 -map 1:a:0` (`qa_aquiles_render.mjs --audio` does it) | RC§4 |
| P43 | `tsc` breaks on draft files | `.ts` drafts in `out/` → save drafts as `.txt` | RC§4 |
| P44 | lens long (37–44°) = "too close, no space, no life" | the original test's camera → 70° lens, travel in every shot, arrive moving, life between beats | AC§0, QT v4 |
| P45 | user: the man in the 2D explainer inserts "doesn't look like our style" | FX drew its own figure (big separate head, diagram body, realistic hand) → every person in an insert is the cast card painted with `toon.ts` (`bodyFront(p, OUTFIT, {...})`), only the diagram layer (gauge, arrows, labels) is FX's own; no realistic hands (our cards have stick limbs) | user 03/11 (vampire v1) |
| P46 | user: "we lost the quality of character we had on Achilles"; "the enemies are not our style" | closed Corinthian helmets left only a box-shaped mask; Persian turbans wrapped the head and big black beards covered half the face; gold head + gold shield merged → L16: face always visible, headwear on top, small beards, contrast head/body/shield, enemies = same bean-head design | user 04/11 (Thermopylae v1) |
| P47 | user: "the action of the fight looks poor" | waves just walked into the shield wall and tipped over; same 2–3 poses; crowds of 30–60 small cards, no hero moments → L17: 3–5 choreographed hero beats at MS/FS (anticipation → hit → reaction), crowds only as background | user 04/11 (Thermopylae v1) |
| P48 | characters lost against the background after the blur was removed | Achilles' DOF used to separate them; sharp busy cliff with dark crack lines competed with the ink → L18: lighter, lower-chroma, simpler backgrounds | user 04/11 |
| P49 | user: "the main character appears inside the table" | cast marks placed inside the workbench volume (bench top + shelf boxes cut legs/waist; flat cards are depth-tested) → every figure's feet ≥ 0.45 m in front of any furniture face (benches, counters, tables, rails, boards); CHARACTERS checks every set's marks against the furniture boxes in `geo.ts`, then stills of every beat where someone stands near furniture | user 04/11 (zombie v2 garage 780–880) |
| P50 | user: "the last seconds look off, slow motion, bad movements" | the last shot was a ~5 s slow backward drift THROUGH the gazebo's glass panels/railing (bars sweeping across the frame, dark empty floor ⅓ of the frame) while the family stood frozen → last shot: no rails/posts/glass across the frame at any time, a confident move at normal speed with a quick crane/pull-out on the final key word, floor ≤ ~25 %, figures lined across the lens (no overlaps) with real reactions ON the closing words, the callback figures (zombies) placed where the final reveal sees them; check the last 6 s as a 10-f tile (`ffmpeg -ss <T−6> -vf "select=not(mod(n\,10)),scale=216:384,tile=9x2"`) | user 04/11 (zombie final) |
| P51 | voice clock has extra "words" / mis-indexed actions | the checker slot tags `[G] [C] [E] [M] [V] [D]` at line ends are read as words by `audio_aquiles_voz.py` and the placeholder script → give the voice tools a tag-free copy (`ROTEIRO_<name>_vN_voz.txt`, `sed -E 's/\s*\[[A-Z]\]\s*$//'`) and strip tags in `placeholder_words_<name>.py` | zombie 04/11 |
| P52 | ElevenLabs page shows "Welcome back"/sign-in in the built-in pane though the user is signed in "in my browser" | the pane has its own profile, separate from the user's Chrome → ask the user to sign in INSIDE the pane (Ctrl+Shift+B to show it) or offer Claude in Chrome; never sign in yourself. Stability slider: keyboard steps lose focus after each re-render → step it one ArrowLeft keydown at a time with a refocus (JS loop, 150 ms) and read `aria-valuenow` back. A "Voice Design" popup can open from the promo card — close it without generating | zombie 04/11 |

## 10. Reference card
`REFERENCE.md` (this folder): every coded rule with **target · gate · n · strength · source** (the QA gates of §6 are
the OUT/EDT/CAP/COL/DOF/CAM/INK/SND codes), the QA false alarms (QAF), and what our two finished videos measured. When a study number and a locked rule disagree, the
locked rule wins (L1–L11); when a production lesson (LOG) and the study disagree, keep the LOG value that passed QA and
note it.
