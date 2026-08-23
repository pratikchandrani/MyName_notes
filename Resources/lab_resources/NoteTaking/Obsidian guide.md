> [!tip] New to the lab?
> Start with [[New Student Note-Taking Guide]] — it covers Obsidian/Markdown basics, daily notes, tags, Concept notes, and literature review workflow end to end. This note is a supplementary link dump plus the device-sync instructions.

- Video tutorial - basic formatting, daily notes, Zettelkasten, Dataview, git, templates, PDF annotations - https://www.youtube.com/watch?v=WqKluXIra70 This video should be enough to get started but if one needs more information then following links will help.
- Obsidian basic formatting guide - https://www.epoch-magazine.com/post/epoch-tutorials-an-introduction-to-obsidian
- More technical setup guide - https://www.emilevankrieken.com/blog/2025/academic-obsidian/
- Concepts of Zettelkasten - https://www.aidanhelfant.com/3-days-to-starting-a-zettelkasten-in-obsidian-as-a-student-part-2/ and https://www.aidanhelfant.com/3-days-to-starting-a-zettelkasten-in-obsidian-as-a-student-part-1/
- Obsidian note example for a biological course - https://sparkl.me/blog/ap/obsidian-zettelkasten-mastering-ap-concepts-with-smart-notes/
- 

## Setup Git and clone the template
- Make a free account on GitHub, visit this URL: https://github.com/pratikchandrani/MyName_notes/ and click on fork at top right. 
- Choose owner as your GitHub profile name and provide proper name "NameSurname_notes" as repository name. 
- Click on fork. Now the template is copied to your own GitHub account with the name "NameSurname_notes" and your URL is at top of browser after it is forked. You can use this URL for rest of the guide.


#Concepts/Zettelkasten #Concepts/Obsidian  
- A Zettelkasten (German for "slip box" or "card index") is a note-taking and knowledge management system developed by German sociologist Niklas Luhmann in the early 20th century.
- At its core, a Zettelkasten is a collection of three main types of notes: fleeting notes (notes on fleeing thoughts, kind of daily notes), literature notes (notes taken from resources like books, articles, etc.), and permanent notes--kind of concept/project notes (notes with one focal idea that often have literature notes backing them up). At it's core the Zettelkasten works by using daily notes and literature notes that connect together to a project note over months and years forming a knowledgebase that compounds over time.
- #PClab/NoteTaking In a research laboratory, one can have a daily note template to record day to day progress as bullet points and then have specific templates for major experiments (NGS analysis, cloning, PCR etc.) wherein structured experimental data can be captured. One can also use daily notes to capture new concepts from article reading and integrate the same with Zotero based reference manager. While taking notes in all these ways, one should add Hashtag related to projects and major concepts of their interest so that they can use Dataview to automate a project specific note building which allows them to periodically review overall progress.

#Concepts/Obsidian #Concepts/Git 
# Syncing "MyName_notes" across Windows, iPad, and Android

Your vault already uses the **Obsidian Git** plugin to sync through GitHub (`github.com/YourGitHub/MyName_notes`). This machine's plugin is already configured for a 10-minute cycle. This guide gets your other three devices onto the identical setup.

## How it actually works (read this first)

- **What syncs automatically once you clone/pull:** theme, snippets, hotkeys, and every community plugin (`dataview`, `templater-obsidian`,  `obsidian-kanban`, etc.) — all tracked in `.obsidian/` and committed to the repo. Pull the repo on a new device and you get the same look and plugin set with no manual reinstalling.
- **What does NOT sync, on purpose:** each device's open tabs/pane layout  (`workspace.json`, `workspace-mobile.json`) and the Git plugin's own  `data.json`. Both are gitignored intentionally — otherwise your 4 devices would fight over window layout on every sync, and each device needs its *own* commit-author identity anyway. This means **the 10-minute interval has to be set manually on each device** — it's a per-device setting, not  something the repo can carry for you.
- **Sync engine:** the plugin auto-commits, pulls, then pushes, using a  `merge` strategy — so if two devices edited different files (or even  different parts of the same file), it resolves automatically without  prompting you. True conflicts (same lines edited on two devices before  either synced) get written as `<<<<<<<` markers in the file, and you  resolve them like a normal git conflict.
- **Mobile constraint:** iPad and Android don't have a system `git`  binary — the plugin ships its own JS git implementation for mobile,  which only speaks HTTPS, not SSH. So auth on mobile is via a GitHub  **Personal Access Token (PAT)** typed into the plugin once. Desktop can  also just use a PAT over HTTPS, which keeps auth identical across all  four devices instead of mixing SSH keys and tokens. 

## Target settings (already live on this Windows PC)

Replicate these in Settings → Community Plugins → Git on every device:

| Setting | Value |

|---|---|

| Vault backup interval (auto commit) | `10` (minutes) |

| Auto pull interval | `10` |

| Auto push interval | `10` |

| Pull updates on startup | On |

| Pull before push | On |

| Merge strategy | Merge (not rebase) |

| Commit message | `vault backup: {{date}}` |

  ---
## 1. One-time: create a GitHub Personal Access Token

