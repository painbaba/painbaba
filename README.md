## Hi, I'm Pratham

I build **AI agent infrastructure** — agent runtimes, browser-driving agents, provider routing and MCP tooling. I also ship full-stack product. India-based, working in public.

### Open source

Patches to **[steel-dev/steel-browser](https://github.com/steel-dev/steel-browser)** — the open-source browser API for AI agents (7.5k★):

**[#353](https://github.com/steel-dev/steel-browser/pull/353) — session timeout with automatic release.** The SDKs exposed a `timeout` on session creation; the self-hosted server accepted it, always reported `timeout: 0`, and kept the session live until released by hand. Implemented server-side release, guarded the timer so a stale one can't release a session that already got replaced, and fixed a spread-order bug in `resetSessionInfo` that was silently discarding caller-supplied values. 5 unit tests.

**[#354](https://github.com/steel-dev/steel-browser/pull/354) — DevTools inspector under `USE_SSL`.** `.replace("ws:", "")` no-ops on `wss:`, so the frontend was handed a malformed URL and CSP-blocked. Stripping the scheme alone isn't enough: the DevTools frontend derives its protocol from *which* query parameter carries the value, so a secure endpoint sent as `ws` opens an insecure socket and gets blocked as mixed content. Switched the parameter too, leaving non-SSL output byte-identical. 6 unit tests.

**[#355](https://github.com/steel-dev/steel-browser/pull/355) — session viewer rendered the wrong session.** No Router was ever mounted, so `useParams()` returned undefined and every viewer URL fell back to `sessions[0]`. The header meanwhile hand-parsed `window.location`, so the header named one session while the body rendered another. Measured before and after in a real browser: 3 of 5 API calls hit the list endpoint before, 0 of 1 after.

### Agents & infrastructure

**[XOMNI](https://github.com/painbaba/xomni)** — one agent, every feature, every free model. Unifies 6 open-source coding agents on a single host: 12 plugins, a provider pool routing 25 verified free models, 329 passing tests.

**[unified-agent](https://github.com/painbaba/unified-agent)** — Hermes host + 13 modules: context compaction, sandbox gating, MCP catalog, repo mapping, GitHub ops, local model serving, verification runner.

**[StrawManus](https://github.com/painbaba/strawmanus)** — a browser-control agent fusing Manus's flat 12-tool action layer with a session, natural-language selector and skill-reuse layer. Runs in your real logged-in browser, self-heals when sites change, replays successful tasks as skills. Ships an MCP server.

**[BX Browser](https://github.com/painbaba/bx-browser)** — DOM-first, vision-capable browser agent. Reads the accessibility tree for 2–4s steps and falls back to vision only when the page demands it. Session keep-alive, model-ladder fallback, zero-dependency core.

**[OpenBerry](https://github.com/painbaba/openberry)** — a local agentic browser for Windows. An agent drives your real Chrome/Edge across tabs over CDP, logged in as you. 100% local, MIT.

**[hermes-skills](https://github.com/painbaba/hermes-skills)** — custom skills for Hermes Agent: delegation recovery, session artifact recovery, CLI APK builds, constrained-budget scraping.

### Applied agents

**[VIGIL](https://github.com/painbaba/vigil)** — autonomous trading-ops agent. Scans markets around the clock, rule-checks, signals, monitors, journals. Google "All Things Agentic".

**[PantryWatch](https://github.com/painbaba/pantrywatch)** — stops food-bank donations expiring. AWS Strands Agents SDK.

**[Hackathon Radar](https://github.com/painbaba/hackathon-radar)** — Devpost scanners, prize and deadline tracking, and win-pattern analysis. Most hackathon losses are selection losses, not build losses.

**[StackPilot](https://github.com/painbaba/stackpilot)** — Android offer console for Indian delivery riders. Allowlisted read-only notification capture, deterministic on-device scoring and trip-chain routing. Kotlin, R8, signed releases.

### Products & builds

| | |
|---|---|
| [Railway Calm](https://railway-calm.vercel.app) | IRCTC, rebuilt around the 90 seconds of tatkal pressure |
| [Life Event OS](https://umang-life-event-os.vercel.app) | UMANG as guided life-event journeys across central + state services |
| [GST Flow](https://gst-flow-steel.vercel.app) | A GST month on one screen for small traders |
| [Move India](https://move-india.vercel.app) | parivahan.gov.in as one plain-language conversation |
| [CyberSafe First 30](https://cybersafe-first-30.vercel.app) | Emergency companion for cyber-fraud victims |
| [PF Life Admin](https://pf-life-admin.vercel.app) | EPFO as a continuous employment timeline |
| [Passport Ready](https://passport-ready-three.vercel.app) | Reach the PSK right the first time |
| [KiranaLedger](https://github.com/painbaba/kiranaledger) | Voice-first Hinglish khata for kirana shops |
| [GridSense](https://github.com/painbaba/gridsense) | Digital-twin smart-grid monitor with real-time anomaly detection |
| [JalSetu](https://github.com/painbaba/jalsetu) | Tells a housing society exactly when its water runs out |
| [CutDirector](https://github.com/painbaba/cutdirector) | One line of English to a playable film, fully offline |
| [PadhaiSetu](https://github.com/painbaba/padhaisetu) | Adaptive vernacular tutor for MP Board |

### Stack

`Python` `TypeScript` `Next.js` `React` `Kotlin` `Node`

Agent runtimes · MCP servers · Chrome DevTools Protocol · Playwright · multi-provider LLM routing · Cloudflare Workers · AWS Strands · Vercel

📫 painpratham@gmail.com
