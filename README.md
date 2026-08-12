# corpaniaproductions.com

Static site for Corpania Productions. No build step — plain HTML, served as-is.

## Structure

    index.html          Home
    about.html          About
    television.html     Television / Series
    films.html          Films & Screenplays
    novels.html         Award-Winning Books
    support.js          rendering runtime (required — do not remove)
    assets/             images, logos, intro video
    CNAME               custom domain
    .nojekyll           tells GitHub Pages to serve files verbatim

## Uploading via the GitHub website (100-file limit per upload)

The web uploader accepts at most 100 files per drag. Do it in two passes:

  Pass 1 — the 5 .html files + support.js + CNAME + README.md   (8 files, ~1 MB)
  Pass 2 — assets/awards + assets/brand + assets/networks + assets/training + assets/image-slot.js
  Pass 3 — assets/press + assets/work
  Pass 4 — assets/video/corpania-intro.mp4  (12.4 MB — on its own)

Images are already compressed for the web (total ~6 MB excluding the video).
The browser uploader also caps TOTAL upload size, not just file count, which is
why the video goes up by itself.

Each pass is its own commit. Drag the `assets` FOLDER itself (not its contents)
so the subfolder paths are preserved.

If a folder ever exceeds 100 files, use GitHub Desktop instead — it has no limit
(Add Local Repository -> point at this folder -> Publish).

## Deploying

1. Upload every file and folder here to the repository root on the `main` branch.
2. Settings -> Pages -> Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Settings -> Pages -> Custom domain: corpaniaproductions.com
4. DNS at your registrar:
   - A records for @  ->  185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - CNAME for www    ->  immortalitybytes.github.io
5. Once the certificate is issued, tick "Enforce HTTPS".

## Notes

- `assets/video/corpania-intro.mp4` (12 MB) is the opening animation. It is a real
  file rather than embedded data so browsers stream and cache it.
- The intro plays once per visitor (remembered in localStorage).
  Append `?intro=1` to any URL to force a replay: corpaniaproductions.com/?intro=1
- File names are case-sensitive on GitHub Pages. Keep them exactly as they are.
