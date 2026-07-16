# Sigilry v2 — A Register of Names

A single-file generative identity ritual. Your name becomes a geometry, a melody,
and a small companion — then takes its place in a register of everyone who signed
before you.

**Live structure: three phases**

- **Arrival** — the question (*who are you?*), a signature line, a bodiless eye
  waiting, prior visitors' marks bleeding through the paper.
- **Inscription** — press Enter: the name is set large, its letters walk to their
  vertices, the path is drawn by hand and scored by its own melody, the press
  stamps the card, the creature is born from the mark. Skippable once seen.
- **Presentation** — the card (tilt, swatches, stroke styles), The Record
  (letter → vertex decode), The Bind (someone you love, side-by-side or
  interwoven), exports (SVG · PNG · film with sound), and The Register.

**Everything derives from the same seed.** FNV-1a hash of the cleaned name →
vertex count, start angle, path, ornament, color, root note + pentatonic mode.
The sigil algorithm is byte-identical to v1.

## Deploy

It's one file. Replace `index.html` on the `main` branch of the GitHub Pages
repo. Fonts come from Google Fonts; everything else is inline.

## Storage

`Store` (in the source, section 20) is an async key/value adapter that picks
`window.storage` → `localStorage` → memory. The register and visitor memory sit
behind it; a real backend implements the same `get`/`set` (see the
`RemoteAdapter` sketch in the source) and, for the register proper, replaces
`Registry.add`/`Registry.all` with two endpoints. Visitor numbers would then be
assigned server-side.

## For the curious

- The letters that vanish mid-flight during Inscription are consecutive
  duplicates — the same rule The Record documents.
- Sound is off by default. The toggle persists. The film export is always scored.
- The creature remembers. Come back, and keep coming back.
- Try signing the register with the name of the register itself.

## Dev

```
./build.sh        # concatenates src/ sections into index.html
node test/run.js  # headless run-through of all three phases
```
