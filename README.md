# Tekkendle

A daily Tekken guessing game. Identify the day's fighter across five puzzle modes, or play real-time 1v1 against another person.

**Live:** [tekkendle.netlify.app](https://tekkendle.netlify.app)

## What it does

Every day there's a new fighter to guess. Five modes give you different clues: a combo notation, a frame-data readout, a zoomed-in portrait, an emoji rebus, and a stage soundtrack. You get a limited number of tries, and the game tracks your streak and win rate.

Versus mode puts you against a real opponent. Search for a random match or share a 5-character code to play someone specific. If nobody's available or the connection drops, you fall back to a CPU opponent instead of waiting.

## How it works

Vanilla JavaScript, one HTML file, no framework. Multiplayer runs over Supabase Realtime: two browsers connect through a shared channel, and the whole match flow (character select, mode bans, rounds, rematch) passes through one transport interface. A CPU opponent and a live opponent both implement that same interface, so the game loop doesn't know or care which one it's playing. That's also what makes the CPU fallback seamless.

## Stack

HTML, CSS, vanilla JavaScript, Supabase (Realtime), deployed on Netlify.

## Running it locally

It's a single static file. Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server
```

Versus mode needs Supabase credentials set in the script to connect real players. Without them, the daily puzzles and CPU practice still work offline.

## Credits

Fan-made, unaffiliated with Bandai Namco. Character and stage assets belong to their respective owners.
