# Zoosi

Free animal-learning games for young children. Animal names in English, Hmong White,
Hmong Green, and Spanish, each with recorded audio.

Live at **[zoosi.co](https://zoosi.co)**. Designed and illustrated by Tou Yia Xiong.

## What's here

This is the complete site — static HTML, no build step, no dependencies, no framework.
Open `index.html` in a browser and it runs.

| File | |
|---|---|
| `index.html` | Home page, game tiles, About panel, privacy policy modal |
| `memory.html` | Memory — flip and match animal pairs |
| `spelling.html` | Spelling Bee — drag letter tiles to spell the name |
| `flashcard.html` | Flashcards — swipe through animals |
| `jigsaw.html` | Puzzle Time — 3×3 interlocking jigsaw |
| `assets/img/` | 26 animal illustrations plus the memory card back |
| `assets/audio/` | 26 names × 4 languages, 104 recordings |
| `.htaccess` | Forces HTTPS on Apache. Ignored by GitHub Pages, which is HTTPS already |
| `404.html` / `404.shtml` | Same page. GitHub Pages reads `.html`, the Apache host reads `.shtml` |
| `.nojekyll` | Stops GitHub Pages running the files through Jekyll |

## Testing on GitHub Pages

Push this directory to a repository, then in **Settings → Pages**, set the source to
the branch root. The site appears at `https://<user>.github.io/<repo>/` within a minute
or two.

Every path in the code is relative, so the site works from a subdirectory without changes.

### Worth knowing

- **Audio needs a real tap first.** Browsers block autoplay until the user interacts with
  the page. Tap a game before expecting sound — this is normal and not a bug.
- **`og:image` points at `https://zoosi.co/assets/og-image.png`,** which is absolute and
  therefore still resolves against the live site rather than the test copy. That file is
  not in this repo. It only affects link-preview cards, nothing on the page itself.
- **Opening files directly from disk** (`file://`) works for everything except a few audio
  paths in some browsers. GitHub Pages avoids this. To test locally instead, run
  `python3 -m http.server` in this directory and open `http://localhost:8000`.

## What to check in the jigsaw

It's the newest game and the least exercised:

- Dragging with a finger, not just a mouse
- Whether pieces snap home too eagerly or not eagerly enough
- Rotating the device mid-puzzle — already-placed pieces should stay placed
- All nine pieces landing triggers confetti and speaks the animal's name

## Deploying to the live host

Upload the contents of this directory to `public_html`, keeping the folder structure.
Rename `.htaccess` if your file manager hides dotfiles — it must keep the leading dot
on the server, or the HTTPS redirect stops working.
