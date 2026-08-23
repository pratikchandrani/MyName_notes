---
aliases:
  - "onboarding guide"
  - "note-taking guide"
  - "student guide"
---

#PClab/NoteTaking #Concepts/Obsidian #Concepts/Zettelkasten

# Lab Note-Taking Guide - Start Here

Welcome. This vault ("MyName_notes") is the lab's shared brain - daily logs, project history, literature notes, and ideas all live here as plain Markdown files, connected by links and tags. This guide gets you from zero to writing your first daily note in about 30 minutes.

Read this once fully, then keep it open as a reference for your first few weeks. See also [[Obsidian guide]] for video tutorials and multi-device Git sync setup - this note focuses on *how we actually use the vault day to day*.

> [!tip] The one habit that matters most
> **Everything starts in today's daily note.** If in doubt about where to write something, write it in today's daily note first. You can always turn it into a linked Concept/Project note later. Nothing gets "lost" as long as it's in a daily note.

---

## 1. What Obsidian is, in one paragraph

Obsidian is a text editor for a folder of `.md` (Markdown) files - that folder is called a **vault**, and `MyName_notes` is ours. It adds three things on top of plain text files: **`[[wikilinks]]`** between notes, a **graph view** of how notes connect, and a **plugin system** (Dataview, Templater, Tasks, etc.) that turns plain text into live, queryable data. Nothing is locked into a proprietary format - every note is a `.md` file you could open in Notepad.