Needed for the new Windows PC, iPad, and Android — one token per device is cleanest (lets you revoke one device without affecting the others).  

1. GitHub → Settings → Developer settings → **Personal access tokens** → Fine-grained tokens → **Generate new token**.

2. Repository access: only `YourGitHub/MyName_notes`.

3. Permissions: **Contents → Read and write**.

4. Expiration: pick something you're comfortable renewing (e.g. 1 year).

5. Generate, copy the token immediately (shown once) — treat it like a password. Repeat for each new device, naming each token clearly (`MyName_notes-windows2`, `MyName_notes-ipad`, `MyName_notes-android`).  

---
## 2. Windows PC

1. **Install Git** (git-scm.com) and **Obsidian** (obsidian.md). Ensure Git is in environment path.

2. Do this once: Clone the repo to wherever you want the vault folder to live in your PC, e.g.:

   ```

   git clone https://github.com/YourGitHub/MyName_notes.git

   ```

   When Git Credential Manager prompts for auth on the first `push`, use  your GitHub username and paste the PAT as the password.

3. Open Obsidian → **Open folder as vault** → select the cloned folder.

4. Obsidian will detect community plugins already in `.obsidian/plugins`  and ask to trust them — click **Trust author and enable plugins**.  You should immediately see the same plugin list and theme as this PC.

5. Settings → Community plugins → **Git** (gear icon) → set the three intervals to `10` and confirm "Pull updates on startup" and "Pull before push" are enabled, matching the table above.

6. Do a manual **Commit-and-Sync** from Obsidian itself once (command palette → `Git: Commit and sync`) to confirm push/pull auth works end-to-end.

7. One can also setup Obsidina/Git on Windows like iPad/Android as shown below. 

---
## 3. iPad/iPhone

1. Install **Obsidian** from the App Store.

2. Create a new vault "setup" (any name — it will be replaced when we sync). Choose local storage and not iCloud as we are going to sync through Git.

3. Settings → Community plugins → turn off restricted mode → Browse →  search **"Git"** → install → enable.

4. Open the command palette (swipe-down search icon or the command icon)  → run **"Git: Clone an existing remote repo"**.

   - Repo URL: `https://<PAT>@github.com/YourGitHub/MyName_notes.git`

   - Directory for clone: type . (vault root)

   - It'll ask "Does your remote repo contain a .obsidian directory at the root?" → answer Yes (now true)

   - It'll warn about deleting local config → choose delete all your local config and plugins

   - Depth: leave blank, let it clone

   - Wait for the cloning, it will replace your setup vault, give restart prompt and then restart obsidian app

5. Once cloned, close and reopen the vault so Obsidian re-reads

   `.obsidian/`. Trust the plugins when prompted — theme and plugin list should now match.

6. Settings → Community plugins → Git → set the same three intervals (it will be automatically set if you sync lab template)

   (`10`/`10`/`10`) and toggle "Pull on boot" + "Pull before push" on.

7. **iOS caveat:** background execution is heavily restricted — the 10-minute timer only actually fires while Obsidian is open/foregrounded (or briefly backgrounded). It won't silently sync every 10 minutes with the app fully closed. In practice: open the app before you start reading/editing (it'll pull), and it'll auto-push while you work. If you want a guaranteed pull on open, "Pull on boot" already covers that.

---
## 4. Android

Same steps as iPad, Android-specific notes only:

1. Install **Obsidian** from the Play Store. Create a new vault. Turn ON the "App storage" toggle when creating it — if you leave it off, Android's storage permission model (SAF) causes the Git plugin to freeze/hang during clone.

2. Community plugins → enable → install **Obsidian Git** → enable.

3. Command palette → **"Git: Clone an existing remote repo"** → same URL `https://<PAT>@github.com/YourGitHub/MyName_notes.git`

4. Reopen vault, trust plugins, confirm theme/plugin parity.

5. Git plugin settings → same `10`/`10`/`10` intervals, "Pull on boot" +   "Pull before push" on.

6. **Android caveat:** less aggressive background-kill than iOS by  default, but manufacturer battery optimizers (Samsung, Xiaomi/MIUI,  OnePlus) often kill background apps aggressively. If you notice syncs not firing while the app is backgrounded, exempt Obsidian from battery optimization: Settings → Apps → Obsidian → Battery → **Unrestricted**.
 

---
## 5. Sanity check across all four devices


- Edit a test note on one device, wait for the auto-commit/push (or trigger `Git: Commit and sync` manually), then open another device and  confirm the change shows up within ~10 minutes (or immediately if you also lower "Pull before push" delay by syncing manually).

- Confirm all four show the same theme, same plugin list, same hotkeys —   if one looks different, it likely hasn't pulled yet, or plugins weren't trusted/enabled after clone.

- If you ever see `<<<<<<<`/`=======`/`>>>>>>>` markers in a note, that's a real merge conflict — open the file, keep the version you want, delete the markers, then commit-and-sync again.

## 6. Security note

PATs are scoped to just this one repo with read/write content access — still, treat each one as a password. If a device is lost or a token leaks, revoke it individually from GitHub → Settings → Developer settings → Personal access tokens, and create new one.
