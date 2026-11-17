# REFERENCE — make-cartoon-story-short: the coded rule card (v1, 02/11/2026)

Every rule the skill uses, with **target · gate · n · strength · source**. **Target** = median per video of the 24
Ricks Clips Shorts (or our value where marked); **gate** = p05–p95 per video unless noted (what fails). Velocities in
px/frame at 720p (×1.5 = 1080) unless noted. "q"/"f" = frame at 30 fps.

**Strength** (study scale, HM l.8–9): **●●●** strong (measured on all 24, large n, ruler checked) · **●●** moderate
(medium n, one coder's eye, or indirect ruler) · **●** indication (small n, one video, or inference) · **USER** = binding
user decision (beats any study number) · **LOG** = our own production lesson (1–2 videos; no channel measurement).

**Source keys** (paths from `<your project folder>\`):
| key | file |
|---|---|
| HM§n · RC§n · CF · AU · BT | `estudo_ricksclips/HANDOFF_MESTRE_RC.md` · `RECEITA_THREEJS_REMOTION.md` · `CONFERENCIA_MR_OMI.md` · `AUDITORIA_RC.md` · `BUILD_TESTE.md` |
| NN§x | `estudo_ricksclips/frentes/NN_*.md`, section x (e.g. 08§1c) |
| D1–D11 · BR l.n | user decisions in `rc_teste/BRIEF_SKILL.md` (l.29–59) · a line of that file |
| AC§n | `rc_teste/ANALISE_CAMERA.md` |
| QT · QA-A · QA-D · QA-D3 · PT-A | `rc_teste/QA_TESTE.md` · `QA_AQUILES.md` · `QA_DESERTO.md` · `QA_DESERTO_auto_deserto_v3.md` · `QA_AQUILES_PTBR.md` |
| LA hh:mm · LD hh:mm | entry in `rc_teste/EQUIPE_AQUILES_LOG.md` · `rc_teste/EQUIPE_DESERTO_LOG.md` |
| EA · ED · BA · BD | `rc_teste/EQUIPE_AQUILES.md` · `EQUIPE_DESERTO.md` · `BUILD_AQUILES.md` · `BUILD_DESERTO.md` |
| GPU§n · AE · BIB | `rc_teste/qa/aquiles/GPU.md` · `rc_teste/ASSETS_EXTERNOS.md` · `biblioteca_3d/BIBLIOTECA.md` |
| MEM-EL | our ElevenLabs web notes (29/10) |
| CHK | `estudo_ricksclips/codigo/08_ROTEIRO/confere_roteiro.py`, run on 02/11 at 3.42 w/s |

---

## LOCK — user decisions (summary; full text in SKILL.md §0.1)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| LOCK-01 | decide and proceed; ONE recommended version, never a menu | — | — | — | USER | D1 |
| LOCK-02 | script first, user approves; sourced facts; no film/channel copying; virgin topics | — | approval | — | USER | D2 |
| LOCK-03 | build first on a placeholder clock, real voice later | — | — | — | USER | D3 |
| LOCK-04 | Alex v4: stab 0.38, sim 0.75, clone 0, MP3 44.1 kHz 192 kbps, Language Auto, built-in pane, ONE take; ≤ ~215–225 words; tighten pauses only | 3.42 w/s | ≤ 66 s | 2 videos | USER | D4 |
| LOCK-05 | no music | voice + literal SFX | — | — | USER | D5 |
| LOCK-06 | master / SFX levels | −14 LUFS, SFX ~14 LU under voice, ~11–14 SFX/min | TP ≤ −2 dBTP | — | USER | D6 |
| LOCK-07 | visual feedback rules (no speed lines, no lying-flat cards, solid objects, legible costumes, no blob heads, red stays red, lit cards) | — | stills review | — | USER | D7 |
| LOCK-08 | camera rules | see CAM | see CAM | — | USER | D8 |
| LOCK-09 | CC0 / CC-BY only; no spend, no sign-in; lean `public/` | 0 credits | — | — | USER | D9 |
| LOCK-10 | temp `E:\remotion-tmp`; RTX 5090; 12 Chromes; Studio 3010 never stopped | — | — | — | USER | D10 |
| LOCK-11 | 1080p + 720p `_leve` copy; report loudness | — | `_leve` ≤ 30 MB | — | USER | D11 |

## VW — what drives views (hit × flop inside the 24; flops = 4 below 1 M)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| VW-01 | format change (third-party comics → own 2D-in-3D animation) is what made the channel | 0.53 M → 7.14 M median | — | 114 + 24 | ●●● (package, not one item) | HM§11; 00§2 |
| VW-02 | duration inside 39–66 s | 20/20 non-flops inside; flops at 31, 35, 68, 78 s (7.86 M × 0.36 M) | 39–66 s | 24 | ●● (confounded with topic) | HM§11; 00§2 |
| VW-03 | protagonist with stakes | 3/4 flops have none | — | 24 | ●● | HM§11; 08§2 |
| VW-04 | real fact + 3rd-person protagonist | 8/8 ≥ 4.6 M (median 8.04 M) × invented 3.14 M (n=5); legend 1.6 M, fiction 3.1 M | — | 24 | ●● / ● (legend) | HM§11; 08§2; 08§5a |
| VW-05 | 2nd-person "Imagine/you" mode also works | 6 videos · 7.14 M · 2 flops | — | 6 | ● | 00§1e |
| VW-06 | mockers proved wrong | 7/7 ≥ 4.6 M (9.51 M) × 6.56 M | — | 24 | ●● | HM§11 |
| VW-07 | ending that recontextualizes; late pivot | reversal 8.98 M (n=6); dry explanation holds 3 of 4 flops; ρ(pivot pos, log views) +0.36 (n=18) | — | 24 | ● | HM§11; 08§2 |
| VW-08 | visual style does NOT separate hits from flops (entry ticket) | all |ρ| ≤ 0.31 | — | 24 | ●● | HM§11 |

## PKG — topic, title, packaging
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| PKG-01 | duration | 60–65 s (locked phase 63.5 s [57–71]) | **39–66 s = 1170–1980 f** | 24 | ●● | HM§1; 00§5 |
| PKG-02 | title: Title Case, no ? ! emoji #, names the OBJECT never the mechanism | 6 words, 32 chars | 4–7 words, 24.6–44.7 chars; mechanism 0/24 | 24 | ●●● | HM§1; 00§1c |
| PKG-03 | title moulds | "The [Object] That/Who…" 5 v · 13.4 M · 0 flops; "Why [Plurals]…" 5 v · 8.0 M · 0 flops | avoid "How X Actually Works", "The Science Behind X" | 10 | ● | HM§1; 00§1e |
| PKG-04 | description = title; 0 tags; Entertainment; auto-dubbing | 24/24 | — | 24 | ●●● | HM§1; 00§1c |
| PKG-05 | thumbnail = a frame of the video with the caption word — **overridden by L12** (custom split-screen cover, SKILL §8.1) | position 0.51 of duration | — | 24 | ●●● (USER override) | HM§1; 00§1d; user 03/11 |
| PKG-06 | frame 0 = assembled scene, character visible; no logo/title/intro | 22/24 | — | 24 | ●●● | HM§1; 00§1c |
| PKG-07 | cadence | 1/day scheduled (24.0–27.7 h intervals) | — | #15–#23 | ● | HM§1; 00§1b |
| PKG-08 | topic: a REAL mechanism, preferably in a historical setting | physical 8.70 M (n=9) ≈ rule/law/scam 7.71 M (n=11); historical 9/9 > 1.6 M; invented/future 3.37 M (n=4) | — | 24 | ● | HM§1; 00§1e; 08§1g |
| PKG-09 | virgin topic: check the channel's 146 titles | 0 overlaps | `meta/sh_RicksClips3000.tsv` | 146 | — | HM§1; 08§5a |

## SCR — script (run CHK at 3.42 w/s; must print PASSA)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| SCR-01 | words (Alex budget) | ≤ 215–225 | duration ≤ 66 s at 3.42 w/s | 2 videos | USER | D4; CHK |
| SCR-01b | words (channel, at 3.70 w/s) | 205–230 (217) | 138–246 | 24 | ●●● | HM§2; 08§1b |
| SCR-02 | sentences · words per sentence | 14–16 (14.5) · 13–14 (14) | 9.2–22.7 · 10–20 | 24 | ●●● | HM§2; 08§1b |
| SCR-03 | punch ≤ 5 words · run-on ≥ 25 words · "So," openers (share of sentences) | 10 % (17/24) · 7 % (15/24) · 10 % (23/24) | 0–34 % · 0–24 % · 4–29 % | 24 | ●● | HM§2; 08§1b |
| SCR-04 | hook = paradox stated as FACT, 1 sentence | 14 words, ends at 3.7 s; house ≤ 16–17 words | 7–20 words; 2.2–6.0 s | 20/24 | ●● | HM§2; 08§1c; BR l.66 |
| SCR-05 | hook moulds | "He + past + absurd act" 11/24 (7.7 M); "X is illegal/impossible, yet Y" 2/24 (14.7 M); conditional "If you…" 5 · 8.0 M · 1 flop | never a question; never "You just…" | 24 | ●● / ● | HM§2; 08§1e; 00§1e |
| SCR-06 | setting: who/where/stakes; ≥ 1 number; never the year | 2 sentences, ends at 25 % of speech; 4.5 numbers | 1–3.9 sentences; 15–39 %; numbers 24/24; year 1/24 | 24 | ●● | HM§2; 08§1c |
| SCR-07 | escalation beats, mockers proved wrong, direct lines read by the narrator | 6 beats (house 5–7); mockers 7/24; 1 line | IQR 4–7; 0–3 lines | 24 | ●● | HM§2; 08§1c |
| SCR-08 | jokes: dry irony > exaggeration > mockery > punch; no "Luckily/Unluckily" | 2 (irony 21/52, exaggeration 12, mockery 7, punch 3) | 0–4.9; L/U 1/24 | 24 (52 jokes) | ●● | HM§2; 08§1f |
| SCR-09 | mystery "Wait…?" (house mould: both approved scripts have it) | 13/24 have a mystery, at 31 % | 12–78 %; "Wait" 3/24 | 24 | ●● (optional in the channel) | HM§2; 08§1c |
| SCR-10 | pivot "You see," + the hidden rule | 72 % of speech (house ~55–75 %) | 45–85 % | 10 explanation uses in 16/24 | ●● | HM§2; 08§1d; BR l.67 |
| SCR-11 | analogy | optional | 4/24 | 24 | ●● | HM§2; 08§1c |
| SCR-12 | ending: reversal/twist + callback; last sentence among the longest; ends on the word | ending 20 words; last sentence 17 words; callback 21/24 | 13–43; 6–31; last ≥ median in 18/24 | 24 | ●● | HM§2; 08§1c |
| SCR-13 | person: 3rd, protagonist unnamed; hook past → narration present | 3rd person 10/12 (current phase); unnamed 20/24 | — | 24 | ●● | HM§2; 08§1g–h |
| SCR-14 | facts with real sources in the `#` header; no film-invented scenes | both examples | — | 2 | USER | D2; BA |
| SCR-15 | checker | `RESULTADO: PASSA` | desert v3 PASSA (65.20 s); Achilles v2 REVER (66.37 s) | 2 | LOG | CHK |
| SCR-16 | no CTA in speech | 0/24 | — | 24 | ●●● | 00§1c |
| SCR-17 | numbers in captions as digits (`leg` field of the clock) | "115", "1,000" | — | 2 | LOG | LD 17:13; placeholder scripts |

## VOI — voice (L4 locks the generator and settings)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| VOI-01 | pace after tightening (Alex v4) | 3.42 w/s (Achilles 227 w / 66.42 s; desert 223 w / 64.26 s = 3.49) | land ≤ 66 s | 2 | USER / LOG | D4; LA 16:48; LD 19:21 |
| VOI-01b | channel pace | 221 w/min = 3.70 w/s; 4.77 syl/s | 208–239 w/min; 3.47–3.99 w/s | 24 | ●●● | HM§3; 09§1.1 |
| VOI-02 | sentence pause | 0.10 s (ours 0.095–0.10 Silero) | nothing > 0.25 s | 24 | ●●● | HM§3, §12; LD 19:21 |
| VOI-03 | comma pause | channel 0.03 s; ours 0.05–0.07 | — | 24 | ●●● / USER | HM§3; D4 |
| VOI-04 | largest pause | channel 0.19 s; ours ceiling 0.18 (measured 0.11–0.13) | 0.13–0.26 s; 0 pauses ≥ 0.40 s | 24 | ●●● | HM§3; LA 16:48; LD 19:21 |
| VOI-05 | first phoneme on frame 2 (0.05–0.07 s) | ours 1.6–1.9 | frames 2–3 | 24 | ●●● | HM§12; LA 16:48; LD 19:21 |
| VOI-06 | light compression: per-word p90−p10 | 5.5 dB (raw ElevenLabs 8.1); ours 8.4 → 5.1, 7.8 → 4.6 | 4.5–6.3 dB | 24 | ●● | HM§3; 09§1.1; LA 16:48; LD 19:21 |
| VOI-07 | tighten pauses only: `apertar_pausas.py --modo teto --frase 0.10 --virgula 0.05 --teto 0.18 --inicio 0.05 --cauda 0.12` | desert 69.07 → 64.26 s, 27 cuts | never time-stretch / pitch | 2 | USER / LOG | D4; `rc_teste/audio_deserto/voz/aperto.log` |
| VOI-08 | timings: faster-whisper small.en (GPU) aligned to the script + acoustic onsets (onsets10) + acoustic ends (−20 dB) | all script words matched | check `*_casamento.json` | 2 | LOG | LA 16:48; LD 19:21 |
| VOI-09 | ElevenLabs UI: Explore → full name → Use; Radix sliders by aria-label, step 0.01; Output Format → MP3 44.1 kHz 192 kbps (default 128); no speed slider (`sp101`); 1 click = 2 generations; History tab re-downloads | — | — | — | USER / LOG | D4; BR l.77–80; MEM-EL |
| VOI-10 | channel narrator: one voice, F0 ~195 Hz, range 16.5 st, acted character lines by the same voice +8…+13 st without pitch shift | (not measured on Alex) | F0 169–210 Hz | 24 / 5 lines | ●● / ● | HM§3; 09§1.1–1.2 |

## SND — sound (L5 no music · L6 levels)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| SND-01 | channel music loop (−14 LU, ~8 s, no ducking) — **overridden: no music** | none | — | 22–24 | ●● (channel) / USER | HM§3; 09§1.4–1.5; D5 |
| SND-02 | SFX sparse and LITERAL (shot, crash, thud, ping, door, gulp…) | ours ~11–14/min (`POR_MIN = 14`; 15 events in 64–66 s) | channel 5–15/min (10.8 [2.9–46.6] incl. residue) | 24 / 2 | ●● / USER | HM§3; 09§1.6; D6; `audio_deserto.py` l.416 |
| SND-03 | no whoosh, except a real flying object (arrow, plane with doppler) | 0 whoosh | 1 max (the object) | 24 / 2 | ●● / USER | HM§3; D6; LA 14:52; LD 17:33 |
| SND-04 | SFX level under the voice | ~14 LU (desert −14.2; Achilles SFX −27.3 LUFS vs voice −14.0) | every SFX below the speech in 300–3400 Hz over a word (Achilles 8–22 dB; desert worst −4.6 dB in its window, −12 dB vs typical speech) | 2 | USER / LOG | D6; LA 16:09, 16:48; LD 19:21 |
| SND-05 | SFX on the EXACT frame of the action (from `cast.ts` `SFX_EVENTS`), pan 0.35·x | attack on the frame (+3 ms checked) | — | 2 | LOG | LA 16:04; LD 17:33 |
| SND-06 | no ambience bed, no continuous footsteps | 0 | — | 24 | ●● | 09§1.6, 09§5 |
| SND-07 | short tails, smooth engine/loop envelopes (so the onset ruler counts 1 per event) | tails ≤ ~0.23 s | 15 onsets = 15 events | 1 | LOG | LD 18:17 |
| SND-08 | SFX-only mix before the voice (QA gate "level without voice") | −27.9 LUFS (voice −14 minus ~14 LU) | ± 2 LU | 2 | LOG | QA-A; LA 16:04–16:20 |
| SND-09 | end: dry cut at acoustic end of the last word + 3 f; no fade; last SFX may be cut | +3 f | ≤ 5 f | 24 | ●●● | HM§3, §12; 09§5 |
| SND-10 | measure every stem: BS.1770 on original channels (`s09_comum.py`) + ffmpeg ebur128 | voice −14.0 · SFX ≈ −28 · final −14.0 | — | 2 | USER / LOG | D6; LA 16:48; LD 19:21 |

## OUT — master and export
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| OUT-01 | 1080×1920 @ 30.000 fps, H.264 (ours CRF 16, yuv420p, bt709) | 24/24 | — | 24 | ●●● | HM§10; 00§1d; GPU§4 |
| OUT-02 | frames: `TOTAL = round(30·acoustic end of last word) + 3` | 1800–1950 | **≤ 1980** (abs. 1170–1980) | 24 | ●● | HM§10, §12; `clock.ts` |
| OUT-03 | loudness: integrated · true peak · LRA | −14.0 LUFS · −2.2 dBTP · 2.2 LU (ours −14.0 · −2.15 · 1.6–2.0) | −15.6…−14.0 (±0.5) · ≤ −2.0 dBTP · 1.7–3.1 | 24 | ●●● | HM§10; 09§1.3; LA 16:48; LD 19:21 |
| OUT-04 | near-mono: Side vs Mid; L/R correlation | −28 dB; 0.997 (ours −26.8 with music; −35.5 without) | −31.9…−23.8 dB | 24 | ●●● | HM§10; LA 16:48; `audio_deserto/voz/troca_voz.json` |
| OUT-05 | no loop to the start | ratio 1.01 | 0.56–1.39 | 24 | ●● | HM§10 |
| OUT-06 | `_leve` copy: 720×1280, CRF 23, same audio | 16.7–24.7 MB | ≤ 30 MB | 4 | USER / LOG | D11; PT-A l.7 |
| OUT-07 | audio mux AAC 256k 48 kHz (`-map 0:v:0 -map 1:a:0`; Remotion writes a mute track) | — | — | — | LOG | GPU§4; RC§4 |

## CAM — camera (L8)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| CAM-01 | lens 70° (vertical fov; 82° only inside a car) | 70° (channel est. ~83°, IQR 71–92) | QA estimate ≥ 65° | 62 frames | ● (new ruler) / USER | AC§1.3, §3.1; D8; LD 17:56 |
| CAM-02 | distance for head size: `d = 0.479 / (h·1.40)` | MS 2.0 m · FS 2.95 m · WS 5.6 m · CU 1.3 m | — | — | ● / USER | AC§3.1; D8 |
| CAM-03 | every shot travels | channel 2–5 s shot: scale change 88 %, travel 0.52 frame widths | each shot ≥ 0.27 zoom range OR ≥ 0.21 widths; ≤ 1 drift-only shot | 130 shots | ●●● | AC§0, §3.3 |
| CAM-04 | arrive moving: first key at `a − 12` (12 f before the crossfade centre) | channel 64 % of changes ≥ 2 px/f after | ≥ 3/4 of changes ≥ 2 px/f in the 6 f after (ours 17/17, 14/15) | 246 | ●●● / USER | AC§1.1, §3.3; D8; QA-A; QA-D |
| CAM-05 | camera always alive | ≥ 2 px/f in 70 % of frames; still 0.9 % | 51–92 %; < 0.3 px/f ≤ 10 %; longest still ≤ 23 f (6 [0–23]) | 24 | ●●● | HM§4; 01§1.1 |
| CAM-06 | glide: symmetric smootherstep, `dur` 25 | window 21 f; peak 28 px/f (p25 14, p75 51, p90 83); ~3 per 10 s; 58 % dolly/zoom | 9–47 f; dur 12–55; 1.12–4.89 per 10 s (QA) | 371 glides | ●●● | HM§4; 01§1.2; RC§2.1 |
| CAM-07 | calm = slow push | +0.12 %/f; 66 % push, 20 % no zoom (drift 0.3–2 px/f), 14 % pull | +0.03…+0.50 %/f; calms with active zoom 65–95 % (81 %) | 19 456 f | ●●● | HM§4; 01§1.3; AC§1.1 |
| CAM-08 | emphasis push / pull-out | push 35 f, 0.37 %/f, +21 %; pull-out 25 f, −19 %, ~1 per 2 pushes | push 23–58 f, 0.19–0.80 %/f | 429 | ●● | HM§4; 01§1.3 |
| CAM-09 | movement types (pairs in motion) | channel: dolly-in 38 · arc/lateral 18 · dolly-out 15 · crane 13 %; ours dolly-out 10.7–13 %, crane 7.6–16.7 % | **dolly-out ≥ 8 %, crane ≥ 4 %** | 24 | ●● / USER | AC§1.2, §3.3; D8; LA 15:31; QA-A; QA-D3 |
| CAM-10 | parallax e90 in moving frames | **≥ 3.5** (user; channel 3.53); ours 6.32 (Achilles), 3.30 (desert v3) | QA hard floor 1.2 (p5) | 24 | ●● / USER | AC§1.2, §3.3; D8; QA-A; QA-D3 |
| CAM-11 | frozen 1-s windows | 7.5 % (channel 7.5 [3.1–22.1]) | ≤ 10 % (desert v3 10.3 % failed) | 24 | ●●● / USER | AC§1.5, §3.3; D8; QA-D |
| CAM-12 | head ≥ 0.15 of frame height (all frames, detector) | ~10 % (channel 9.2 %) | ≤ 24 % | 24 | ●● | AC§1.3, §3.3 |
| CAM-13 | close-ups | 2.4 % of time; ≤ 1 CU per video, ≤ 1 s | ≤ 3 % | 661 f | ●● / USER | HM§4; AC§3.1, §3.3; D8 |
| CAM-14 | near characters never seen > 30° from above; cards tilt to a high lens (elevation − 10°, max 50°) | 0 frames > 30° | — | 2 | USER / LOG | D7, D8; LA 15:28–15:30; LD 18:24 |
| CAM-15 | angle | eye level 88 % · high 7 · low 2 · zenith 2 | — | 661 f | ●● | HM§4; 07§1.5 |
| CAM-16 | framing: head top CU 0.23 · MS 0.38 · FS 0.42 · WS 0.50; head centred | x 0.50 (64 % within ±0.1) | — | 661 f | ●● | HM§4; 07§1.5 |
| CAM-17 | foreground cut by the frame edge, 0.3–0.5× focus distance, stays until the end of its shot | 8 % of frames (MS 14 %) | 8–15 % (per video 0–15.6) | 661 f | ●● / LOG | HM§4; 07§1.4; LA 16:25 |
| CAM-18 | roll wiggles; fixed dutch only when motivated | 1.4° in 9 f, 3.6 per 10 s; dutch ~3–8 % of time | p90 6.3°; rolls 1.3–7.7 per 10 s | 24 | ●● / ● | HM§4, §12; 01§1.5 |
| CAM-19 | impact shake | ≤ 1 per video, 4–6 f alternating, 1–8 px | ≤ 1 | 19 in 11 videos | ●● | HM§4; 01§1.5 |
| CAM-20 | no handheld float | 0.07 px | 0.04–0.18 | 24 | ●●● | HM§4; 01§1.1 |
| CAM-21 | camera starts NOT tied to words (compose by framing) | 22.6 % within ±6 f × null 22.3 % | — | 570 | ●●● | HM§4; 10§1.2 |
| CAM-22 | life between beats: scene change with calm camera · e90 calm · visual events | 2.1 % · 0.5 · 1.25/s; 2–3 secondary elements per shot; head turn every ~1–2 s; weight sway 1–2 % | ≥ 1.5 % · ≥ 0.3 · ≥ 1.0/s | 24 | ●● / USER | AC§1.5, §3.1, §3.3; D8 |
| CAM-23 | no lateral slide along repeating textures (blocks moving ~half a period per frame read as shake) | approach frontally, slower | — | 1 | USER / LOG | D8; LA 16:03 |
| CAM-24 | hero in frame through key actions | — | — | 1 | USER / LOG | D8; LA 15:05 |
| CAM-25 | arcs with a polar `orbit()` key (a straight `mix()` is a chord) | — | — | — | LOG | AC§3.1; QT v4 |
| CAM-26 | one long take | 10.2 s (ours 8.5 s, 12.3 s) | 7–14 s (7.3–13.6) | 24 | ●●● / USER | HM§4; 10§1.1; D8; QA-A; QA-D |

## EDT — editing, transitions, timing
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| EDT-01 | crossfade at EVERY shot change, linear α | 7 f; ~10 per Short (9.5) | 5–10 f; 4.2–18.9 per video | 14 by eye / 246 | ●●● | HM§7, §12; 01§1.4 |
| EDT-02 | shot changes | 13 per video = 2.3 per 10 s; median shot 3.0 s | 7–20; 1.6–3.3 per 10 s | 24 | ●●● | HM§4; 10§1.1 |
| EDT-03 | hard cuts | 0–1 per video (11 in 24) | ≤ 1 | 24 | ●●● | HM§4, §12; 01§1.4 |
| EDT-04 | white transition flash | 0 | 0; a motivated flash ≤ 1 | 24 | ●●● | HM§7; 01§1.4; 11§1.3 |
| EDT-05 | trick transitions (through window/hatch/pupil/screen 19 · whip 9 · smoke/object 9 · iris 5 · follow object 4 · photo 4) | 1–3 (median 2) | measured 0–6 | 24 | ●● | HM§7; 01§1.4 |
| EDT-06 | change starts +1 f after the acoustic onset of the post-pause word: `a = round(30·t) + 4` (a = centre) | +1 f (middle +4) | IQR −3…+3 | 226 | ●●● | HM§9; 10§1.2; RC§2.1; AU§4 |
| EDT-07 | light change centred on the time word ("night", "morning", "sunset") | 0 f | p25–p75 −5…+6 | 24 | ●● | HM§9; 02§1.6 |
| EDT-08 | last shot | ~3.3 s, enters by crossfade (21/24), often inside the last sentence (11/24) | 0.6–13.3 s (min–max) | 24 | ●● | HM§9; 10§1.5 |
| EDT-09 | hook: first visual event · first shot change | frame 10 · 3.4 s (≈ end of sentence 1) | 1–40 f · 0.6–8.3 s | 24 | ●● | HM§9; 10§1.1 |
| EDT-10 | actions ≥ a+3 f and ≤ b−4 f of their own shot (`ACTION_SHOT`; check with `ancoras_<name>.mjs`) | 0 anchors < 3 f | 0 | 2 | USER / LOG | D8; BD; LA 16:45–16:48; QA-D |

## SYN — sync
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| SYN-01 | reaction (expression/pose/effect that illustrates a word) on the acoustic onset frame; `LEAD = 0` | 0.0 f | p05 −2.3 … p95 +1.7 | 19 | ●● | HM§9; 10§1.3 |
| SYN-02 | continuous action not locked to words | 45.8 % × null 44 % | — | 480 | ●● | HM§9; 10§1.2 |
| SYN-03 | visual density · longest gap without event | 1.25 events/s · 3.9 s | 0.83–1.43 · 2.6–8.3 s | 24 | ●● | HM§9; 10§1.1 |

## SHT — shot mix
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| SHT-01 | share of time per shot size | MS 32 · WS 21 · INS 20 · FS 17 · EWS 6 · CU 2.4 % | — | 661 f | ●● | HM§4; 07§1.5 |
| SHT-02 | cast per frame | 0: 26 % · 1: 42 % · 2: 18 % · 3–5: 9 % · crowd 4 % | — | 661 f | ●● | HM§4; 07§1.5 |
| SHT-03 | 2D inserts: set names `insert_*`, each with its own push + drift + parallax | — | — | 1 | LOG | LD 17:22, 18:22–18:24; `qa_aquiles.py:663` |

## COL — colour and grade (values on the FINAL frame, captions and ink excluded; QA tolerance on dark zone ±6)
| code | state (share of channel time) | Y′601 p50 | p5 outside ink | p99 | lit C* p50/p90 | dark zone a*/b* | Y′ < 0.05 | n | strength | source |
|---|---|---|---|---|---|---|---|---|---|---|
| COL-01 | day (28 %) | 0.57 [0.42–0.71] | 0.23 [0.15–0.38] | 0.97 [0.95–0.99] | 35 / 56 | +11 / 0 (#482f3c) | ≤ 0.2 % | 374 f / 17 v | ●●● | HM§5a; 02§5 |
| COL-02 | golden (8 %) | 0.54 [0.36–0.74] | 0.22 [0.16–0.40] | 0.93 [0.81–0.99] | 33 / 50 | +18 / 0 (#502f44) | ≈ 0 | 106 f / 11 v | ●● | HM§5a; 02§5 |
| COL-03 | night + blue interior (21 %) | 0.27 [0.18–0.36] | 0.10 [0.07–0.18] | 0.85 [0.71–0.97] | 36 / 62 | +17 / −28 (#30295d) | ≤ 2 % | 272 f / 15 v | ●● | HM§5a; 02§5 |
| COL-04 | interior (33 %) | 0.48 [0.22–0.74] | 0.15 [0.06–0.25] | 0.95 [0.89–0.99] | 29 / 52 | +11 / +1 (#44272d) | ≤ 1 % | 439 f / 21 v | ●● | HM§5a; 02§5 |

| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| COL-05 | black never neutral: day/golden warm lifted (39,27,33); night navy (9,5,32) | — | — | 24 | ●●● | HM§5a; 02§1.1 |
| COL-06 | sky day top → horizon | #689cce → #a4c3e6, luma ratio 1.28 | 0.97–1.71 | 246 f / 17 v | ●● | HM§5a; 02§1.4 |
| COL-07 | sky golden · night | #c39199 → #fcbc97 (1.21) · #565bb5 → #636ccc (1.16) | — | 67 f · 31 f | ●● · ● | HM§5a; 02§1.4 |
| COL-08 | lit palette day / night / golden | day orange-wood #efad65 33 %, sky blue #6fb7fc 27 %, red #e25748 11 %; night blue #4b5dce 53 %, lamp orange #f6b87c 7 %; golden peach #fdc38a 43 % | — | 24 | ●● | HM§5a; 02§1.3 |
| COL-09 | vignette `×(1 − k·smoothstep(r0,1,r))` | day 0.06/0.5 · golden 0.08/0.45 · night 0.12/0.45 | — | 24 | ●● | HM§5a; 02§1.5 |
| COL-10 | no grain | 0 (codec floor 0.15–0.18) | QA ≤ 0.2 | 24 | ●●● | HM§5a; 02§1.5 |
| COL-11 | time-of-day drift | golden+night 13 % of the 1st quarter → 39–40 % of the 3rd/4th; day 44 % → 17–20 % | — | 24 | ●● | HM§5a; 02§1.6 |
| COL-12 | saturated props keep their hue in shade (red car: chroma −30 %, no violet tint); car red = channel red #e25748 (cherry #c8323a fell into the dark zone even in sun) | — | dark-zone gate ±6 | 1 | USER / LOG | D7; LD 18:49, 18:59; QA-D v3 |
| COL-13 | darks desaturated per light in `grade.ts`; neutral shadow ink | — | — | 1 | LOG | LA 15:51 |

## LGT — light and shadow
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| LGT-01 | shadow = a COOL colour swap also by day: shadow/light ratio (linear, same surface) | R 0.20 · G 0.31 · B 1.21 · Y 0.31; hue 283–311° (ours: B 0.6 passed the dark-zone gate) | B 0.87–2.06 · Y 0.14–0.39 | 6 pairs / 3 videos | ● / LOG | HM§5b; 04§1.3; AU§2; LA 15:51; QT l.36 |
| LGT-02 | sun per shot: day back-side light; golden sun in frame | day az 20–60°, el 20–35° (6/10); golden az 0–10°, el 3–8° (4/5) | ±30° by eye | 10 + 5 shots | ● | HM§5b; 04§1.5 |
| LGT-03 | character card never darkens, only tints: face V; tint per light; no rim | V 0.973; day [1,0.95,0.90] · golden [1,0.79,0.68] · lamp [1,0.74,0.55] · night [1,0.71,0.88] | V 0.844–1.000; rim 0/18 | 402 heads | ●●● | HM§6; 04§1.7; RC§2.2 |
| LGT-04 | face side gradient (light/dark halves) | 0.3 % (reference, 36 frames); ours 0.3 % (`GRAD_K` 1.0) | 0.1–0.9 %; brief ≤ ~0.5 % | 36 f | ●● / LOG | QT l.32–34; QA-A; LA 15:51 |
| LGT-05 | cards cast cool soft shadows also by day | Y 0.15–0.39, 1–2.7 head widths | — | small | ● | HM§5b; 04§1.6 |
| LGT-06 | bloom only on emissives above 1.0 (lamps r50 18–36 px, moon ~60 px at 1080) | — | — | small | ● | HM§5b; 04§1.8; RC§2.13 |
| LGT-07 | light follows the story: families · changes · first change | 3 · 4 · ~8 s (20/24 change) | 1–4 · 0–11 | 19 | ●● | HM§5b; 04§1.9 |
| LGT-08 | never animate the sun within a shot — except a deliberate time-lapse light (`lapseDusk`/`lapseDawn` on the global clock) | — | — | 1 | ● / LOG | RC§2.4; LD 17:13 |

## INK — outlines
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| INK-01 | world ink width at 1080 (QA on straight lines) | EW 2.38 px (ours 2.26–2.32) | channel 0.97–4.78; QA median 2.0–2.8, p95 ≤ 5 | 7 274 lines | ●●● | HM§5c; 03§1.1; RC§3a; QA-A; QA-D3 |
| INK-02 | width with distance | near (1–1.5 m) 3.2 · mid (3–4 m) 2.5 · far (~8 m) 1.7 px | — | 4 frames | ● | HM§5c; 03§1.2 |
| INK-03 | line only on MANUFACTURED objects; NOINK on terrain, foliage, cloud, water, sky; no line at contacts/curbs/junctions | 65 % of geometry edges have a line | junctions 0/5 | 40 edges | ●● | HM§5c; 03§1.3; 03§5 |
| INK-04 | colour near-black not neutral, pulled 35–40 % toward the scene | #1c1218 (recipe #140d13) | — | 96 lines / 18 f | ● | HM§5c; 03§1.4; RC§2.10 |
| INK-05 | ink in its own pass BEFORE the DOF; crisp | 10–90 rise 1.25 px | — | 7 274 | ●●● | HM§5c; 03§1.1; RC§4 |
| INK-06 | no boil | 0.13 px RMS | — | 8 f | ●● | HM§5c; 03§1.6 |
| INK-07 | character outline: width · thick/thin (thick side random) · colour | 4.4 % W · 3.5:1 · #2e1d26 (ours 4.66 % · 3.64) | p10–p90 3.4–6.3 % W · QA 2.5–5 | 87 heads | ●● | HM§6; 03§1.5; QA-A |

## TEX — textures and objects
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| TEX-01 | flat colour fields; painted joints only where a real joint is | flat 58 % · flat + joints 24 % · fine detail 19 % · bitmap ~3 %; flat-pixel fraction 0.69 | 0.42–0.84 | 170 samples · 1 320 f | ●● · ●●● | HM§5d; 05§1.2–1.3 |
| TEX-02 | lit wood #c68c49 with gap #522316 visible 3–5 px at 1080 | ΔL* 33 (gap) | ΔL* 25–35; gap 2.2–7.0 px | 16 / 18 | ●● | HM§5d; 05§1.1; RC§2.6 |
| TEX-03 | other screen colours: stone #ccc3b5 · brick #d16143 (dark joint) · grass #6fa03a · water #2576c3 flat · tile #e68a70 | — | — | 2–14 each | ● / ●● | HM§5d; 05§1.1 |
| TEX-04 | no visible tiling on organic ground; no "lemon" wood (h ≥ 80 with C* ≥ 60) | 0 | — | 24 | ●● | HM§5d; 05§1, 05§7 |
| TEX-05 | objects solid: decks/interiors, nothing seen through hulls or bodies | 0 holes | stills review | 1 | USER / LOG | D7; LA 15:17 |

## CHR — characters
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| CHR-01 | head: H/W · crown nTop · jaw nBot · egg · asym | 0.95 · 1.83 · 2.15 · −0.12 · +0.07 | H/W 0.89–0.99 | 19 skulls | ●● | HM§6; 06§1.2 |
| CHR-02 | hat or hair | ≥ 90 % of characters (bald ~5 %) | — | 468 faces | ●● | HM§6; 06§1.2 |
| CHR-03 | body in head heights: head : torso : legs | 3.49 HH = 1 : 1.10 : 1.40; bean torso | 3.36–4.20 | 21 | ●● | HM§6; 06§1.4 |
| CHR-04 | limbs = one ink stroke, no knee; dot hands; short oval feet; every character has arms | 0.058 W | 0.043–0.071 W | 20 | ●● / LOG | HM§6; 06§1.4; QT v2 |
| CHR-05 | face: eyes on the centre line · mouth · no catchlight · blush only as embarrassment | eyes 0.255 W apart; mouth +0.195 W; catchlight 0/~470 | 0.19–0.31 W | 375 | ●●● / ● | HM§6; 06§1.3 |
| CHR-06 | expressions | ≥ 14 | — | 24 | ●● | HM§6; 06§1.3 |
| CHR-07 | animation on 1s; no boil; no squash | 0 repeated frames in 33.7 k pairs | — | 24 | ●●● / ● | HM§6; 06§1.5 |
| CHR-08 | blink: closed frames · total · interval in bursts | 2 f (72 %) · 3 f · 18 f; 43 % of faces ≥ 2 s don't blink; mean 1 per 2.17 s | total 2–4 f; interval 8–59 f | 53 blinks | ●● | HM§6; 06§1.5 |
| CHR-09 | expression change in 1 f, often hidden in a blink | 26 % of blinks (10/38) | — | 38 | ● | HM§6; 06§1.5 |
| CHR-10 | costumes read by gender/role (no long robe on a man; a kneel reads as a kneel) | — | stills review | 2 | USER / LOG | D7; LA 15:34 |
| CHR-11 | no black blob head from behind: 3/4 view or hair + ears + neck skin | — | stills review | 1 | USER / LOG | D7; LD 17:28, 18:43 |
| CHR-12 | no snaps: arm blends ≥ 5 f; lean ramps; view (front/side/back) from a fixed reference lens between keys; holds 6 f + return 6 f | 0 cast impacts | QA impacts ≤ 1 | 2 | LOG | LA 16:25; LD 18:43 |
| CHR-13 | generic people and objects, no real logos or brands | 0 | — | 2 | USER / LOG | BD; LD 17:19 |
| CHR-14 | outline tuning that hit the gate (desert) | `INK_W` 3.1 u, `INK_K` 0.52 (≈ 4.4 % W, ~3.5:1) | — | 1 | LOG | LD 18:43 |

## DOF — depth
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| DOF-01 | DOF visible share of time (+ light blur) | 0.29 with sky / 0.20 without (+14 % light); ours 21 % | 20–30 % | 2 655 f / 661 f / 24 v | ●● | HM§5e; 07§1.1; QA-A; QA-D3 |
| DOF-02 | strength when on: equal in every shot size | σ1080 6.0 (R ≈ 10 px; far decile R ≈ 24) | 4.8–13.1; QA σ p90 10–20 | 24 | ●● | HM§5e; 07§1.1–1.2 |
| DOF-02b | with the 70° lens, `cInf` ~24–30 to reach σ p90 10–20 (cInf 22 gave 8.6 and failed; cInf 30 gave 15.2) | — | — | 2 | LOG | QT l.73, 204, 215; LA 15:31; QA-A |
| DOF-03 | where DOF is on | CU 38 % · INS 34 · MS 26 · FS 23 · WS 16 · EWS/aerial ~0 | — | 24 | ●● | HM§5e; 07§1.2 |
| DOF-04 | focus on the head | sharp in 87 % of DOF frames | — | 121 | ●● | HM§5e; 07§1.3 |
| DOF-05 | aerial perspective: sky-line band pulled toward the horizon colour; fog colour = horizon | k 0.43 (~40 %); day fog #a4c3e6, 25 → 420 m (his value, not measured) | IQR 0.08–0.72 | 110 f | ●● | HM§5e, §12; 07§1.6; RC§2.2 |
| DOF-06 | any post pass that reads depth (heat haze) goes AFTER the lens blur; scale it so it is not read as DOF | haze ×0.55 | — | 1 | LOG | LD 17:56, 18:02 |

## FX — 2D effects
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| FX-01 | effects only where the speech asks for action | ~4.6 per minute (42 in 9.2 min) | 0 (office) … ~14 (cannons) | 10 videos | ● | HM§7; 11§1.4 |
| FX-02 | enter dry in 1 f; leave at the shot change or dissipate | — | — | 10 | ● | HM§7; 11§1.4 |
| FX-03 | durations: muzzle fire 12 f · speed lines 10–12 f (banned here, FX-05) · sparkle star 14 f pulsing · splash flash 6 f + foam ≥ 25 f · explosion fire ~30 f → smoke ≥ 40 f · dust 15–60 f · emotions (steam, sweat, pain, Zzz) 18–80 f cycling | — | — | 10 | ● | HM§7; 11§1.4 |
| FX-04 | no music notes; no thought balloons | 0 | 0 | 10 / 24 | ● | HM§7; 11§1.4; LA 14:55 |
| FX-05 | no speed lines / white stripes for running — only 2 small dust puffs at the feet (0.2 → 0.44 m, gone in 10 f) | 0 stripes | — | 1 | USER / LOG | D7; LA 15:30, 15:34 |
| FX-06 | window/furnace/crack glow = 3D emissive + bloom, not a sprite | — | — | 10 | ● | HM§7; 11§1.4 |
| FX-07 | glints small enough to keep the object readable | star ≤ 1/4 of the object's width | — | 1 | LOG | LD 18:41 |
| FX-08 | heat/air waves: thin (≤ 1/3), translucent, scene-coloured, behind the character (≥ 7 m from lens, ≥ 2.5 m behind him) | — | never crossing a face | 1 | LOG | LD 17:27, 18:22 |

## CAP — captions (`Caption.tsx` + `clock.ts` in the engine already implement these)
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| CAP-01 | font and size | Franklin Gothic Heavy (`FRAHV.TTF`; fallback Libre Franklin 900), 81 px | IoU win 16/30 | 30 cards × 160 variants | ●●● size / ●● font | HM§8; 11§1.1; QT |
| CAP-02 | white fill; black stroke 5.5 px outside + hard shadow (+3, +4) blurred 1.5 px; no box, no glow | — | QA dark run ≥ 5 px | — | ●● | HM§8; 11§1.1 |
| CAP-03 | baseline y = 1377 (71.72 %), centred, one line, never wraps | 1377 (ours 1376.5) | 1376.5–1377; ≥ 90 % of frames in 1376–1378 | 3 707 cards | ●●● | HM§8; 11§1.1; QA-A; QA-D3 |
| CAP-04 | words per card (function words glued to the next; max 3) | 1.32 (ours 1.33–1.36); 63 % 1 word, 33 % 2, 3 % 3 | 1.23–1.38 | 24 / 60 by eye | ●● | HM§8; 11§1.2 |
| CAP-05 | card timing: dry switch, frame 0 to last, enters ~1 f before the acoustic onset | 10 f (ours 11–12 f); 2.81 cards/s | 3–19 f; QA 8–12 | 24 | ●●● / ● | HM§8, §12; 11§1.2 |
| CAP-06 | sentence case, punctuation kept, numbers as digits, no emphasis colour | 0/24 emphasis | — | 24 | ●● | HM§8; 11§1.2 |
| CAP-07 | mounted outside the composer (no ink, DOF or grade), no own crossfade | — | — | — | ●● | RC§2.13 |

## ENG — engine and machine
| code | rule | target | gate | n | strength | source |
|---|---|---|---|---|---|---|
| ENG-01 | versions: Remotion 4.0.290, three 0.175, @react-three/fiber 9.1.2, @react-three/postprocessing 3.0.4, postprocessing 6.37.2 | — | — | — | LOG | BT l.43–44; `rc_teste/package.json` |
| ENG-02 | composer order: ink → lens pre → lens main → bloom → tone NEUTRAL → grade, MSAA 4 | — | — | — | ●● | RC§2.13; CF§3 |
| ENG-03 | fast render: 12 Chromes × concurrency 1 on the RTX 5090 (CPU is the limit; GPU ~1–2 % busy) | 1846 f in 57 s (32.6 f/s) vs 265 s | — | 1 | LOG | GPU§2–4; LA 15:40 |
| ENG-04 | stills: one bundle + one Chrome | ~2 s/still at 0.5 | — | — | LOG | LA 14:42; GPU§4 |
| ENG-05 | Remotion copies `public/` on every bundle → only `*_lowpoly.glb` + licences (1.2 GB of raw moved out) | desert `public/deserto/lib` 0.6 MB | — | 2 | USER / LOG | D9; RC§4; LA 17:14; LD 17:19 |
| ENG-06 | composition ids with hyphens, never "_" | `<Name>-<role>` | — | — | LOG | LA 14:36 |
| ENG-07 | `npx tsc --noEmit` clean before saving to main (Studio 3010 reloads on save) | 0 errors | — | — | LOG | EA (sandbox 4) |
| ENG-08 | GPU 1 = RTX 5090 (the monitor is on it), GPU 0 = RTX 3080; scripts pin the 5090 by LUID; no Windows setting changes | — | — | — | LOG | GPU§1; EA |
| ENG-09 | automatic QA run time | ~3 min | — | — | LOG | LA 15:40 |
| ENG-10 | licences: models and sounds CC0 (or CC-BY with a credit line for what appears); both examples: 0 CC-BY lines | 0 credits spent | — | 2 | USER / LOG | D9; QA-A; QA-D; AE |

## QAF — known false alarms of `scripts/qa_aquiles.py`
| code | the tool says | reality | do | n | strength | source |
|---|---|---|---|---|---|---|
| QAF-01 | CU 12.5–14.6 % | 2D inserts counted as CU (only sets with "insert"/"inserto" are skipped); detector CU 1.3–1.9 % | name sets `insert_*` | 1 | LOG | LD 17:22; QA-D; `qa_aquiles.py:663` |
| QAF-02 | golden p99/darks fail in time-lapses | `lapseDusk`/`lapseDawn` mix golden and night; whole shot scored as DOURADO | report as ruler limit | 1 | LOG | QA-D v1–v3 |
| QAF-03 | SFX/min 24.8 without voice/music | onset ruler re-counts tails still sounding 0.24 s later; propeller pulses up to 4× | trust `cues.md`; short tails, smooth envelopes → 15 onsets = 15 events | 1 | LOG | LD 18:17 |
| QAF-04 | SFX/min 60–73 with voice, no music | speech attacks counted (73.2/min on `aquiles_v2c_sem_musica`) | judge on the SFX stem | 2 | LOG | PT-A l.98–99 |
| QAF-05 | "music continuous: PASS" with no music | voice/SFX fool the chromagram | ignore | 2 | LOG | PT-A l.100; QA-D v2 |
| QAF-06 | outline 2.04 % W, thick/thin 8.40 | the engine's white air filter detected as a head (n = 1–2 heads) | check which heads were measured | 1 | LOG | LD 18:43; QA-D |
| QAF-07 | impacts (≥ 3 f alternating) | RANSAC flips between the cast layer and the background in arcs; no visible shake | re-render the window with `--props='{"post":{"cast":false}}'` | 2 | LOG | LA 16:25; QA-A |
| QAF-08 | crane below 4 % | crane with changing pitch classified as roll | add a pure ~1 s vertical rise | 1 | LOG | QT l.80, 213–214 |
| QAF-09 | DOF 34 % | heat-haze shimmer read as blur | scale the haze | 1 | LOG | LD 18:02 |
| QAF-10 | caption changes 193–196 × 167 planned | 2D inserts change text in the caption band | compare with `clock.ts` cards | 1 | LOG | QA-D v1; QA-D3 l.51 |
| QAF-11 | camera numbers unchanged after a fix | camera `.npz` reused for the same mp4 name (fixed 16:30: recompute + `carimbo.json` + lock) | new mp4 name per render anyway | 1 | LOG | LA 16:10, 16:30 |
| QAF-12 | crash `UFuncOutputCastingError` | all-integer camera vector, `qa_aquiles.py:665–666` lacks `dtype=float` | QA patches; or no all-integer vectors | 1 | LOG | LD 17:22, 18:02 |
| QAF-13 | lens estimate 89° (est/real 1.27) | vanishing-point ruler on n = 1 frame | use gate 8b (`story.ts` fov) | 1 | LOG | QA-D3 l.129–130; AC§5 |

## What our two finished videos measured (benchmarks)
| item | Achilles | desert |
|---|---|---|
| script | 227 words, 16 sentences (CHK at 3.42: REVER, 66.37 s) | 223 words, 15 sentences (CHK: PASSA, 65.20 s) |
| real voice | take1, 71.16 → 66.42 s; **TOTAL 1991 f** (11 over the 1980 gate) | take1, 69.07 → 64.26 s; **TOTAL 1926 f** |
| master | −14.0 LUFS · TP −2.15 · LRA 2.0 · Side−Mid −26.8 dB (with music, before its removal) | −14.0 LUFS · TP −2.15 · LRA 1.6 · Side−Mid −35.5 dB |
| SFX | 15 (14/min budget), only whoosh = the arrow | 15 of 34 events, only whoosh = the plane |
| shots | 18 shots / 17 crossfades, long take 8.5 s (arrow) | 16 shots / 15 crossfades, long take 12.3 s ("shade") |
| QA (placeholder clock) | v1: 72 PASS · 2 FAIL (impacts, glides/10 s 5.04) | v1 63·18 → v2 68·14 → v3 69·13 |
| camera 3D / render | grua 16.7 %, dolly-out 12.1 %, parallax 6.32, frozen 0.1 %, arrive moving 17/17 | grua 7.6 %, dolly-out 12.9 %, parallax 3.30, frozen 10.3 %, arrive moving 14/15 |
| deliverables | `out/aquiles_v2c_sem_musica.mp4` (123 MB) + `_leve` (18.7 MB) | `out/deserto_final_voz.mp4` (115 MB) + `_leve` (16.7 MB) |
Sources: CHK; LA 16:48; LD 19:21; QA-A; QA-D; QA-D3; `audio_deserto/voz/troca_voz.json`; file sizes in `rc_teste/out/`.