### Getting set up
1. Install Obsidian ([obsidian.md](https://obsidian.md)) on your laptop.
2. Get the vault: either clone the lab's GitHub repo (ask Pratik/a senior lab member for access) or get a copy of the folder.
3. **Open folder as vault** → select the `MyName_notes` folder.
4. Obsidian will detect the community plugins already configured in `.obsidian/` and ask to trust them - click **Trust author and enable plugins**. You'll immediately get the same plugin set, theme, and hotkeys everyone else uses.
5. For syncing your own edits back via Git across your devices, follow the **"Syncing MyName_notes across Windows, iPad, and Android"** section in [[Obsidian guide]].

### The three editing modes
- **Live Preview** (default) - formatting renders as you type, cursor position shows raw syntax. Use this day to day.
- **Source mode** - raw Markdown always visible. Useful when debugging why something isn't rendering.
- **Reading view** - fully rendered, read-only. What your notes look like "finished."

Toggle between these from the icon in the top-right of a note, or the command palette (`Ctrl/Cmd+P`).

### Essential moves
| Action                            | How                                                                                                 |
| --------------------------------- | --------------------------------------------------------------------------------------------------- |
| Open today's daily note           | Calendar plugin (right sidebar) → click today, or `Ctrl/Cmd+P` → "Open today's daily note"          |
| Create a link to another note     | Type `[[` and start typing the note name - autocomplete finds it                                    |
| See what links to this note       | **Backlinks** pane, bottom of right sidebar                                                         |
| Search everything                 | `Ctrl/Cmd+Shift+F` (full-text, powered by the Omnisearch plugin)                                    |
| Command palette (do anything)     | `Ctrl/Cmd+P`                                                                                        |
| Paste an image                    | `Ctrl/Cmd+V` directly into a note - it's saved into that folder's `assets/` subfolder automatically |
| See how a note connects to others | Graph view icon, left sidebar                                                                       |

---

## 2. Markdown basics

You don't need to memorize this - Live Preview shows you the result immediately - but here's the reference:

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold**   *italic*   ==highlight==   ~~strikethrough~~

- bullet list
  - nested bullet
1. numbered list

- [ ] an open task
- [x] a completed task

> A blockquote

[[Concepts/Apoptosis]]          → link to another note in the vault
[[Concepts/Apoptosis|apoptosis]] → same link, but displays as "apoptosis"
![[Pasted image 20260101.png]]  → embed an image that lives in the vault
[External link text](https://example.com)

`inline code`

​```python
# a fenced code block, syntax-highlighted
​```

| Table | Header |
|---|---|
| cell | cell |

#tag-name           → a flat tag
#Projects/YourProject → a hierarchical tag (nests under "Projects" in the tag pane)

---                 → horizontal rule, used a lot in this vault to separate sections/entries
```

**Callouts** (styled admonition boxes) are also supported - useful for flagging something in a note:

```markdown
> [!note] Optional title
> Content here

> [!warning]
> Something to be careful about
```
Common types: `note`, `tip`, `warning`, `example`, `question`, `quote`.

---

## 3. How this vault is organized

Top-level folders, and what actually lives in each:

| Folder              | Purpose                                                                                                                                                                                          |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `daily_notes/`      | One file per day, `YYYY-MM-DD.md`. **The entry point for everything you do.**                                                                                                                    |
| `Projects/`         | `Auto_summary/` holds one auto-generated rollup note per active project (pulled from daily notes - see §6). Some projects also still keep hand-written running-log notes in a project subfolder. |
| `Concepts/`         | Permanent reference notes - one per recurring topic/technique/gene/pathway you keep coming back to.                                                                                              |
| `Resources/`        | Lab SOPs, templates etc.                                                                                                                                                                         |
| `Events/`           | Conferences, guest talks.                                                                                                                                                                        |
| `Zotero_PDF_notes/` | If you use Zotero plugin to import articles and make notes from it's PDFs                                                                                                                        |

Every folder with images/attachments has its own `assets/` (or `files/`) subfolder - Obsidian pastes images there automatically, keeping attachments next to the notes that use them.

**Zotero PDF notes**: when you import a paper via the Zotero connector, it lands in a `Zotero_PDF_notes/` folder at the vault root (created automatically on first import), linked by citekey.

---

## 4. Daily notes - your main workflow

This is where you'll spend most of your time in the vault. Start with a daily note on everyday, take notes regarding whatever you are doing, use tags/file links to enrich your note with Obsidian specific functions which will allow you to build a connected network/structure over time. It will also allow you to build automated notes in `Projects/Auto_summary`.

### Creating today's note
Click today on the **Calendar** panel (left sidebar), or `Ctrl/Cmd+P` → "Daily notes: Open today's daily note." It's auto-created from the template at `resources/templates/daily.md`, which gives you a format with date, pending tasks, "Daily work updates" "End of daily work updates", Recent files, Foot notes. You should note your daily points in between "Daily work updates" and "End of daily work updates".

Rules of thumb:
- **One tag block per project/topic you touched that day.** Use bullet points in each block for continuity. Multiple projects in one day → multiple blocks, each starting with its own tag.
- **Link out, don't duplicate.** If something deserves a permanent, reusable note (a technique, a gene, a concept you'll reference again), `[[link it]]` rather than writing the whole explanation inline - see §6 for when to spin that off into a Concept note.
- **Log first, organize later.** You don't need the target note to exist before you link to it - click the resulting red/unresolved link later and Obsidian creates the note for you.
- **One daily note per day.** Don't create a second note for "later today" - just keep appending in same note per day.

---

## 5. Tags - the organizing backbone

Tags are how the vault turns scattered daily entries into structured, queryable project/topic histories via Dataview plugin. Conventions used across the vault:

| Tag pattern             | Meaning                         | Example                                             |
| ----------------------- | ------------------------------- | --------------------------------------------------- |
| `#Projects/ProjectName` | Work on a specific project      | `#Projects/LUADGenomicsLandscape`                   |
| `#JC`                   | Journal Club entry              | `#JC: Elveera - deep learning viral DNA in TCGA...` |
| `#WoW`                  | "Wonder of the Week" entry      | `#WoW: non canonical TCA cycle...`                  |
| `#Concepts/Topic`       | Cross-references a concept area | `#Concepts/GatewayCloning`                          |

**Use an existing project tag if one exists** - check [[_Index|Project Index]] (`Projects/Auto_summary/_Index.md`) for the current list before inventing a new one. Starting a brand-new project? Add a tag, use it consistently, and add the project to `_Index.md` so others can find its rollup.

To see every tag in the vault and how heavily used each is, open **`MoM/Table of Tags`** - it's a live Dataview query, always current.

---

## 6. Concept notes - your permanent knowledge base

A **Concept note** is a standalone, reusable reference note for something you'll refer back to repeatedly: a technique, a gene/pathway, a piece of software, a recurring theoretical idea. Think of it as the "permanent note" layer of a Zettelkasten - see [[Obsidian guide]] for the underlying philosophy (fleeting notes → literature notes → permanent notes).

**When to create one:** you can either plan ahead - think of concepts you are repeatedly going to refer in your project and make a dedicated note for them OR the second time you catch yourself explaining the same concept in a daily note, stop and make it a Concept note instead, then link to it in past notes and going forward.

**Structure to follow** (based on `Concepts/G4Quadruplex.md`):

```markdown
# Concept Title
Date updated:

One-paragraph short definition/summary.

---

## Sub-concepts
### Sub-topic A
- Bullet-point facts
### Sub-topic B
- Bullet-point facts

## Related Concepts
- [[OtherConcept]] - why it's related

## Resources/References
- Research Article
- URL

---

## Daily Notes Discussing this Concept
​```dataviewjs
const folder = '"daily_notes"';
const searchTerms = ["keyword1", "keyword2", "synonym"];
const pages = dv.pages(folder);
const results = [];
for (const page of pages) {
  const content = await dv.io.load(page.file.path);
  if (searchTerms.some(term => content.includes(term))) {
    results.push([page.file.link, page.file.name]);
  }
}
results.sort((a, b) => b[1].localeCompare(a[1]));
dv.table(["File", "Date"], results);
​```
```

The trailing Dataview block is what makes this "permanent" note self-updating: every time you mention one of those search terms in a daily note, it shows up here automatically - you never manually maintain a list of "where did I discuss this."

Once a Concept note exists, **link to it** from daily notes (`[[G4Quadruplex]]`) instead of re-explaining the concept inline.

---

## 7. Literature review workflow

1. **Reading a paper** - open it in Zotero, highlight/annotate as normal. Use the Zotero connector in Obsidian (`Ctrl/Cmd+P` → Zotero commands) to import your annotations as a note - it lands in `Zotero_PDF_notes/`, linked to the paper's citekey.
2. **Log the read in your daily note** the same day, under the relevant project tag - one or two lines on what you read and why it matters, plus a link to the imported Zotero note if you made one:
   ```markdown
   #Projects/Microchromosome
   - Read [[Zotero_PDF_notes/SmithEtAl2024]] - ploidy checkpoint mechanism
   ```
1. **If the paper introduces a concept you'll reuse** (a technique, a gene, a mechanism), create or update the relevant [[Concepts]] note and link it in your daily notes, following the structure in §6.

This mirrors the classic Zettelkasten literature-note step: the daily note captures *that* you read it, the Zotero note captures the source annotations, and the Concept note captures the durable, reusable knowledge.

---

## 8. Logging a longer-running experiment or idea

- **Log a pointer in your daily note** the day you work on it (`#Projects/G4Quadruplex - updated alignment strategy`), so it also surfaces in that day's history and in the project's Dataview rollup. Multi-day updates will pileup in project's notes automatically providing you a way to browse and keep track of it over longer duration.

> [!note] Formal per-experiment-type templates (PCR, western blot, cell culture, sequencing, etc.) can be standardized if you wish - the pattern above is the working convention. If you build a template for a technique you run often, save it under `resources/templates/` and link it in daily note with `[[Experiments/NameofExperiment]]` and put more details in there. You can configure template to automatically add experiments in Experiments directory. Remember to add project tag in experiment for automatic project's Dataview rollup.

---

## 9. Project rollups - how work becomes a project history

You never manually maintain a project's history - it's assembled automatically from your daily notes. Each project has an auto-summary note under `Projects/Auto_summary/` (e.g. `G4Quadruplex.md`) containing a `dataviewjs` block that scans every daily note for that project's tag and compiles a chronological list of everything ever logged under it - no copy-pasting required.

`Projects/Auto_summary/_Index.md` is the master directory of every project, lab activity, and knowledge resource in the vault. **When you start a new project:**
1. Pick a short, unique tag: `#Projects/YourProjectName`.
2. Use it consistently in your daily notes.
3. Add an entry to `_Index.md` and (ask a senior lab member to help set up, or copy an existing one like `G4Quadruplex` for consistency across lab memebrs) create the auto-summary note in `Projects/Auto_summary/`.

---

## 10. Tasks

Any line starting with `- [ ]` anywhere in the vault is a task the **Tasks plugin** tracks vault-wide. Mark it done with `- [x]`. Your daily note's "Tasks due from earlier" block automatically surfaces every open task in the vault - so jotting `- [ ] re-run alignment with new reference` in the middle of a daily entry is enough; it'll keep showing up until you check it off.

For a longer-running checklist tied to nothing in particular, use `Todo Lists/` and Todo plugin.

---

## 11. Plugin cheat-sheet

| Plugin                            | What it's for here                                                                                                                  |
| --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Dataview / dataviewjs**         | Powers every auto-updating table/list in this vault - daily note task lists, project rollups, Concept-note backlinks, the tag table |
| **Templater**                     | Auto-fills the daily note template (`resources/templates/daily.md`) when you open today's note                                      |
| **Calendar**                      | Sidebar calendar to jump to any daily note                                                                                          |
| **Tasks**                         | Vault-wide `- [ ]` task tracking                                                                                                    |
| **Tag Wrangler**                  | Rename/merge tags across the whole vault safely (right-click a tag)                                                                 |
| **Obsidian Git**                  | Auto commit/pull/push to GitHub every 10 min - see [[Obsidian guide]] for multi-device setup                                        |
| **Zotero Desktop Connector**      | Import paper annotations from Zotero straight into a linked note                                                                    |
| **Pandoc Reference List**         | Citation formatting/reference list support                                                                                          |
| **Kanban**                        | Board view for any note you want to manage as a kanban                                                                              |
| **Mind Map**                      | Visualize a note's outline as a mind map                                                                                            |
| **Omnisearch**                    | Full-text search (`Ctrl/Cmd+Shift+F`)                                                                                               |
| **Inline Admonitions / callouts** | The `> [!note]`-style boxes                                                                                                         |
| **Icon Folder**                   | Folder icons in the file tree (cosmetic)                                                                                            |
| **Advanced Tables**               | Add improved navigation, formatting, and manipulation to markdown tables                                                            |

---

## 12. House rules

- **Log in the daily note the day it happens.** Backfilling weeks later breaks the "what did I do this week" queries and defeats the whole point of the system.
- **Always start a work block with its project tag.** Untagged notes don't show up in any rollup and are effectively invisible to Dataview.
- **Prefer linking over duplicating.** If you're about to write the same explanation for the second/third time, that's a sign it should be a [[Concepts]] note.
- **Don't rename or move a Concept/Project note casually** - other notes link to it by name/path, and renaming breaks those links unless you let Obsidian's "update links" prompt handle it (it usually does, but double-check backlinks after).
- **Paste images, don't screenshot-and-link externally** - keeps everything self-contained and versioned in Git.
- **Check `_Index.md` before creating a new project tag** - avoid near-duplicate tags like `#Projects/Microbiome` and `#Projects/GutMicrobiome` for the same thing unless they really are distinct projects.
- **Ask before restructuring folders or plugin config.** The `.obsidian/` config is shared and synced via Git across everyone's devices. You can delink from lab repo and make local changes if you wish.

---

## 13. Day-1 checklist

-  Install Obsidian, open the vault, trust community plugins
-  Set up Git sync for your device ([[Obsidian guide]])
-  Open today's daily note and write one real entry under a project tag
-  Browse `Projects/Auto_summary/_Index.md` to see what's active in the lab
-  Open one existing [[Concepts]] note to see the target structure
-  Skim `MoM/Table of Tags` to see which project tags already exist
-  If you're starting a new project, pick your `#Projects/...` tag and add it to `_Index.md`
-  Bookmark this note (star icon, top-right) for quick reference

Questions on anything here → ask a senior lab member.
