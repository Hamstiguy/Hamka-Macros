# Macros | By hamka

**Build your own input macros from Scratch-style blocks, or let an AI build them for you.**
Windows · single exe · English & Deutsch · [Deutsche Version](README.de.md)

![Ready-made macros](docs/img/ready-made.png)

---

## ⚠️ Read this first

**Macros is a tool for automating your own mouse and keyboard input. It is not a cheat client, and it must not be used as one.**

- **Only use it where it is allowed:** your own computer, single-player worlds, private servers and communities that explicitly permit macros, practice and training, accessibility (for example holding a repetitive input for you).
- **Do not use it** on servers, games, tournaments or ranked/competitive modes whose rules forbid automation or macros. Many public multiplayer servers do. **Check the rules before you switch anything on.**
- Using a macro where it is not allowed can get your account **banned**. That is **your decision and your responsibility**. The author gives **no support** for getting around anti-cheat systems and does not want to be asked.
- **Use at your own risk.** The software is provided "as is", without any warranty. The author is not liable for bans, lost accounts, lost progress, damaged files or anything else that results from using it.
- The optional Minecraft mod (*Macros Bridge*) only **reads** game information. It does not change the game, send packets or move the player.
- Macros you download from the marketplace were written by other people. Look at what a macro does (open it in the block editor) before you switch it on.

If you do not agree with this, do not use the program.

---

## What it does

| | |
|---|---|
| **Ready-made** | A few finished, configurable macros (for example *Stun Slam*) with keybind, delay and slots right on the card. |
| **Custom** | Your own macros as cards. Click a card to switch it on, double-click to open the block editor. |
| **Block editor** | Scratch-like blocks: waits, key and mouse inputs, loops, conditions, variables, lists, your own blocks, and optional Minecraft blocks. Several stacks run at the same time. |
| **AI macro agent** | Describe what you want; the agent builds the macro, checks it, tests it in a simulator and hands you a card (*Add / Replace / Test*). |
| **Marketplace** | Share your macros and add other people's with one click. No account needed. |
| **Themes** | 13 themes, from soft pastel to pure black. |

![Custom macros](docs/img/custom.png)

![Block editor](docs/img/editor.png)

---

## Install

