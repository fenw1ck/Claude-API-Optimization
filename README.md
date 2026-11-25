# Request Builder (Claude API optimization)

A form that turns a request for any of fenw1ck's projects into a clear, structured brief for Claude. Clear briefs mean fewer clarifying questions, less re-reading and smaller jobs, so each request uses less API.

**Live site:** https://fenw1ck.github.io/Claude-API-Optimization/ (once Pages is on: Settings → Pages → Deploy from a branch → `main`, `/ (root)`).

## How it works

1. **Fill in the order.**
   - Required: the project, the kind of request (something broken, a feature, new content, research, a question) and a one-sentence summary.
   - Each kind then asks for its own details: steps to reproduce, "done when", the source to follow, how deep to research.
2. **Fix what the ticket flags.** The ticket checks itself as you type:
   - required fields;
   - a summary that is too short or too long, or looks like two requests;
   - vague words like "fix it" or "make it better";
   - bug steps written on one line;
   - a missing finish line.
3. **Copy the ticket, or open it as a GitHub issue** in that project's repo (pre-filled).

Every ticket ends with **Before you start**. It names the project notes Claude should read first, says to ask at most one question, and limits the change to the job size you chose (quick / normal / thorough).

New art goes through the [Art Asset Builder](https://fenw1ck.github.io/Art-Assets/) instead, which can draw known subjects with no AI at all.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | the whole page (no build step) |
| `projects.json` | the projects the form knows (Euclid game, Planting Guide, Art Assets, Free Data Library, Muscle Anatomy Trainer, Claude API Optimization, and "New project"): repo, site, docs to read first, areas, kinds of content. Edit it to add a project. |

Drafts are kept in your browser only.
