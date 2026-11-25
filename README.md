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

Every ticket ends with **Before you start**. It names the project notes Claude should read first, says to ask at most one question, and limits the change to the job size you chose (quick / normal / thorough).

**Art is always saved in Art Assets.** Choosing "art" as the kind of content ticks Art Assets automatically, and the ticket tells Claude to build the art there and copy it into the other projects. With several projects ticked, the GitHub issue opens in Art Assets when art is involved, and otherwise in the first project ticked.

**Art requests are made here too** (25 Nov 2026). The Art Asset Builder was merged in and retired: whenever art is involved, a card asks its questions (where the art will be seen, look notes, states, repeating structure, variation). It looks the subject up in the Art Assets research library (by name, "Which one" or the summary), lets you choose to use the research as it is, fill its gaps or search deeper, and shows a live preview when the engine can already draw it, which may need no Claude at all. The answers go into the ticket as an **Art brief**. The library and the drawing programs (`core.js`, `plants.js`, `containers.js`, `research/index.json`) load from the Art Assets site, so they are always current. The old form is kept at https://fenw1ck.github.io/Art-Assets/builder-archive.html.

**Sources to treat as expert** (optional, every request) lists the books, sites or files Claude should trust over a web search; they go into the ticket under their own heading.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | the whole page (no build step) |
| `projects.json` | the projects the form knows (Euclid game, Planting Guide, Art Assets, Free Data Library, Muscle Anatomy Trainer, Claude API Optimization, and "New project"): repo, site, docs to read first, areas, kinds of content. Edit it to add a project. |

Drafts are kept in your browser only.