1. Download **Macros.zip** (or just **Macros.exe**) from the [latest release](https://github.com/Hamstiguy/Hamka-Macros/releases/latest).
2. Unzip it and run **Start Macros.cmd**. On the first start it trusts the publisher certificate (Windows asks for administrator rights once) and removes the "downloaded from the internet" mark.
3. After that, the app updates itself from new releases.

Requirements: Windows 10 or 11 (64-bit). Windows may show a SmartScreen note because the program is signed with a self-made certificate and not a paid one. Only install it from the release page above.

> The one exe is all you need. Your settings live in `%APPDATA%\PrestigeMacros`.

---

## Quick start: your first macro

1. Open **Custom** and click the dashed **New macro** tile (the plus). A working start macro appears: *click while the trigger is held*.
2. Click the new card to switch it on. Hover it: it glows, and the selected state stays visible.
3. Double-click the card (or use **Customize Macro**) to open the block editor.
4. Drag blocks from the left palette into the workspace. Change numbers directly in the blocks. Values you want on the card get a label (*card settings*).
5. Pick a **trigger** key at the top. The macro runs while you use that key.
6. Want to share it? Open **Marketplace → Publish** (see below).

> Tip: don't know which block you need? Press **AI** (top right) and just describe the macro.

---

## AI macro agent: set it up

Open the side panel with the **AI** button. Which AI answers is chosen in **Settings → AI for the macro agent**. The chat, the tools and the macro cards are the same for all three. Pick one:

![AI settings](docs/img/settings-ai.png)

### Option A – NVIDIA NIM (recommended)

Free API key, about 40 requests per minute. The app paces itself and switches to the next model when one is busy.

1. In **Settings → AI for the macro agent** choose **NVIDIA NIM** and click **Get key**. This opens `build.nvidia.com`.
2. Sign in there (a free NVIDIA account) and create an **API key**.
3. Paste the key into **NVIDIA API key** in the app. It is stored **encrypted on this PC** (Windows DPAPI) and never shown again.
4. Click **Test**. One tiny request confirms that the key works.
5. Choose a model chip (default `deepseek-v4.1-flash`) and open the AI panel.

### Option B – Freebuff CLI

Uses the Freebuff command-line tool, started invisibly in the background. It has daily free hours; when the premium model's hours run out, the app takes the best unlimited one.

1. Install [Node.js](https://nodejs.org), then in a terminal:
   ```bash
   npm install -g freebuff
   ```
   (or press **Install Freebuff** in the app's settings).
2. Sign in once:
   ```bash
   freebuff login
   ```
3. In **Settings → AI for the macro agent** choose **Freebuff CLI**. The app finds the installed tool by itself.

### Option C – DeepSeek Chat (your own account)

Uses your DeepSeek account in a built-in browser (Microsoft Edge WebView2). No API key.

1. Choose **DeepSeek Chat** in the settings and open the AI panel.
2. The real DeepSeek page appears once. **Sign in there yourself.** The app never types your credentials, and the login stays saved on this PC.
3. After the sign-in the page disappears and you chat in the app. The app sends at most one message every 8 seconds, so DeepSeek is not flooded. Under load you may see "server busy".

If DeepSeek does not load, install the Microsoft Edge **WebView2 runtime**.

### Using the agent

- Write what you want: *"Click while I hold mouse 5, about 12 clicks per second, with a bit of randomness."*
- The panel shows what the agent does: thinking, searching the block library, writing the macro, checking it, testing it in a simulator.
- When it finishes you get a macro card with **Add** (new macro), **Replace "…"** (when you opened one in the editor), **Test** and **Code**.
- **Think** gives the AI more time to reason; **web** (where available) lets it search the internet.
- A provider switch starts a new chat.

![AI chat](docs/img/ai-chat.png)

Privacy: your messages and the macro text go to the provider you chose (NVIDIA, Freebuff or DeepSeek). Don't write secrets into the chat.

---

## Marketplace

![Marketplace](docs/img/marketplace.png)
*Example entries, shown for illustration.*

- **Add:** click the download bar on a card. The macro is checked before it is added, and it is added **switched off**.
- **Publish:** click **Publish**, pick one of your macros and give it a name, a short description and tags. Click **Publish macro**.

![Publish dialog](docs/img/publish.png)

Rules of the marketplace:

- The unchanged **start macro** (the one every new macro begins with) cannot be published, whatever its values. Build something of your own first.
- Titles with offensive words are refused; authors with such a name are shown as "Anonymous".
- Uploads are rate limited: **one per minute** per device, then **5 per hour and 15 per day**, and **8 per hour and 25 per day** per network. When you hit a limit, the app tells you how long to wait.
- Every entry can be reported. Reported entries are reviewed.

---

## Themes

13 themes, including pastel **Prestige**, **Light**, and a plain **Black**. Switching is instant.

![Themes](docs/img/themes.png)

---

## Minecraft blocks (optional)

If you play Minecraft, the *Macros Bridge* Fabric mod (install it from **Settings**) lets blocks **read** information such as health, hunger, items and nearby entities, so macros can react to what happens. The mod is read-only. Many servers forbid client mods and macros, so see **Read this first** above before you use it online.

---

## Tips & troubleshooting

- **A macro does nothing:** is its card switched on, and is the right key set as the trigger?
- **A macro is too fast or too slow:** most blocks have a time with a *±* random range. Change it on the card.
- **"Please wait…" while publishing:** you hit the upload limit; wait the shown time.
- **AI says the free tier is busy:** the app tries the next model automatically; wait a moment or choose another provider.

---

## For developers

Source overview and internals are in [CONTEXT.md](CONTEXT.md). The marketplace backend (Cloudflare Worker + D1) is in [docs/market-backend.md](docs/market-backend.md).

## License and credits

Made by **hamka**. Licensed under the [Apache License 2.0](LICENSE). Not affiliated with Mojang, Microsoft, NVIDIA, DeepSeek or Freebuff; all names belong to their owners.
