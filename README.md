# Tiny Arcade

A home for small browser games. The site is plain HTML and CSS, so there is no build step or package installation.

## Preview locally

From the repository root, run:

```sh
python3 -m http.server 8000 --directory site
```

Open <http://localhost:8000/>.

## Add a game

1. Create `site/games/<game-slug>/index.html` and put the game's assets alongside it. Use relative URLs for assets so games work both locally and on GitHub Pages.
2. Replace the empty-state block in `site/index.html` (inside `.game-grid`) with a card like this. Add more cards to the same grid as you add games:

   ```html
   <a class="game-card" href="./games/game-slug/">
     <span class="game-card__art" aria-hidden="true">✦</span>
     <span class="game-card__body">
       <span class="game-card__category">Puzzle · 5 min</span>
       <span class="game-card__title">Game title</span>
       <span class="game-card__description">A short description of the game.</span>
       <span class="game-card__action">Play game <span aria-hidden="true">↗</span></span>
     </span>
   </a>
   ```

3. Update the game count in the collection heading on `site/index.html`.

## Deploy

In the repository's **Settings → Pages**, select **GitHub Actions** as the build and deployment source. Pushing to `main` (or running the workflow manually) publishes the contents of `site/` to GitHub Pages. Relative links keep the site working at either a user/organization domain or a repository subpath.
