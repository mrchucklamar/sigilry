# Sigilry

A personal sigil drawn from your name. Each name yields a unique mark.

Built as a single self-contained HTML file — no build step, no dependencies beyond Google Fonts.

## How it works

Each name is hashed (FNV-1a) into a seed. The seed drives a deterministic random number generator that places vertices around a ring. Each letter of your name maps to a vertex by its position in the alphabet (`'a' → 0`, `'b' → 1`, etc., wrapped to the vertex count). Connecting those vertices in order traces a unique path — your sigil.

Open the "Inscribed Path" panel to see the letter-to-vertex mapping live, with a small companion that watches you work.

## Run it

Just open `index.html` in any modern browser. No server needed.

## Credits

Inspired by editorial-stationery aesthetics and the playful onboarding flows that make the web feel handmade.
