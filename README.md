# Request Builder (Claude API optimization)

A form that turns a request for any of fenw1ck's projects into a clear, structured brief for Claude. Clear briefs mean fewer clarifying questions, less re-reading and smaller jobs, so each request uses less API.

**Live site:** https://fenw1ck.github.io/Claude-API-Optimization/ (once Pages is on: Settings → Pages → Deploy from a branch → `main`, `/ (root)`).

## How it works

1. **Fill in the order.**
   - Required: the project or projects (tick every one the work touches), the kind of request (something broken, a feature, new content, research, a question) and a one-sentence summary.
   - Each kind then asks for its own details: steps to reproduce, "done when", the source to follow, how deep to research.
2. **Fix what the ticket flags.** The ticket checks itself as you type:
   - required fields;
   - a summary that is too short or too long, or looks like two requests;
   - vague words like "fix it" or "make it better";
   - bug steps written on one line;
   - a missing finish line.
3. **Copy the ticket, or open it as a GitHub issue** in that project's repo (pre-filled).

**Size check, reused answers, files, and getting the work back** (25 Nov 2026).
- **The form sizes the job, not you** (25 Nov 2026, replaces the old Size check): step 5 is now **Extras** and has no job-size choice. The form counts the "Done when" lines of every ticket in the bundle together, plus extra projects, bundle parts, art and a long description (`sizeOf`), and writes Quick, Normal or Thorough into the ticket's Effort line with the reasons. People tend to underestimate; the count doesn't.
- **From the Art Assets Game engine tab** (25 Nov 2026): **Edit this part** opens the form with `?engine=<part>&name&what&params&from`. The form ticks the Euclid game and Art Assets, picks **Change or add a feature**, writes "Improve the game engine: <part>" and the part's current rules and settings into *What should happen*, picks the area *Game engine (engine.js, engine.html)* and links back. The art card stays hidden for these (`A.engine`), because Art Assets is ticked for engine.js, not for art. projects.json gained engine areas for both projects.
- **From the Art Assets library** (25 Nov 2026): its **Edit this art** opens this form with `?improve=<id>&title=<name>&from=<library link>#img=<PNG data URL>`; the form fills an Improve ticket, puts the library link in Links and attaches the picture under Screenshots and files.
  - Since the library was organised (25 Nov 2026), Edit also sends `entry` (the card's own research entry, which the art card then uses even when the name doesn't match), `parent` (the nearest entry, preselected as "File it under" when the piece has none), `branch`, `tags` and `drawn`. The art card shows them under **From the library card**, and the Art brief adds *Where it lives*, *Tags* and *Drawn now by* lines.
- **Reused answers:** copying or opening a ticket saves each project's job size, area, things to leave alone and expert sources (in the browser); ticking the project later fills the empty ones and says which. Every ticket also tells Claude that the project's notes are its memory and to record lasting decisions there.
- **Something is broken** has a **Where exactly** field. Step 5 has a drag-and-drop area for screenshots and documents (listed on the ticket; drag them into the GitHub issue or paste them into the chat; images have a Copy button). Links are checked as web addresses, and a bad one holds the ticket.
- Step 6, **How do you want the work back?** (pull request, straight to main, files to download, a published page, or the reply; formats; where it goes) is written into every ticket and remembered for every project unless unticked. The **Getting the work back** tab (`#guide`) explains each way, the one-time setup (connecting GitHub, turning on Pages) and common mistakes.

**Art that needs no Claude, and art carried over** (25 Nov 2026). In the art card, **Claude can leave the art alone** turns the Art brief into one line saying the art is covered; when the ticket asked for nothing but that art, the meter says **No ticket needed**. The Art brief now names the research file and the program that draws it. The art on a copied or opened ticket is remembered in the browser; on the next ticket, **Keep the art from the last ticket on this one** adds it (name, research file, drawing program, where it is seen) under *Art from the last ticket*. The **Improve this art** button on a card in the Art Assets library ([builder-archive.html](https://fenw1ck.github.io/Art-Assets/builder-archive.html), Research library tab) opens this form with an "Improve the … art" ticket already started (`?improve=<id>&title=<title>`).

**Bundles: one task, several tickets** (25 Nov 2026). Under the main request, **This project needs art** adds a *New art* card (what it is, where it will be seen, look notes, states, done when; it checks the research library as you type) and becomes **Add more art**; **And another thing** adds any other kind of request (kind, one sentence, details, done when). Each card is its own ticket that shares everything else on the form: projects, area, job size, sources, things to leave alone, notes to read. The copy box then holds the whole bundle: the shared context once, then *Ticket 1 of n*, *Ticket 2 of n*… with an instruction to do them in order, one at a time. **Open as GitHub issue** opens the bundle as one issue; under the ticket, each part also has its own issue link (art parts open in Art Assets), with a line naming the other tickets in the bundle. Parts are saved in the draft; with no parts the ticket is exactly as before.

**What's already open** (25 Nov 2026). Ticking a project lists its open pull requests and issues under the project chips (Art Assets too when art is involved), straight from GitHub's public API: one check per repo per visit, within GitHub's 60-an-hour limit for pages that aren't signed in. Open pull requests also go into the ticket's **Before you start**, telling Claude to branch from one if the work builds on it, and the ticket flags them so you can merge first.

Every ticket ends with **Before you start**. It names the project notes Claude should read first, says to ask at most one question, and limits the change to the job size the form worked out (quick / normal / thorough).

**Art is always saved in Art Assets.** Choosing "art" as the kind of content ticks Art Assets automatically, and the ticket tells Claude to build the art there and copy it into the other projects. With several projects ticked, the GitHub issue opens in Art Assets when art is involved, and otherwise in the first project ticked.

**Art requests are made here too** (25 Nov 2026). The Art Asset Builder was merged in and retired: whenever art is involved, a card asks its questions (where the art will be seen, look notes, states, repeating structure, variation). It looks the subject up in the Art Assets research library (by name, "Which one" or the summary), lets you choose to use the research as it is, fill its gaps or search deeper, and shows a live preview when the engine can already draw it, which may need no Claude at all. The answers go into the ticket as an **Art brief**. The library and the drawing programs (`core.js`, `plants.js`, `containers.js`, `research/index.json`) load from the Art Assets site, so they are always current. The old form is kept at https://fenw1ck.github.io/Art-Assets/builder-archive.html.

**Sources to treat as expert** (optional, every request) lists the books, sites or files Claude should trust over a web search; they go into the ticket under their own heading.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | the whole page (no build step) |
| `projects.json` | the projects the form knows (Euclid game, Planting Guide, Art Assets, Free Data Library, Muscle Anatomy Trainer, Claude API Optimization, and "New project"): repo, site, docs to read first, areas, kinds of content. Edit it to add a project. |

Drafts are kept in your browser only.
