# Lofi's Avalanche Run

A fast, snowy endless runner made for the CLAY Hackathon (Code Like a Yeti) on Sui. A yeti sprints down a mountain, dodges rocks and logs, grabs snowflakes, and tries to stay ahead of the avalanche.

**Play it:** https://tosin737.github.io/lofi-avalanche-run/

It runs in any modern browser, on desktop and on phones. No install, no build step, no account.

## How to play

Your yeti runs on its own. You pick the lane and decide when to jump or slide.

| Action | Keyboard | Touch |
| --- | --- | --- |
| Move left or right | Arrow keys or A / D | Swipe left or right |
| Jump | Up arrow, W or Space | Swipe up, tap, or the Jump button |
| Slide | Down arrow or S | Swipe down, or the Slide button |

Score is distance plus 10 points for every snowflake. The run speeds up the further you go, and so does the music.

## What is on the mountain

**Hazards**
- **Granite boulder:** fills one lane. Switch lanes.
- **Fallen pine:** spans all three lanes. Jump over it.
- **Icicle gate:** spans all three lanes. Slide underneath. Jumping still hits.
- **Black ice:** jump it, or lose speed for a moment.

**Pickups**
- **Snowflake:** +10 score. Snowflakes fly into the runner when you grab them.
- **Hot cocoa:** a shield that absorbs your next hit.
- **Headphones:** pull snowflakes toward you for 8 seconds.
- **Rocket sled:** 4 seconds of extra speed where nothing can hurt you.

## The chaser

Brute the Yeti rides the front of the avalanche, and he stays out of sight while you run clean.

- Your **first hit** brings him right behind you for about 3 seconds. A "ONE HIT LEFT" tag shows on screen.
- After that he slowly drops back out of view.
- A **second hit while he is close** and he catches you. The run is over.
- Once he has dropped back, the count starts over. A later hit just brings him back for another chase.

## Leaderboard

The Leaderboard tab keeps the top 10 runs on your device. Before a score is accepted, the game replays the run from its seed and recorded inputs and checks that the score matches, so edited scores are rejected. Scores are stored in your browser only, so they are not shared between players yet.

## Using the official Lofi art

The hero in this build is a placeholder yeti called Pip. To use your own character art, open the **Cast** tab and load a PNG with a transparent background. It replaces Pip in the game and in the cast list. The image stays in your browser and is not uploaded anywhere.

## Run it locally

It is a single file. Download `index.html` and open it in a browser.

To serve it from a folder instead, run this in the project folder and open the address it prints:

```
python -m http.server 8000
```

## Put it online with GitHub Pages

1. Open the repo's **Settings**, then **Pages**.
2. Under **Branch**, choose `main` and `/ (root)`, then save.
3. After a minute or two the game is live at `https://<your-username>.github.io/<repo-name>/`.

## How it is built

- One HTML file with the game, styles and audio together. No libraries, no build tools.
- The game logic is a fixed-step simulation that is separate from the drawing, which is what makes runs replayable and the leaderboard check possible.
- Graphics are drawn on a canvas, and every character is drawn in code.
- The soundtrack is generated live with the Web Audio API, and the tempo rises as you run.
- Fonts (Bricolage Grotesque, DM Sans, JetBrains Mono) load from Google Fonts. The game falls back to system fonts if they cannot load.

## Not in this version

There are no on-chain features yet. Scores and the leaderboard live in the browser. Wallet connection, soulbound run records and a shared leaderboard on Sui are the natural next steps.

## Credits

Built for the CLAY Hackathon, with help from Claude. Lofi the Yeti is the hackathon host's character, and the placeholder hero here is an original design.
