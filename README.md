# H2L — HTML to Life

> One file. No build. No dependencies. Double-click and play.

**▶ Play them live: [erikvanberkel.github.io/h2l](https://erikvanberkel.github.io/h2l/)**

**H2L** is a collection of complete, self-contained applications that live inside a
single `.html` file each. No `npm install`. No bundler. No CDN. No service worker.
No backend. You open the file in any browser — on a laptop, a phone, a museum kiosk,
a 10-year-old machine with no internet — and it just runs.

Every artifact in this repository obeys one hard rule:

> **The entire thing — markup, styling, logic, art, audio, levels — fits in one
> HTML file that depends on nothing but the browser.**

That constraint is the whole point. It is what makes these files durable, portable,
forkable, and honest.

---

## Why a single file?

Modern web projects are extraordinary at producing software that works *today, on my
machine, with this lockfile*. They are terrible at producing software that still runs
in five years. A single self-contained HTML file flips that:

- **It survives.** No dependency rots. No registry goes dark. No build step breaks.
  The file you save today opens the same way in 2035.
- **It travels.** Email it. Drop it on a USB stick. Host it on anything that serves
  static files. Open it from `file://` with no server at all.
- **It is legible.** Everything is in one place. There is no hidden framework
  deciding things for you — `view-source:` is the complete truth of the program.
- **It is yours.** Fork by copying. Modify by editing. There is no toolchain between
  you and the code.
- **It is fast.** One request. No hydration. No waterfall. The browser parses it and
  the thing is alive.

The web platform itself is now powerful enough — Canvas, WebGL, Web Audio,
`requestAnimationFrame`, pointer/touch events, CSS animation — that "no dependencies"
is no longer a limitation. It's a discipline that produces better, smaller, more
understandable software.

---

## The rules

Anything that lives here must:

1. **Be exactly one `.html` file.** All CSS in `<style>`, all JS in `<script>`, all
   art generated in-code or inlined (data URIs / procedural generation). No sibling
   assets.
2. **Have zero runtime dependencies.** No external scripts, fonts, stylesheets, or
   network calls. If it needs the internet to run, it doesn't belong here.
3. **Run from `file://`.** Opening the file directly — no local server — must work.
4. **Work on a phone and a desktop.** Responsive layout; touch *and* keyboard/mouse
   where it makes sense.
5. **Degrade gracefully.** No console errors, no broken state on resize, no reliance
   on bleeding-edge APIs without a fallback.

If a file breaks any of these, it gets fixed or it leaves.

---

## What's inside

Right now H2L is a small arcade. Each title is a complete game in one file.

| Play                                                                        | Title              | What it is                                                                 |
| --------------------------------------------------------------------------- | ------------------ | -------------------------------------------------------------------------- |
| [**HORNET STRIKE**](https://erikvanberkel.github.io/h2l/fa18.html)          | `fa18.html`        | Pseudo-3D flight combat with 9 missions, including a realistic runway takeoff. |
| [**SUNSET DRIVE**](https://erikvanberkel.github.io/h2l/outrun.html)         | `outrun.html`      | An Outrun-style arcade racer with on-screen touch controls for mobile.     |
| [**GALAGA**](https://erikvanberkel.github.io/h2l/galaga.html)               | `galaga.html`      | A faithful clone of the classic fixed-shooter, dives and all.              |
| [**SPACE INVADERS**](https://erikvanberkel.github.io/h2l/spaceinvaders.html)| `spaceinvaders.html` | The original marching-aliens shooter, rebuilt from scratch.              |
| [**T5**](https://erikvanberkel.github.io/h2l/t5.html)                       | `t5.html`          | A falling-block puzzle with modern guideline rules (hold, ghost, kicks).   |

All five are pure Canvas/JS, render their own art and sound, and clock in between
~28 KB and ~80 KB — the complete game, in a file smaller than most images.

---

## Running them

There is no setup. Pick whichever you like:

- **Online**, instantly — open [erikvanberkel.github.io/h2l](https://erikvanberkel.github.io/h2l/)
  (e.g. [outrun](https://erikvanberkel.github.io/h2l/outrun.html)) and play in the browser.
- **Double-click** the `.html` file. It opens in your default browser and runs.
- **Drag** the file onto an open browser window.
- Or serve the folder statically and visit the file:

  ```sh
  # any static server works; here's one with zero install if you have python
  python -m http.server 8000
  # then open http://localhost:8000/galaga.html
  ```

That's it. No install, no flags, no environment variables.

---

## The plan

H2L starts as games because games exercise the platform hardest — real-time
rendering, input, audio, state. But the charter is broader than games. The name is
**HTML to Life**: anything worth using that can be expressed as one living,
self-contained page belongs here.

The roadmap is less a list of features than a set of directions:

- **More games.** Different genres, different rendering tricks (2D Canvas, WebGL,
  pure-CSS). Each one a self-imposed challenge: how much game fits in one file?
- **Tools and apps.** Calculators, editors, visualizers, generators, toys — small,
  sharp utilities that load instantly and need no account.
- **Demos and experiments.** Shaders, simulations, generative art, audio
  synthesizers — the kind of thing you bookmark and come back to.
- **A shared craft.** Patterns that recur across files — a tiny game loop, a Web
  Audio sound kit, a responsive Canvas scaler, a touch-control overlay — documented
  and reused by copy-paste, never by dependency.

The unifying thesis stays fixed even as the contents grow: **the best way to make
software that lasts is to make it depend on as little as possible.** One file is the
smallest unit of software that can do something real. H2L is an argument, made by
example, that it's also one of the most powerful.

---

## Contributing / adding your own

To add something:

1. Build it as a single `.html` file that obeys [the rules](#the-rules).
2. Make sure it opens cleanly from `file://` with no console errors.
3. Check it on a phone-sized viewport and a desktop one.
4. Drop it in the repo root and add a row to [What's inside](#whats-inside).

Keep it self-contained. Keep it honest. If you can't open it by double-clicking,
it isn't done.

---

*H2L — because the most durable software is the kind that needs nothing but a browser.*
